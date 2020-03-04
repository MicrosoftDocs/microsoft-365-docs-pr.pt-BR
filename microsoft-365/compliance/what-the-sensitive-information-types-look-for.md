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
ms.openlocfilehash: 368ccef9e5213a7494140d2c305ddafe1e0c3f79
ms.sourcegitcommit: 9c335d110e0b499501edc8a31b987641819118a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2020
ms.locfileid: "42409506"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="4d3ce-104">O que os tipos de informações confidenciais procuram</span><span class="sxs-lookup"><span data-stu-id="4d3ce-104">What the sensitive information types look for</span></span>

<span data-ttu-id="4d3ce-105">A prevenção de perda de dados (DLP) no centro &amp; de conformidade de segurança do Office 365 inclui muitos tipos de informações confidenciais que estão prontos para uso nas suas políticas de DLP.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="4d3ce-106">Este tópico lista todos os tipos de informações confidenciais e mostra o que uma política de DLP procura ao detectar cada tipo.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="4d3ce-107">Um tipo de informação confidencial é definido por um padrão que pode ser identificado por uma função ou uma expressão regular.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="4d3ce-108">Além disso, evidências corroborativas, como palavras-chave e somas de verificação, podem ser usadas para identificar um tipo de informação confidencial.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="4d3ce-109">O nível de confiança e a proximidade também são usados no processo de avaliação.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="4d3ce-110">Número de roteamento ABA</span><span class="sxs-lookup"><span data-stu-id="4d3ce-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-111">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-111">Format</span></span>

<span data-ttu-id="4d3ce-112">9 dígitos que podem estar em um padrão formatado ou não formatado</span><span class="sxs-lookup"><span data-stu-id="4d3ce-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-113">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-113">Pattern</span></span>

<span data-ttu-id="4d3ce-114">Binário</span><span class="sxs-lookup"><span data-stu-id="4d3ce-114">Formatted:</span></span>
- <span data-ttu-id="4d3ce-115">Quatro dígitos, começando com 0, 1, 2, 3, 6, 7 ou 8</span><span class="sxs-lookup"><span data-stu-id="4d3ce-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="4d3ce-116">Um hífen</span><span class="sxs-lookup"><span data-stu-id="4d3ce-116">A hyphen</span></span>
- <span data-ttu-id="4d3ce-117">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-117">Four digits</span></span>
- <span data-ttu-id="4d3ce-118">Um hífen</span><span class="sxs-lookup"><span data-stu-id="4d3ce-118">A hyphen</span></span>
- <span data-ttu-id="4d3ce-119">Um dígito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-119">A digit</span></span>

<span data-ttu-id="4d3ce-120">Não formatado: 9 dígitos consecutivos começando com 0, 1, 2, 3, 6, 7 ou 8</span><span class="sxs-lookup"><span data-stu-id="4d3ce-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="4d3ce-121">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-121">Checksum</span></span>

<span data-ttu-id="4d3ce-122">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-123">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-123">Definition</span></span>

<span data-ttu-id="4d3ce-124">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-125">A função Func_aba_routing localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-126">Uma palavra-chave de Keyword_ABA_Routing for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="4d3ce-127">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-127">Keywords</span></span>

#### <a name="keyword_aba_routing"></a><span data-ttu-id="4d3ce-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="4d3ce-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="4d3ce-129">aba</span><span class="sxs-lookup"><span data-stu-id="4d3ce-129">aba</span></span>
- <span data-ttu-id="4d3ce-130">aba #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-130">aba #</span></span>
- <span data-ttu-id="4d3ce-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-131">aba routing #</span></span>
- <span data-ttu-id="4d3ce-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-132">aba routing number</span></span>
- <span data-ttu-id="4d3ce-133">aba #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-133">aba#</span></span>
- <span data-ttu-id="4d3ce-134">abarouting #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-134">abarouting#</span></span>
- <span data-ttu-id="4d3ce-135">aba number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-135">aba number</span></span>
- <span data-ttu-id="4d3ce-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="4d3ce-136">abaroutingnumber</span></span>
- <span data-ttu-id="4d3ce-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-137">american bank association routing #</span></span>
- <span data-ttu-id="4d3ce-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-138">american bank association routing number</span></span>
- <span data-ttu-id="4d3ce-139">americanbankassociationrouting #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="4d3ce-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="4d3ce-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="4d3ce-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-141">bank routing number</span></span>
- <span data-ttu-id="4d3ce-142">bankrouting #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-142">bankrouting#</span></span>
- <span data-ttu-id="4d3ce-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="4d3ce-143">bankroutingnumber</span></span>
- <span data-ttu-id="4d3ce-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-144">routing transit number</span></span>
- <span data-ttu-id="4d3ce-145">RTN</span><span class="sxs-lookup"><span data-stu-id="4d3ce-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="4d3ce-146">Número de Identidade Nacional (DNI) da Argentina</span><span class="sxs-lookup"><span data-stu-id="4d3ce-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-147">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-147">Format</span></span>

<span data-ttu-id="4d3ce-148">Oito dígitos separados por pontos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-149">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-149">Pattern</span></span>

<span data-ttu-id="4d3ce-150">Oito dígitos:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-150">Eight digits:</span></span>
- <span data-ttu-id="4d3ce-151">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-151">Two digits</span></span>
- <span data-ttu-id="4d3ce-152">Um ponto </span><span class="sxs-lookup"><span data-stu-id="4d3ce-152">A period</span></span>
- <span data-ttu-id="4d3ce-153">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-153">Three digits</span></span>
- <span data-ttu-id="4d3ce-154">Um ponto </span><span class="sxs-lookup"><span data-stu-id="4d3ce-154">A period</span></span>
- <span data-ttu-id="4d3ce-155">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-156">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-156">Checksum</span></span>

<span data-ttu-id="4d3ce-157">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-158">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-158">Definition</span></span>

<span data-ttu-id="4d3ce-159">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-160">A expressão regular Regex_argentina_national_id localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-161">Uma palavra-chave de Keyword_argentina_national_id for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-162">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-162">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="4d3ce-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="4d3ce-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="4d3ce-164">Número de Identidade Nacional da Argentina</span><span class="sxs-lookup"><span data-stu-id="4d3ce-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="4d3ce-165">Identidade</span><span class="sxs-lookup"><span data-stu-id="4d3ce-165">Identity</span></span> 
- <span data-ttu-id="4d3ce-166">Identificar cartão de identidade nacional</span><span class="sxs-lookup"><span data-stu-id="4d3ce-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="4d3ce-167">DNI</span><span class="sxs-lookup"><span data-stu-id="4d3ce-167">DNI</span></span> 
- <span data-ttu-id="4d3ce-168">Registro Nacional de pessoas da NIC</span><span class="sxs-lookup"><span data-stu-id="4d3ce-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="4d3ce-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="4d3ce-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="4d3ce-170">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="4d3ce-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="4d3ce-171">Identidad</span><span class="sxs-lookup"><span data-stu-id="4d3ce-171">Identidad</span></span> 
- <span data-ttu-id="4d3ce-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="4d3ce-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="4d3ce-173">Número de conta de banco da Austrália</span><span class="sxs-lookup"><span data-stu-id="4d3ce-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-174">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-174">Format</span></span>

<span data-ttu-id="4d3ce-175">6 a 10 dígitos com ou sem um número BSB</span><span class="sxs-lookup"><span data-stu-id="4d3ce-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-176">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-176">Pattern</span></span>

<span data-ttu-id="4d3ce-177">Número de conta é 6 de 10 dígitos.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="4d3ce-178">Número BSB da Austrália:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="4d3ce-179">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-179">Three digits</span></span> 
- <span data-ttu-id="4d3ce-180">Um hífen</span><span class="sxs-lookup"><span data-stu-id="4d3ce-180">A hyphen</span></span> 
- <span data-ttu-id="4d3ce-181">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-182">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-182">Checksum</span></span>

<span data-ttu-id="4d3ce-183">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-184">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-184">Definition</span></span>

<span data-ttu-id="4d3ce-185">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-186">A expressão regular Regex_australia_bank_account_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="4d3ce-187">Uma palavra-chave de Keyword_australia_bank_account_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="4d3ce-188">A expressão regular Regex_australia_bank_account_number_bsb localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="4d3ce-189">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-190">A expressão regular Regex_australia_bank_account_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="4d3ce-191">Uma palavra-chave de Keyword_australia_bank_account_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-192">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-192">Keywords</span></span>

#### <a name="keyword_australia_bank_account_number"></a><span data-ttu-id="4d3ce-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="4d3ce-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="4d3ce-194">swift bank code</span></span>
- <span data-ttu-id="4d3ce-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="4d3ce-195">correspondent bank</span></span>
- <span data-ttu-id="4d3ce-196">base currency</span><span class="sxs-lookup"><span data-stu-id="4d3ce-196">base currency</span></span>
- <span data-ttu-id="4d3ce-197">usa account</span><span class="sxs-lookup"><span data-stu-id="4d3ce-197">usa account</span></span>
- <span data-ttu-id="4d3ce-198">holder address</span><span class="sxs-lookup"><span data-stu-id="4d3ce-198">holder address</span></span>
- <span data-ttu-id="4d3ce-199">bank address</span><span class="sxs-lookup"><span data-stu-id="4d3ce-199">bank address</span></span>
- <span data-ttu-id="4d3ce-200">information account</span><span class="sxs-lookup"><span data-stu-id="4d3ce-200">information account</span></span>
- <span data-ttu-id="4d3ce-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="4d3ce-201">fund transfers</span></span>
- <span data-ttu-id="4d3ce-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="4d3ce-202">bank charges</span></span>
- <span data-ttu-id="4d3ce-203">bank details</span><span class="sxs-lookup"><span data-stu-id="4d3ce-203">bank details</span></span>
- <span data-ttu-id="4d3ce-204">banking information</span><span class="sxs-lookup"><span data-stu-id="4d3ce-204">banking information</span></span>
- <span data-ttu-id="4d3ce-205">full names</span><span class="sxs-lookup"><span data-stu-id="4d3ce-205">full names</span></span>
- <span data-ttu-id="4d3ce-206">iaea</span><span class="sxs-lookup"><span data-stu-id="4d3ce-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="4d3ce-207">Número de carteira de motorista da Austrália</span><span class="sxs-lookup"><span data-stu-id="4d3ce-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-208">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-208">Format</span></span>

<span data-ttu-id="4d3ce-209">Nove letras e dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-210">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-210">Pattern</span></span>

<span data-ttu-id="4d3ce-211">Nove letras e dígitos:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="4d3ce-212">Dois dígitos ou letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="4d3ce-213">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-213">Two digits</span></span> 
- <span data-ttu-id="4d3ce-214">Cinco dígitos ou letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="4d3ce-215">OU</span><span class="sxs-lookup"><span data-stu-id="4d3ce-215">OR</span></span>

- <span data-ttu-id="4d3ce-216">1 a 2 letras opcionais (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="4d3ce-217">4 a 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-217">4-9 digits</span></span>

<span data-ttu-id="4d3ce-218">OU</span><span class="sxs-lookup"><span data-stu-id="4d3ce-218">OR</span></span>

- <span data-ttu-id="4d3ce-219">Nove dígitos ou letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-220">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-220">Checksum</span></span>

<span data-ttu-id="4d3ce-221">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-222">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-222">Definition</span></span>

<span data-ttu-id="4d3ce-223">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-224">A expressão regular Regex_australia_drivers_license_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-225">Uma palavra-chave de Keyword_australia_drivers_license_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="4d3ce-226">Nenhuma palavra-chave de Keyword_australia_drivers_license_number_exclusions for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-227">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-227">Keywords</span></span>

#### <a name="keyword_australia_drivers_license_number"></a><span data-ttu-id="4d3ce-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="4d3ce-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="4d3ce-229">international driving permits</span></span>
- <span data-ttu-id="4d3ce-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="4d3ce-230">australian automobile association</span></span>
- <span data-ttu-id="4d3ce-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="4d3ce-231">international driving permit</span></span>
- <span data-ttu-id="4d3ce-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-232">DriverLicence</span></span>
- <span data-ttu-id="4d3ce-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="4d3ce-233">DriverLicences</span></span>
- <span data-ttu-id="4d3ce-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="4d3ce-234">Driver Lic</span></span>
- <span data-ttu-id="4d3ce-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-235">Driver Licence</span></span>
- <span data-ttu-id="4d3ce-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="4d3ce-236">Driver Licences</span></span>
- <span data-ttu-id="4d3ce-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="4d3ce-237">DriversLic</span></span>
- <span data-ttu-id="4d3ce-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-238">DriversLicence</span></span>
- <span data-ttu-id="4d3ce-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="4d3ce-239">DriversLicences</span></span>
- <span data-ttu-id="4d3ce-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="4d3ce-240">Drivers Lic</span></span>
- <span data-ttu-id="4d3ce-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="4d3ce-241">Drivers Lics</span></span>
- <span data-ttu-id="4d3ce-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-242">Drivers Licence</span></span>
- <span data-ttu-id="4d3ce-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="4d3ce-243">Drivers Licences</span></span>
- <span data-ttu-id="4d3ce-244">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="4d3ce-244">Driver'Lic</span></span>
- <span data-ttu-id="4d3ce-245">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="4d3ce-245">Driver'Lics</span></span>
- <span data-ttu-id="4d3ce-246">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-246">Driver'Licence</span></span>
- <span data-ttu-id="4d3ce-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="4d3ce-247">Driver'Licences</span></span>
- <span data-ttu-id="4d3ce-248">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="4d3ce-248">Driver' Lic</span></span>
- <span data-ttu-id="4d3ce-249">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="4d3ce-249">Driver' Lics</span></span>
- <span data-ttu-id="4d3ce-250">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-250">Driver' Licence</span></span>
- <span data-ttu-id="4d3ce-251">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="4d3ce-251">Driver' Licences</span></span>
- <span data-ttu-id="4d3ce-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="4d3ce-252">Driver'sLic</span></span>
- <span data-ttu-id="4d3ce-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="4d3ce-253">Driver'sLics</span></span>
- <span data-ttu-id="4d3ce-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-254">Driver'sLicence</span></span>
- <span data-ttu-id="4d3ce-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="4d3ce-255">Driver'sLicences</span></span>
- <span data-ttu-id="4d3ce-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="4d3ce-256">Driver's Lic</span></span>
- <span data-ttu-id="4d3ce-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="4d3ce-257">Driver's Lics</span></span>
- <span data-ttu-id="4d3ce-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-258">Driver's Licence</span></span>
- <span data-ttu-id="4d3ce-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="4d3ce-259">Driver's Licences</span></span>
- <span data-ttu-id="4d3ce-260">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-260">DriverLic#</span></span>
- <span data-ttu-id="4d3ce-261">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-261">DriverLics#</span></span>
- <span data-ttu-id="4d3ce-262">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-262">DriverLicence#</span></span>
- <span data-ttu-id="4d3ce-263">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-263">DriverLicences#</span></span>
- <span data-ttu-id="4d3ce-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-264">Driver Lic#</span></span>
- <span data-ttu-id="4d3ce-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-265">Driver Lics#</span></span>
- <span data-ttu-id="4d3ce-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-266">Driver Licence#</span></span>
- <span data-ttu-id="4d3ce-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-267">Driver Licences#</span></span>
- <span data-ttu-id="4d3ce-268">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-268">DriversLic#</span></span>
- <span data-ttu-id="4d3ce-269">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-269">DriversLics#</span></span>
- <span data-ttu-id="4d3ce-270">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-270">DriversLicence#</span></span>
- <span data-ttu-id="4d3ce-271">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-271">DriversLicences#</span></span>
- <span data-ttu-id="4d3ce-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-272">Drivers Lic#</span></span>
- <span data-ttu-id="4d3ce-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-273">Drivers Lics#</span></span>
- <span data-ttu-id="4d3ce-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-274">Drivers Licence#</span></span>
- <span data-ttu-id="4d3ce-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-275">Drivers Licences#</span></span>
- <span data-ttu-id="4d3ce-276">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-276">Driver'Lic#</span></span>
- <span data-ttu-id="4d3ce-277">Driver'Lics #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-277">Driver'Lics#</span></span>
- <span data-ttu-id="4d3ce-278">Driver'Licence #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-278">Driver'Licence#</span></span>
- <span data-ttu-id="4d3ce-279">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-279">Driver'Licences#</span></span>
- <span data-ttu-id="4d3ce-280">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-280">Driver' Lic#</span></span>
- <span data-ttu-id="4d3ce-281">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-281">Driver' Lics#</span></span>
- <span data-ttu-id="4d3ce-282">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-282">Driver' Licence#</span></span>
- <span data-ttu-id="4d3ce-283">Driver'Licences#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-283">Driver' Licences#</span></span>
- <span data-ttu-id="4d3ce-284">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-284">Driver'sLic#</span></span>
- <span data-ttu-id="4d3ce-285">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-285">Driver'sLics#</span></span>
- <span data-ttu-id="4d3ce-286">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-286">Driver'sLicence#</span></span>
- <span data-ttu-id="4d3ce-287">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-287">Driver'sLicences#</span></span>
- <span data-ttu-id="4d3ce-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-288">Driver's Lic#</span></span>
- <span data-ttu-id="4d3ce-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-289">Driver's Lics#</span></span>
- <span data-ttu-id="4d3ce-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-290">Driver's Licence#</span></span>
- <span data-ttu-id="4d3ce-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-291">Driver's Licences#</span></span> 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a><span data-ttu-id="4d3ce-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="4d3ce-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="4d3ce-293">AAA</span><span class="sxs-lookup"><span data-stu-id="4d3ce-293">aaa</span></span>
- <span data-ttu-id="4d3ce-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="4d3ce-294">DriverLicense</span></span>
- <span data-ttu-id="4d3ce-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-295">DriverLicenses</span></span>
- <span data-ttu-id="4d3ce-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="4d3ce-296">Driver License</span></span>
- <span data-ttu-id="4d3ce-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-297">Driver Licenses</span></span>
- <span data-ttu-id="4d3ce-298">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="4d3ce-298">DriversLicense</span></span>
- <span data-ttu-id="4d3ce-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-299">DriversLicenses</span></span>
- <span data-ttu-id="4d3ce-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="4d3ce-300">Drivers License</span></span>
- <span data-ttu-id="4d3ce-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-301">Drivers Licenses</span></span>
- <span data-ttu-id="4d3ce-302">Driver'License</span><span class="sxs-lookup"><span data-stu-id="4d3ce-302">Driver'License</span></span>
- <span data-ttu-id="4d3ce-303">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-303">Driver'Licenses</span></span>
- <span data-ttu-id="4d3ce-304">Driver'License</span><span class="sxs-lookup"><span data-stu-id="4d3ce-304">Driver' License</span></span>
- <span data-ttu-id="4d3ce-305">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-305">Driver' Licenses</span></span>
- <span data-ttu-id="4d3ce-306">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="4d3ce-306">Driver'sLicense</span></span>
- <span data-ttu-id="4d3ce-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-307">Driver'sLicenses</span></span>
- <span data-ttu-id="4d3ce-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="4d3ce-308">Driver's License</span></span>
- <span data-ttu-id="4d3ce-309">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-309">Driver's Licenses</span></span>
- <span data-ttu-id="4d3ce-310">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-310">DriverLicense#</span></span>
- <span data-ttu-id="4d3ce-311">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-311">DriverLicenses#</span></span>
- <span data-ttu-id="4d3ce-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-312">Driver License#</span></span>
- <span data-ttu-id="4d3ce-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-313">Driver Licenses#</span></span>
- <span data-ttu-id="4d3ce-314">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-314">DriversLicense#</span></span>
- <span data-ttu-id="4d3ce-315">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-315">DriversLicenses#</span></span>
- <span data-ttu-id="4d3ce-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-316">Drivers License#</span></span>
- <span data-ttu-id="4d3ce-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-317">Drivers Licenses#</span></span>
- <span data-ttu-id="4d3ce-318">Driver'License #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-318">Driver'License#</span></span>
- <span data-ttu-id="4d3ce-319">Driver'Licenses #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-319">Driver'Licenses#</span></span>
- <span data-ttu-id="4d3ce-320">Driver'License#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-320">Driver' License#</span></span>
- <span data-ttu-id="4d3ce-321">Driver'Licenses#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-321">Driver' Licenses#</span></span>
- <span data-ttu-id="4d3ce-322">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-322">Driver'sLicense#</span></span>
- <span data-ttu-id="4d3ce-323">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="4d3ce-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-324">Driver's License#</span></span>
- <span data-ttu-id="4d3ce-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="4d3ce-326">Número de conta médica da Austrália</span><span class="sxs-lookup"><span data-stu-id="4d3ce-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-327">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-327">Format</span></span>

<span data-ttu-id="4d3ce-328">10 a 11 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-329">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-329">Pattern</span></span>

<span data-ttu-id="4d3ce-330">10 a 11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-330">10-11 digits:</span></span>
- <span data-ttu-id="4d3ce-331">Primeiro dígito está no intervalo de 2 a 6</span><span class="sxs-lookup"><span data-stu-id="4d3ce-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="4d3ce-332">O nono dígito é um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="4d3ce-333">O décimo dígito é o dígito do problema</span><span class="sxs-lookup"><span data-stu-id="4d3ce-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="4d3ce-334">O décimo primeiro dígito (opcional) é o número individual</span><span class="sxs-lookup"><span data-stu-id="4d3ce-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-335">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-335">Checksum</span></span>

<span data-ttu-id="4d3ce-336">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-337">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-337">Definition</span></span>

<span data-ttu-id="4d3ce-338">Uma política de DLP tem 95% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-339">A função Func_australian_medical_account_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-340">Uma palavra-chave de Keyword_Australia_Medical_Account_Number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="4d3ce-341">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-341">The checksum passes.</span></span>

<span data-ttu-id="4d3ce-342">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-343">A função Func_australian_medical_account_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-344">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-344">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-345">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-345">Keywords</span></span>

#### <a name="keyword_australia_medical_account_number"></a><span data-ttu-id="4d3ce-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="4d3ce-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="4d3ce-347">bank account details</span></span>
- <span data-ttu-id="4d3ce-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="4d3ce-348">medicare payments</span></span>
- <span data-ttu-id="4d3ce-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="4d3ce-349">mortgage account</span></span>
- <span data-ttu-id="4d3ce-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="4d3ce-350">bank payments</span></span>
- <span data-ttu-id="4d3ce-351">information branch</span><span class="sxs-lookup"><span data-stu-id="4d3ce-351">information branch</span></span>
- <span data-ttu-id="4d3ce-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="4d3ce-352">credit card loan</span></span>
- <span data-ttu-id="4d3ce-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="4d3ce-353">department of human services</span></span>
- <span data-ttu-id="4d3ce-354">local service</span><span class="sxs-lookup"><span data-stu-id="4d3ce-354">local service</span></span>
- <span data-ttu-id="4d3ce-355">medicare</span><span class="sxs-lookup"><span data-stu-id="4d3ce-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="4d3ce-356">Número de passaporte da Austrália</span><span class="sxs-lookup"><span data-stu-id="4d3ce-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-357">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-357">Format</span></span>

<span data-ttu-id="4d3ce-358">Uma letra seguida por sete dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-359">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-359">Pattern</span></span>

<span data-ttu-id="4d3ce-360">Uma letra (não diferencia maiúsculas de minúsculas) seguida de sete dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-361">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-361">Checksum</span></span>

<span data-ttu-id="4d3ce-362">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-363">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-363">Definition</span></span>

<span data-ttu-id="4d3ce-364">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-365">A expressão regular Regex_australia_passport_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-366">Uma palavra-chave de Keyword_passport ou Keyword_australia_passport_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-367">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-367">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="4d3ce-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="4d3ce-368">Keyword_passport</span></span>

- <span data-ttu-id="4d3ce-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-369">Passport Number</span></span>
- <span data-ttu-id="4d3ce-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="4d3ce-370">Passport No</span></span>
- <span data-ttu-id="4d3ce-371">Passport #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-371">Passport #</span></span>
- <span data-ttu-id="4d3ce-372">Passaport #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-372">Passport#</span></span>
- <span data-ttu-id="4d3ce-373">Passportid</span><span class="sxs-lookup"><span data-stu-id="4d3ce-373">PassportID</span></span>
- <span data-ttu-id="4d3ce-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="4d3ce-374">Passportno</span></span>
- <span data-ttu-id="4d3ce-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="4d3ce-375">passportnumber</span></span>
- <span data-ttu-id="4d3ce-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="4d3ce-376">パスポート</span></span>
- <span data-ttu-id="4d3ce-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="4d3ce-377">パスポート番号</span></span>
- <span data-ttu-id="4d3ce-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="4d3ce-378">パスポートのNum</span></span>
- <span data-ttu-id="4d3ce-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="4d3ce-379">パスポート ＃</span></span> 
- <span data-ttu-id="4d3ce-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="4d3ce-380">Numéro de passeport</span></span>
- <span data-ttu-id="4d3ce-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="4d3ce-381">Passeport n °</span></span>
- <span data-ttu-id="4d3ce-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="4d3ce-382">Passeport Non</span></span>
- <span data-ttu-id="4d3ce-383">Passeport #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-383">Passeport #</span></span>
- <span data-ttu-id="4d3ce-384">Passeport #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-384">Passeport#</span></span>
- <span data-ttu-id="4d3ce-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="4d3ce-385">PasseportNon</span></span>
- <span data-ttu-id="4d3ce-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="4d3ce-386">Passeportn °</span></span>

#### <a name="keyword_australia_passport_number"></a><span data-ttu-id="4d3ce-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="4d3ce-388">Passaport</span><span class="sxs-lookup"><span data-stu-id="4d3ce-388">passport</span></span>
- <span data-ttu-id="4d3ce-389">passport details</span><span class="sxs-lookup"><span data-stu-id="4d3ce-389">passport details</span></span>
- <span data-ttu-id="4d3ce-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="4d3ce-390">immigration and citizenship</span></span>
- <span data-ttu-id="4d3ce-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="4d3ce-391">commonwealth of australia</span></span>
- <span data-ttu-id="4d3ce-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="4d3ce-392">department of immigration</span></span>
- <span data-ttu-id="4d3ce-393">residential address</span><span class="sxs-lookup"><span data-stu-id="4d3ce-393">residential address</span></span>
- <span data-ttu-id="4d3ce-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="4d3ce-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="4d3ce-395">cartões</span><span class="sxs-lookup"><span data-stu-id="4d3ce-395">visa</span></span>
- <span data-ttu-id="4d3ce-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-396">national identity card</span></span>
- <span data-ttu-id="4d3ce-397">passport number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-397">passport number</span></span>
- <span data-ttu-id="4d3ce-398">travel document</span><span class="sxs-lookup"><span data-stu-id="4d3ce-398">travel document</span></span>
- <span data-ttu-id="4d3ce-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="4d3ce-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="4d3ce-400">Número de imposto de renda da Austrália</span><span class="sxs-lookup"><span data-stu-id="4d3ce-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-401">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-401">Format</span></span>

<span data-ttu-id="4d3ce-402">8 a 9 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-403">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-403">Pattern</span></span>

<span data-ttu-id="4d3ce-404">8 a 9 dígitos normalmente apresentados com espaços, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="4d3ce-405">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-405">Three digits</span></span> 
- <span data-ttu-id="4d3ce-406">Um espaço opcional</span><span class="sxs-lookup"><span data-stu-id="4d3ce-406">An optional space</span></span> 
- <span data-ttu-id="4d3ce-407">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-407">Three digits</span></span> 
- <span data-ttu-id="4d3ce-408">Um espaço opcional</span><span class="sxs-lookup"><span data-stu-id="4d3ce-408">An optional space</span></span> 
- <span data-ttu-id="4d3ce-409">2 a 3 dígitos em que o último dígito é um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-410">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-410">Checksum</span></span>

<span data-ttu-id="4d3ce-411">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-412">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-412">Definition</span></span>

<span data-ttu-id="4d3ce-413">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-414">A função Func_australian_tax_file_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-415">Nenhuma palavra-chave de Keyword_Australia_Tax_File_Number ou Keyword_number_exclusions for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="4d3ce-416">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-416">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-417">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-417">Keywords</span></span>

#### <a name="keyword_australia_tax_file_number"></a><span data-ttu-id="4d3ce-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="4d3ce-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-419">australian business number</span></span>
- <span data-ttu-id="4d3ce-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="4d3ce-420">marginal tax rate</span></span>
- <span data-ttu-id="4d3ce-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="4d3ce-421">medicare levy</span></span>
- <span data-ttu-id="4d3ce-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-422">portfolio number</span></span>
- <span data-ttu-id="4d3ce-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="4d3ce-423">service veterans</span></span>
- <span data-ttu-id="4d3ce-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="4d3ce-424">withholding tax</span></span>
- <span data-ttu-id="4d3ce-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="4d3ce-425">individual tax return</span></span>
- <span data-ttu-id="4d3ce-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-426">tax file number</span></span>

#### <a name="keyword_number_exclusions"></a><span data-ttu-id="4d3ce-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="4d3ce-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="4d3ce-428">00000000</span><span class="sxs-lookup"><span data-stu-id="4d3ce-428">00000000</span></span>
- <span data-ttu-id="4d3ce-429">11111111</span><span class="sxs-lookup"><span data-stu-id="4d3ce-429">11111111</span></span>
- <span data-ttu-id="4d3ce-430">22222222</span><span class="sxs-lookup"><span data-stu-id="4d3ce-430">22222222</span></span>
- <span data-ttu-id="4d3ce-431">33333333</span><span class="sxs-lookup"><span data-stu-id="4d3ce-431">33333333</span></span>
- <span data-ttu-id="4d3ce-432">44444444</span><span class="sxs-lookup"><span data-stu-id="4d3ce-432">44444444</span></span>
- <span data-ttu-id="4d3ce-433">55555555</span><span class="sxs-lookup"><span data-stu-id="4d3ce-433">55555555</span></span>
- <span data-ttu-id="4d3ce-434">66666666</span><span class="sxs-lookup"><span data-stu-id="4d3ce-434">66666666</span></span>
- <span data-ttu-id="4d3ce-435">77777777</span><span class="sxs-lookup"><span data-stu-id="4d3ce-435">77777777</span></span>
- <span data-ttu-id="4d3ce-436">88888888</span><span class="sxs-lookup"><span data-stu-id="4d3ce-436">88888888</span></span>
- <span data-ttu-id="4d3ce-437">99999999</span><span class="sxs-lookup"><span data-stu-id="4d3ce-437">99999999</span></span>
- <span data-ttu-id="4d3ce-438">000000000</span><span class="sxs-lookup"><span data-stu-id="4d3ce-438">000000000</span></span>
- <span data-ttu-id="4d3ce-439">111111111</span><span class="sxs-lookup"><span data-stu-id="4d3ce-439">111111111</span></span>
- <span data-ttu-id="4d3ce-440">222222222</span><span class="sxs-lookup"><span data-stu-id="4d3ce-440">222222222</span></span>
- <span data-ttu-id="4d3ce-441">333333333</span><span class="sxs-lookup"><span data-stu-id="4d3ce-441">333333333</span></span>
- <span data-ttu-id="4d3ce-442">444444444</span><span class="sxs-lookup"><span data-stu-id="4d3ce-442">444444444</span></span>
- <span data-ttu-id="4d3ce-443">555555555</span><span class="sxs-lookup"><span data-stu-id="4d3ce-443">555555555</span></span>
- <span data-ttu-id="4d3ce-444">666666666</span><span class="sxs-lookup"><span data-stu-id="4d3ce-444">666666666</span></span>
- <span data-ttu-id="4d3ce-445">777777777</span><span class="sxs-lookup"><span data-stu-id="4d3ce-445">777777777</span></span>
- <span data-ttu-id="4d3ce-446">888888888</span><span class="sxs-lookup"><span data-stu-id="4d3ce-446">888888888</span></span>
- <span data-ttu-id="4d3ce-447">999999999</span><span class="sxs-lookup"><span data-stu-id="4d3ce-447">999999999</span></span>
- <span data-ttu-id="4d3ce-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="4d3ce-448">0000000000</span></span>
- <span data-ttu-id="4d3ce-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="4d3ce-449">1111111111</span></span>
- <span data-ttu-id="4d3ce-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="4d3ce-450">2222222222</span></span>
- <span data-ttu-id="4d3ce-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="4d3ce-451">3333333333</span></span>
- <span data-ttu-id="4d3ce-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="4d3ce-452">4444444444</span></span>
- <span data-ttu-id="4d3ce-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="4d3ce-453">5555555555</span></span>
- <span data-ttu-id="4d3ce-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="4d3ce-454">6666666666</span></span>
- <span data-ttu-id="4d3ce-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="4d3ce-455">7777777777</span></span>
- <span data-ttu-id="4d3ce-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="4d3ce-456">8888888888</span></span>
- <span data-ttu-id="4d3ce-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="4d3ce-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="4d3ce-458">Chave de autenticação do Azure DocumentDB</span><span class="sxs-lookup"><span data-stu-id="4d3ce-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-459">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-459">Format</span></span>

<span data-ttu-id="4d3ce-460">A cadeia de caracteres "DocumentDb" seguida dos caracteres e cadeias de caracteres descritos no padrão abaixo.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-461">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-461">Pattern</span></span>

- <span data-ttu-id="4d3ce-462">A cadeia de caracteres "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="4d3ce-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="4d3ce-463">Qualquer combinação entre 3-200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços</span><span class="sxs-lookup"><span data-stu-id="4d3ce-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="4d3ce-464">Um símbolo maior que (>), um sinal de igual (=), uma aspa (") ou um apóstrofo (')</span><span class="sxs-lookup"><span data-stu-id="4d3ce-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="4d3ce-465">Qualquer combinação de 86 letras minúsculas ou maiúsculas, dígitos, barra de avanço (/) ou sinal de adição (+)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="4d3ce-466">Dois sinais de igual (=)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-467">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-467">Checksum</span></span>

<span data-ttu-id="4d3ce-468">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-469">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-469">Definition</span></span>

<span data-ttu-id="4d3ce-470">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-471">A expressão regular CEP_Regex_AzureDocumentDBAuthKey localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-472">A expressão regular CEP_CommonExampleKeywords não **localiza o** conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-473">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-473">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="4d3ce-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="4d3ce-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="4d3ce-475">(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="4d3ce-476">contoso</span><span class="sxs-lookup"><span data-stu-id="4d3ce-476">contoso</span></span>
- <span data-ttu-id="4d3ce-477">fabrikam</span><span class="sxs-lookup"><span data-stu-id="4d3ce-477">fabrikam</span></span>
- <span data-ttu-id="4d3ce-478">Northwind</span><span class="sxs-lookup"><span data-stu-id="4d3ce-478">northwind</span></span>
- <span data-ttu-id="4d3ce-479">área restrita</span><span class="sxs-lookup"><span data-stu-id="4d3ce-479">sandbox</span></span>
- <span data-ttu-id="4d3ce-480">onebox</span><span class="sxs-lookup"><span data-stu-id="4d3ce-480">onebox</span></span>
- <span data-ttu-id="4d3ce-481">localhost</span><span class="sxs-lookup"><span data-stu-id="4d3ce-481">localhost</span></span>
- <span data-ttu-id="4d3ce-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="4d3ce-482">127.0.0.1</span></span>
- <span data-ttu-id="4d3ce-483">testacs.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="4d3ce-484">suplementos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-484">com</span></span>
- <span data-ttu-id="4d3ce-485">s-int.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="4d3ce-486">Netlogon</span><span class="sxs-lookup"><span data-stu-id="4d3ce-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="4d3ce-487">Cadeia de conexão de banco de dados Azure IAAS e cadeia de conexão do Azure SQL</span><span class="sxs-lookup"><span data-stu-id="4d3ce-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-488">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-488">Format</span></span>

<span data-ttu-id="4d3ce-489">A cadeia de caracteres "Server", "Server" ou "Data Source" seguida dos caracteres e cadeias de caracteres descritos no padrão abaixo, incluindo a cadeia de caracteres "cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="4d3ce-490">com "ou" cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="4d3ce-491">NET "ou" Database. Windows.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="4d3ce-492">NET ", e a cadeia de caracteres" password "ou" password "ou" pwd ".</span><span class="sxs-lookup"><span data-stu-id="4d3ce-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-493">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-493">Pattern</span></span>

- <span data-ttu-id="4d3ce-494">A cadeia de caracteres "Server", "Server" ou "Data Source"</span><span class="sxs-lookup"><span data-stu-id="4d3ce-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="4d3ce-495">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="4d3ce-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="4d3ce-496">Um sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-496">An equal sign (=)</span></span>
- <span data-ttu-id="4d3ce-497">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="4d3ce-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="4d3ce-498">Qualquer combinação entre 1-200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços</span><span class="sxs-lookup"><span data-stu-id="4d3ce-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="4d3ce-499">A cadeia de caracteres "cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="4d3ce-500">com "," cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="4d3ce-501">NET "ou" Database. Windows.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="4d3ce-502">Netlogon</span><span class="sxs-lookup"><span data-stu-id="4d3ce-502">net"</span></span>
- <span data-ttu-id="4d3ce-503">Qualquer combinação entre 1-300 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços</span><span class="sxs-lookup"><span data-stu-id="4d3ce-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="4d3ce-504">A cadeia de caracteres "password", "password" ou "pwd"</span><span class="sxs-lookup"><span data-stu-id="4d3ce-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="4d3ce-505">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="4d3ce-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="4d3ce-506">Um sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-506">An equal sign (=)</span></span>
- <span data-ttu-id="4d3ce-507">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="4d3ce-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="4d3ce-508">Um ou mais caracteres que não são ponto-e-vírgula (;), aspas (") ou apóstrofo (')</span><span class="sxs-lookup"><span data-stu-id="4d3ce-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="4d3ce-509">Um ponto e vírgula (;), aspas (") ou apóstrofo (')</span><span class="sxs-lookup"><span data-stu-id="4d3ce-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-510">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-510">Checksum</span></span>

<span data-ttu-id="4d3ce-511">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-512">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-512">Definition</span></span>

<span data-ttu-id="4d3ce-513">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-514">A expressão regular CEP_Regex_AzureConnectionString localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-515">A expressão regular CEP_CommonExampleKeywords não **localiza o** conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-516">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-516">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="4d3ce-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="4d3ce-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="4d3ce-518">(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="4d3ce-519">contoso</span><span class="sxs-lookup"><span data-stu-id="4d3ce-519">contoso</span></span>
- <span data-ttu-id="4d3ce-520">fabrikam</span><span class="sxs-lookup"><span data-stu-id="4d3ce-520">fabrikam</span></span>
- <span data-ttu-id="4d3ce-521">Northwind</span><span class="sxs-lookup"><span data-stu-id="4d3ce-521">northwind</span></span>
- <span data-ttu-id="4d3ce-522">área restrita</span><span class="sxs-lookup"><span data-stu-id="4d3ce-522">sandbox</span></span>
- <span data-ttu-id="4d3ce-523">onebox</span><span class="sxs-lookup"><span data-stu-id="4d3ce-523">onebox</span></span>
- <span data-ttu-id="4d3ce-524">localhost</span><span class="sxs-lookup"><span data-stu-id="4d3ce-524">localhost</span></span>
- <span data-ttu-id="4d3ce-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="4d3ce-525">127.0.0.1</span></span>
- <span data-ttu-id="4d3ce-526">testacs.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="4d3ce-527">suplementos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-527">com</span></span>
- <span data-ttu-id="4d3ce-528">s-int.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="4d3ce-529">Netlogon</span><span class="sxs-lookup"><span data-stu-id="4d3ce-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="4d3ce-530">Cadeia de conexão IoT do Azure</span><span class="sxs-lookup"><span data-stu-id="4d3ce-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-531">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-531">Format</span></span>

<span data-ttu-id="4d3ce-532">A cadeia de caracteres "HostName" seguida dos caracteres e cadeias de caracteres descritos no padrão abaixo, incluindo as cadeias de caracteres "Azure-Devices.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="4d3ce-533">NET "e" SharedAccessKey ".</span><span class="sxs-lookup"><span data-stu-id="4d3ce-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-534">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-534">Pattern</span></span>

- <span data-ttu-id="4d3ce-535">A cadeia de caracteres "HostName"</span><span class="sxs-lookup"><span data-stu-id="4d3ce-535">The string "HostName"</span></span>
- <span data-ttu-id="4d3ce-536">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="4d3ce-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="4d3ce-537">Um sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-537">An equal sign (=)</span></span>
- <span data-ttu-id="4d3ce-538">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="4d3ce-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="4d3ce-539">Qualquer combinação entre 1-200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços</span><span class="sxs-lookup"><span data-stu-id="4d3ce-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="4d3ce-540">A cadeia de caracteres "Azure-Devices.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="4d3ce-541">Netlogon</span><span class="sxs-lookup"><span data-stu-id="4d3ce-541">net"</span></span>
- <span data-ttu-id="4d3ce-542">Qualquer combinação entre 1-200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços</span><span class="sxs-lookup"><span data-stu-id="4d3ce-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="4d3ce-543">A cadeia de caracteres "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="4d3ce-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="4d3ce-544">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="4d3ce-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="4d3ce-545">Um sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-545">An equal sign (=)</span></span>
- <span data-ttu-id="4d3ce-546">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="4d3ce-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="4d3ce-547">Qualquer combinação de 43 letras minúsculas ou maiúsculas, dígitos, barra de avanço (/) ou sinal de adição (+)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="4d3ce-548">Um sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-549">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-549">Checksum</span></span>

<span data-ttu-id="4d3ce-550">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-551">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-551">Definition</span></span>

<span data-ttu-id="4d3ce-552">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-553">A expressão regular CEP_Regex_AzureIoTConnectionString localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-554">A expressão regular CEP_CommonExampleKeywords não **localiza o** conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-555">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-555">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="4d3ce-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="4d3ce-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="4d3ce-557">(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="4d3ce-558">contoso</span><span class="sxs-lookup"><span data-stu-id="4d3ce-558">contoso</span></span>
- <span data-ttu-id="4d3ce-559">fabrikam</span><span class="sxs-lookup"><span data-stu-id="4d3ce-559">fabrikam</span></span>
- <span data-ttu-id="4d3ce-560">Northwind</span><span class="sxs-lookup"><span data-stu-id="4d3ce-560">northwind</span></span>
- <span data-ttu-id="4d3ce-561">área restrita</span><span class="sxs-lookup"><span data-stu-id="4d3ce-561">sandbox</span></span>
- <span data-ttu-id="4d3ce-562">onebox</span><span class="sxs-lookup"><span data-stu-id="4d3ce-562">onebox</span></span>
- <span data-ttu-id="4d3ce-563">localhost</span><span class="sxs-lookup"><span data-stu-id="4d3ce-563">localhost</span></span>
- <span data-ttu-id="4d3ce-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="4d3ce-564">127.0.0.1</span></span>
- <span data-ttu-id="4d3ce-565">testacs.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="4d3ce-566">suplementos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-566">com</span></span>
- <span data-ttu-id="4d3ce-567">s-int.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="4d3ce-568">Netlogon</span><span class="sxs-lookup"><span data-stu-id="4d3ce-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="4d3ce-569">Senha de configuração de publicação do Azure</span><span class="sxs-lookup"><span data-stu-id="4d3ce-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-570">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-570">Format</span></span>

<span data-ttu-id="4d3ce-571">A cadeia de caracteres "userpwd =" seguida de uma cadeia de caracteres alfanumérica.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-572">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-572">Pattern</span></span>

- <span data-ttu-id="4d3ce-573">A cadeia de caracteres "userpwd ="</span><span class="sxs-lookup"><span data-stu-id="4d3ce-573">The string "userpwd="</span></span>
- <span data-ttu-id="4d3ce-574">Qualquer combinação de letras minúsculas ou dígitos de 60</span><span class="sxs-lookup"><span data-stu-id="4d3ce-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="4d3ce-575">Aspas (")</span><span class="sxs-lookup"><span data-stu-id="4d3ce-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-576">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-576">Checksum</span></span>

<span data-ttu-id="4d3ce-577">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-578">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-578">Definition</span></span>

<span data-ttu-id="4d3ce-579">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-580">A expressão regular CEP_Regex_AzurePublishSettingPasswords localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-581">A expressão regular CEP_CommonExampleKeywords não **localiza o** conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


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

### <a name="keywords"></a><span data-ttu-id="4d3ce-582">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-582">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="4d3ce-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="4d3ce-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="4d3ce-584">(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="4d3ce-585">contoso</span><span class="sxs-lookup"><span data-stu-id="4d3ce-585">contoso</span></span>
- <span data-ttu-id="4d3ce-586">fabrikam</span><span class="sxs-lookup"><span data-stu-id="4d3ce-586">fabrikam</span></span>
- <span data-ttu-id="4d3ce-587">Northwind</span><span class="sxs-lookup"><span data-stu-id="4d3ce-587">northwind</span></span>
- <span data-ttu-id="4d3ce-588">área restrita</span><span class="sxs-lookup"><span data-stu-id="4d3ce-588">sandbox</span></span>
- <span data-ttu-id="4d3ce-589">onebox</span><span class="sxs-lookup"><span data-stu-id="4d3ce-589">onebox</span></span>
- <span data-ttu-id="4d3ce-590">localhost</span><span class="sxs-lookup"><span data-stu-id="4d3ce-590">localhost</span></span>
- <span data-ttu-id="4d3ce-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="4d3ce-591">127.0.0.1</span></span>
- <span data-ttu-id="4d3ce-592">testacs.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="4d3ce-593">suplementos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-593">com</span></span>
- <span data-ttu-id="4d3ce-594">s-int.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="4d3ce-595">Netlogon</span><span class="sxs-lookup"><span data-stu-id="4d3ce-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="4d3ce-596">Cadeia de conexão do cache do Redis do Azure</span><span class="sxs-lookup"><span data-stu-id="4d3ce-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-597">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-597">Format</span></span>

<span data-ttu-id="4d3ce-598">A cadeia de caracteres "Redis. cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="4d3ce-599">NET "seguido pelos caracteres e cadeias de caracteres descritos no padrão abaixo, incluindo a cadeia de caracteres" password "ou" pwd ".</span><span class="sxs-lookup"><span data-stu-id="4d3ce-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-600">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-600">Pattern</span></span>

- <span data-ttu-id="4d3ce-601">A cadeia de caracteres "Redis. cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="4d3ce-602">Netlogon</span><span class="sxs-lookup"><span data-stu-id="4d3ce-602">net"</span></span>
- <span data-ttu-id="4d3ce-603">Qualquer combinação entre 1-200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços</span><span class="sxs-lookup"><span data-stu-id="4d3ce-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="4d3ce-604">A cadeia de caracteres "password" ou "pwd"</span><span class="sxs-lookup"><span data-stu-id="4d3ce-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="4d3ce-605">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="4d3ce-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="4d3ce-606">Um sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-606">An equal sign (=)</span></span>
- <span data-ttu-id="4d3ce-607">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="4d3ce-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="4d3ce-608">Qualquer combinação de 43 caracteres que sejam letras minúsculas ou maiúsculas, dígitos, barra de avanço (/) ou sinal de adição (+)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="4d3ce-609">Um sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-610">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-610">Checksum</span></span>

<span data-ttu-id="4d3ce-611">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-612">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-612">Definition</span></span>

<span data-ttu-id="4d3ce-613">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-614">A expressão regular CEP_Regex_AzureRedisCacheConnectionString localiza o conteúdo que corresponde ao padrão..</span><span class="sxs-lookup"><span data-stu-id="4d3ce-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="4d3ce-615">A expressão regular CEP_CommonExampleKeywords não **localiza o** conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-616">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-616">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="4d3ce-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="4d3ce-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="4d3ce-618">(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="4d3ce-619">contoso</span><span class="sxs-lookup"><span data-stu-id="4d3ce-619">contoso</span></span>
- <span data-ttu-id="4d3ce-620">fabrikam</span><span class="sxs-lookup"><span data-stu-id="4d3ce-620">fabrikam</span></span>
- <span data-ttu-id="4d3ce-621">Northwind</span><span class="sxs-lookup"><span data-stu-id="4d3ce-621">northwind</span></span>
- <span data-ttu-id="4d3ce-622">área restrita</span><span class="sxs-lookup"><span data-stu-id="4d3ce-622">sandbox</span></span>
- <span data-ttu-id="4d3ce-623">onebox</span><span class="sxs-lookup"><span data-stu-id="4d3ce-623">onebox</span></span>
- <span data-ttu-id="4d3ce-624">localhost</span><span class="sxs-lookup"><span data-stu-id="4d3ce-624">localhost</span></span>
- <span data-ttu-id="4d3ce-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="4d3ce-625">127.0.0.1</span></span>
- <span data-ttu-id="4d3ce-626">testacs.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="4d3ce-627">suplementos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-627">com</span></span>
- <span data-ttu-id="4d3ce-628">s-int.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="4d3ce-629">Netlogon</span><span class="sxs-lookup"><span data-stu-id="4d3ce-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="4d3ce-630">SAS do Azure</span><span class="sxs-lookup"><span data-stu-id="4d3ce-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-631">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-631">Format</span></span>

<span data-ttu-id="4d3ce-632">A cadeia de caracteres "SIG" seguida pelos caracteres e cadeias de caracteres descritos no padrão abaixo.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-633">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-633">Pattern</span></span>

- <span data-ttu-id="4d3ce-634">A cadeia de caracteres "SIG"</span><span class="sxs-lookup"><span data-stu-id="4d3ce-634">The string "sig"</span></span>
- <span data-ttu-id="4d3ce-635">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="4d3ce-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="4d3ce-636">Um sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-636">An equal sign (=)</span></span>
- <span data-ttu-id="4d3ce-637">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="4d3ce-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="4d3ce-638">Qualquer combinação entre 43-53 caracteres que são letras minúsculas ou maiúsculas, dígitos ou o sinal de porcentagem (%)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="4d3ce-639">A cadeia de caracteres "% 3D"</span><span class="sxs-lookup"><span data-stu-id="4d3ce-639">The string "%3d"</span></span>
- <span data-ttu-id="4d3ce-640">Qualquer caractere que não seja letras minúsculas, dígitos ou sinal de porcentagem (%)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-641">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-641">Checksum</span></span>

<span data-ttu-id="4d3ce-642">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-643">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-643">Definition</span></span>

<span data-ttu-id="4d3ce-644">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-645">A expressão regular CEP_Regex_AzureSAS localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="4d3ce-646">Cadeia de conexão do barramento de serviço do Azure</span><span class="sxs-lookup"><span data-stu-id="4d3ce-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-647">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-647">Format</span></span>

<span data-ttu-id="4d3ce-648">A cadeia de caracteres "EndPoint" seguida dos caracteres e cadeias de caracteres descritos no padrão abaixo, incluindo as cadeias de caracteres "ServiceBus. Windows.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="4d3ce-649">NET "e" SharedAccesKey ".</span><span class="sxs-lookup"><span data-stu-id="4d3ce-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-650">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-650">Pattern</span></span>

- <span data-ttu-id="4d3ce-651">A cadeia de caracteres "EndPoint"</span><span class="sxs-lookup"><span data-stu-id="4d3ce-651">The string "EndPoint"</span></span>
- <span data-ttu-id="4d3ce-652">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="4d3ce-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="4d3ce-653">Um sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-653">An equal sign (=)</span></span>
- <span data-ttu-id="4d3ce-654">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="4d3ce-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="4d3ce-655">Qualquer combinação entre 1-200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços</span><span class="sxs-lookup"><span data-stu-id="4d3ce-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="4d3ce-656">A cadeia de caracteres "ServiceBus. Windows.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="4d3ce-657">Netlogon</span><span class="sxs-lookup"><span data-stu-id="4d3ce-657">net"</span></span>
- <span data-ttu-id="4d3ce-658">Qualquer combinação entre 1-200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços</span><span class="sxs-lookup"><span data-stu-id="4d3ce-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="4d3ce-659">A cadeia de caracteres "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="4d3ce-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="4d3ce-660">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="4d3ce-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="4d3ce-661">Um sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-661">An equal sign (=)</span></span>
- <span data-ttu-id="4d3ce-662">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="4d3ce-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="4d3ce-663">Qualquer combinação de 43 caracteres que sejam letras minúsculas ou maiúsculas, dígitos, barra de avanço (/) ou sinal de adição (+)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="4d3ce-664">Um sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-665">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-665">Checksum</span></span>

<span data-ttu-id="4d3ce-666">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-667">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-667">Definition</span></span>

<span data-ttu-id="4d3ce-668">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-669">A expressão regular CEP_Regex_AzureServiceBusConnectionString localiza o conteúdo que corresponde ao padrão..</span><span class="sxs-lookup"><span data-stu-id="4d3ce-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="4d3ce-670">A expressão regular CEP_CommonExampleKeywords não **localiza o** conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-671">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-671">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="4d3ce-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="4d3ce-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="4d3ce-673">(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="4d3ce-674">contoso</span><span class="sxs-lookup"><span data-stu-id="4d3ce-674">contoso</span></span>
- <span data-ttu-id="4d3ce-675">fabrikam</span><span class="sxs-lookup"><span data-stu-id="4d3ce-675">fabrikam</span></span>
- <span data-ttu-id="4d3ce-676">Northwind</span><span class="sxs-lookup"><span data-stu-id="4d3ce-676">northwind</span></span>
- <span data-ttu-id="4d3ce-677">área restrita</span><span class="sxs-lookup"><span data-stu-id="4d3ce-677">sandbox</span></span>
- <span data-ttu-id="4d3ce-678">onebox</span><span class="sxs-lookup"><span data-stu-id="4d3ce-678">onebox</span></span>
- <span data-ttu-id="4d3ce-679">localhost</span><span class="sxs-lookup"><span data-stu-id="4d3ce-679">localhost</span></span>
- <span data-ttu-id="4d3ce-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="4d3ce-680">127.0.0.1</span></span>
- <span data-ttu-id="4d3ce-681">testacs.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="4d3ce-682">suplementos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-682">com</span></span>
- <span data-ttu-id="4d3ce-683">s-int.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="4d3ce-684">Netlogon</span><span class="sxs-lookup"><span data-stu-id="4d3ce-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="4d3ce-685">Chave da conta de armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="4d3ce-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-686">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-686">Format</span></span>

<span data-ttu-id="4d3ce-687">A cadeia de caracteres "DefaultEndpointsProtocol" seguida dos caracteres e cadeias de caracteres descritos no padrão abaixo, incluindo a cadeia de caracteres "AccountKey".</span><span class="sxs-lookup"><span data-stu-id="4d3ce-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-688">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-688">Pattern</span></span>

- <span data-ttu-id="4d3ce-689">A cadeia de caracteres "DefaultEndpointsProtocol"</span><span class="sxs-lookup"><span data-stu-id="4d3ce-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="4d3ce-690">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="4d3ce-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="4d3ce-691">Um sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-691">An equal sign (=)</span></span>
- <span data-ttu-id="4d3ce-692">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="4d3ce-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="4d3ce-693">Qualquer combinação entre 1-200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços</span><span class="sxs-lookup"><span data-stu-id="4d3ce-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="4d3ce-694">A cadeia de caracteres "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="4d3ce-694">The string "AccountKey"</span></span>
- <span data-ttu-id="4d3ce-695">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="4d3ce-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="4d3ce-696">Um sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-696">An equal sign (=)</span></span>
- <span data-ttu-id="4d3ce-697">0-2 caracteres de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="4d3ce-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="4d3ce-698">Qualquer combinação de 86 caracteres que sejam letras minúsculas ou maiúsculas, dígitos, barra de avanço (/) ou sinal de adição (+)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="4d3ce-699">Dois sinais de igual (=)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-700">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-700">Checksum</span></span>

<span data-ttu-id="4d3ce-701">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-702">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-702">Definition</span></span>

<span data-ttu-id="4d3ce-703">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-704">A expressão regular CEP_Regex_AzureStorageAccountKey localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-705">A expressão regular CEP_AzureEmulatorStorageAccountFilter não **localiza o** conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-706">A expressão regular CEP_CommonExampleKeywords não **localiza o** conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-707">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-707">Keywords</span></span>

#### <a name="cep_azureemulatorstorageaccountfilter"></a><span data-ttu-id="4d3ce-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="4d3ce-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="4d3ce-709">(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="4d3ce-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="4d3ce-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="4d3ce-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="4d3ce-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="4d3ce-712">(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="4d3ce-713">contoso</span><span class="sxs-lookup"><span data-stu-id="4d3ce-713">contoso</span></span>
- <span data-ttu-id="4d3ce-714">fabrikam</span><span class="sxs-lookup"><span data-stu-id="4d3ce-714">fabrikam</span></span>
- <span data-ttu-id="4d3ce-715">Northwind</span><span class="sxs-lookup"><span data-stu-id="4d3ce-715">northwind</span></span>
- <span data-ttu-id="4d3ce-716">área restrita</span><span class="sxs-lookup"><span data-stu-id="4d3ce-716">sandbox</span></span>
- <span data-ttu-id="4d3ce-717">onebox</span><span class="sxs-lookup"><span data-stu-id="4d3ce-717">onebox</span></span>
- <span data-ttu-id="4d3ce-718">localhost</span><span class="sxs-lookup"><span data-stu-id="4d3ce-718">localhost</span></span>
- <span data-ttu-id="4d3ce-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="4d3ce-719">127.0.0.1</span></span>
- <span data-ttu-id="4d3ce-720">testacs.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="4d3ce-721">suplementos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-721">com</span></span>
- <span data-ttu-id="4d3ce-722">s-int.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="4d3ce-723">Netlogon</span><span class="sxs-lookup"><span data-stu-id="4d3ce-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="4d3ce-724">Chave da conta de armazenamento do Azure (genérico)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-725">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-725">Format</span></span>

<span data-ttu-id="4d3ce-726">Qualquer combinação de letras maiúsculas ou minúsculas de 86, dígitos, barra (/) ou sinal de adição (+), precedida ou seguida dos caracteres descritos no padrão abaixo.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-727">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-727">Pattern</span></span>

- <span data-ttu-id="4d3ce-728">0-1 do símbolo maior que (>), apóstrofo ('), sinal de igual (=), aspas (") ou sinal de número (#)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="4d3ce-729">Qualquer combinação de 86 caracteres que sejam letras minúsculas ou maiúsculas, dígitos, a barra (/) ou sinal de adição (+)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="4d3ce-730">Dois sinais de igual (=)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="4d3ce-731">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-731">Checksum</span></span>

<span data-ttu-id="4d3ce-732">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-733">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-733">Definition</span></span>

<span data-ttu-id="4d3ce-734">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-735">A expressão regular CEP_Regex_AzureStorageAccountKeyGeneric localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="4d3ce-736">Número Nacional da Bélgica</span><span class="sxs-lookup"><span data-stu-id="4d3ce-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-737">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-737">Format</span></span>

<span data-ttu-id="4d3ce-738">11 dígitos mais delimitadores</span><span class="sxs-lookup"><span data-stu-id="4d3ce-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-739">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-739">Pattern</span></span>

<span data-ttu-id="4d3ce-740">11 dígitos mais delimitadores.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="4d3ce-741">Seis dígitos e dois pontos no formato AA.MM.DD da data de nascimento </span><span class="sxs-lookup"><span data-stu-id="4d3ce-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="4d3ce-742">Um hífen</span><span class="sxs-lookup"><span data-stu-id="4d3ce-742">A hyphen</span></span> 
- <span data-ttu-id="4d3ce-743">Três dígitos sequenciais (ímpares para homens, pares para mulheres) </span><span class="sxs-lookup"><span data-stu-id="4d3ce-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="4d3ce-744">Um ponto</span><span class="sxs-lookup"><span data-stu-id="4d3ce-744">A period</span></span> 
- <span data-ttu-id="4d3ce-745">Dois dígitos que são um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-746">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-746">Checksum</span></span>

<span data-ttu-id="4d3ce-747">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-748">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-748">Definition</span></span>

<span data-ttu-id="4d3ce-749">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-750">A função Func_belgium_national_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-751">Uma palavra-chave de Keyword_belgium_national_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="4d3ce-752">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-752">The checksum passes.</span></span>

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-753">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-753">Keywords</span></span>

#### <a name="keyword_belgium_national_number"></a><span data-ttu-id="4d3ce-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="4d3ce-755">Identidade</span><span class="sxs-lookup"><span data-stu-id="4d3ce-755">Identity</span></span>
- <span data-ttu-id="4d3ce-756">Registro</span><span class="sxs-lookup"><span data-stu-id="4d3ce-756">Registration</span></span>
- <span data-ttu-id="4d3ce-757">Identificador</span><span class="sxs-lookup"><span data-stu-id="4d3ce-757">Identification</span></span> 
- <span data-ttu-id="4d3ce-758">ID</span><span class="sxs-lookup"><span data-stu-id="4d3ce-758">ID</span></span> 
- <span data-ttu-id="4d3ce-759">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="4d3ce-759">Identiteitskaart</span></span>
- <span data-ttu-id="4d3ce-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-760">Registratie nummer</span></span> 
- <span data-ttu-id="4d3ce-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-761">Identificatie nummer</span></span> 
- <span data-ttu-id="4d3ce-762">Identiteit</span><span class="sxs-lookup"><span data-stu-id="4d3ce-762">Identiteit</span></span>
- <span data-ttu-id="4d3ce-763">Registratie</span><span class="sxs-lookup"><span data-stu-id="4d3ce-763">Registratie</span></span>
- <span data-ttu-id="4d3ce-764">Identificatie</span><span class="sxs-lookup"><span data-stu-id="4d3ce-764">Identificatie</span></span> 
- <span data-ttu-id="4d3ce-765">Carte d’identité</span><span class="sxs-lookup"><span data-stu-id="4d3ce-765">Carte d’identité</span></span> 
- <span data-ttu-id="4d3ce-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="4d3ce-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="4d3ce-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="4d3ce-767">numéro d'identification</span></span>
- <span data-ttu-id="4d3ce-768">identité</span><span class="sxs-lookup"><span data-stu-id="4d3ce-768">identité</span></span> 
- <span data-ttu-id="4d3ce-769">inscription</span><span class="sxs-lookup"><span data-stu-id="4d3ce-769">inscription</span></span> 
- <span data-ttu-id="4d3ce-770">Identifikation</span><span class="sxs-lookup"><span data-stu-id="4d3ce-770">Identifikation</span></span>
- <span data-ttu-id="4d3ce-771">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="4d3ce-771">Identifizierung</span></span>
- <span data-ttu-id="4d3ce-772">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-772">Identifikationsnummer</span></span>
- <span data-ttu-id="4d3ce-773">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="4d3ce-773">Personalausweis</span></span>
- <span data-ttu-id="4d3ce-774">Registrierung</span><span class="sxs-lookup"><span data-stu-id="4d3ce-774">Registrierung</span></span>
- <span data-ttu-id="4d3ce-775">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="4d3ce-776">Número de CPF do Brasil</span><span class="sxs-lookup"><span data-stu-id="4d3ce-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-777">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-777">Format</span></span>

<span data-ttu-id="4d3ce-778">11 dígitos que incluem um dígito de verificação e podem ser formatados ou não formatados</span><span class="sxs-lookup"><span data-stu-id="4d3ce-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-779">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-779">Pattern</span></span>

<span data-ttu-id="4d3ce-780">Binário</span><span class="sxs-lookup"><span data-stu-id="4d3ce-780">Formatted:</span></span>
- <span data-ttu-id="4d3ce-781">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-781">Three digits</span></span> 
- <span data-ttu-id="4d3ce-782">Um ponto </span><span class="sxs-lookup"><span data-stu-id="4d3ce-782">A period</span></span> 
- <span data-ttu-id="4d3ce-783">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-783">Three digits</span></span> 
- <span data-ttu-id="4d3ce-784">Um ponto </span><span class="sxs-lookup"><span data-stu-id="4d3ce-784">A period</span></span> 
- <span data-ttu-id="4d3ce-785">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-785">Three digits</span></span> 
- <span data-ttu-id="4d3ce-786">Um hífen</span><span class="sxs-lookup"><span data-stu-id="4d3ce-786">A hyphen</span></span> 
- <span data-ttu-id="4d3ce-787">Dois dígitos que são dígitos de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-787">Two digits which are check digits</span></span>

<span data-ttu-id="4d3ce-788">Não formatado</span><span class="sxs-lookup"><span data-stu-id="4d3ce-788">Unformatted:</span></span>
- <span data-ttu-id="4d3ce-789">11 dígitos em que os dois últimos dígitos são dígitos de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-790">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-790">Checksum</span></span>

<span data-ttu-id="4d3ce-791">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-792">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-792">Definition</span></span>

<span data-ttu-id="4d3ce-793">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-794">A função Func_brazil_cpf localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-795">Uma palavra-chave de Keyword_brazil_cpf for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="4d3ce-796">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-796">The checksum passes.</span></span>

<span data-ttu-id="4d3ce-797">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-798">A função Func_brazil_cpf localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-799">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-799">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-800">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-800">Keywords</span></span>

#### <a name="keyword_brazil_cpf"></a><span data-ttu-id="4d3ce-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="4d3ce-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="4d3ce-802">CPF</span><span class="sxs-lookup"><span data-stu-id="4d3ce-802">CPF</span></span>
- <span data-ttu-id="4d3ce-803">Identificador</span><span class="sxs-lookup"><span data-stu-id="4d3ce-803">Identification</span></span>
- <span data-ttu-id="4d3ce-804">Registro</span><span class="sxs-lookup"><span data-stu-id="4d3ce-804">Registration</span></span>
- <span data-ttu-id="4d3ce-805">Participação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-805">Revenue</span></span>
- <span data-ttu-id="4d3ce-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="4d3ce-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="4d3ce-807">Imposto</span><span class="sxs-lookup"><span data-stu-id="4d3ce-807">Imposto</span></span> 
- <span data-ttu-id="4d3ce-808">Identificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-808">Identificação</span></span> 
- <span data-ttu-id="4d3ce-809">Inscrição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-809">Inscrição</span></span> 
- <span data-ttu-id="4d3ce-810">Receita</span><span class="sxs-lookup"><span data-stu-id="4d3ce-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="4d3ce-811">Número de Pessoa Jurídica (CNPJ) do Brasil</span><span class="sxs-lookup"><span data-stu-id="4d3ce-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-812">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-812">Format</span></span>

<span data-ttu-id="4d3ce-813">14 dígitos que incluem um número de registro, o número da ramificação e dígitos de verificação, além de delimitadores de seleção</span><span class="sxs-lookup"><span data-stu-id="4d3ce-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-814">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-814">Pattern</span></span>
<span data-ttu-id="4d3ce-815">14 dígitos mais delimitadores:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="4d3ce-816">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-816">Two digits</span></span> 
- <span data-ttu-id="4d3ce-817">Um ponto </span><span class="sxs-lookup"><span data-stu-id="4d3ce-817">A period</span></span> 
- <span data-ttu-id="4d3ce-818">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-818">Three digits</span></span> 
- <span data-ttu-id="4d3ce-819">Um ponto </span><span class="sxs-lookup"><span data-stu-id="4d3ce-819">A period</span></span> 
- <span data-ttu-id="4d3ce-820">Três dígitos (esses primeiros oito dígitos são o número de registro) </span><span class="sxs-lookup"><span data-stu-id="4d3ce-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="4d3ce-821">Uma barra</span><span class="sxs-lookup"><span data-stu-id="4d3ce-821">A forward slash</span></span> 
- <span data-ttu-id="4d3ce-822">Número da ramificação de quatro dígitos </span><span class="sxs-lookup"><span data-stu-id="4d3ce-822">Four-digit branch number</span></span> 
- <span data-ttu-id="4d3ce-823">Um hífen</span><span class="sxs-lookup"><span data-stu-id="4d3ce-823">A hyphen</span></span> 
- <span data-ttu-id="4d3ce-824">Dois dígitos que são dígitos de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-825">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-825">Checksum</span></span>

<span data-ttu-id="4d3ce-826">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-827">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-827">Definition</span></span>

<span data-ttu-id="4d3ce-828">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-829">A função Func_brazil_cnpj localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-830">Uma palavra-chave de Keyword_brazil_cnpj for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="4d3ce-831">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-831">The checksum passes.</span></span>

<span data-ttu-id="4d3ce-832">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-833">A função Func_brazil_cnpj localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-834">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-834">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-835">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-835">Keywords</span></span>

#### <a name="keyword_brazil_cnpj"></a><span data-ttu-id="4d3ce-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="4d3ce-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="4d3ce-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="4d3ce-837">CNPJ</span></span> 
- <span data-ttu-id="4d3ce-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="4d3ce-838">CNPJ/MF</span></span> 
- <span data-ttu-id="4d3ce-839">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="4d3ce-839">CNPJ-MF</span></span> 
- <span data-ttu-id="4d3ce-840">Registro Nacional de Pessoas Jurídicas</span><span class="sxs-lookup"><span data-stu-id="4d3ce-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="4d3ce-841">Registro de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="4d3ce-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="4d3ce-842">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="4d3ce-842">Legal entity</span></span> 
- <span data-ttu-id="4d3ce-843">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="4d3ce-843">Legal entities</span></span> 
- <span data-ttu-id="4d3ce-844">Status do Registro</span><span class="sxs-lookup"><span data-stu-id="4d3ce-844">Registration Status</span></span> 
- <span data-ttu-id="4d3ce-845">Negócio</span><span class="sxs-lookup"><span data-stu-id="4d3ce-845">Business</span></span> 
- <span data-ttu-id="4d3ce-846">Empresa</span><span class="sxs-lookup"><span data-stu-id="4d3ce-846">Company</span></span>
- <span data-ttu-id="4d3ce-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="4d3ce-847">CNPJ</span></span> 
- <span data-ttu-id="4d3ce-848">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="4d3ce-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="4d3ce-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="4d3ce-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="4d3ce-850">CGC</span><span class="sxs-lookup"><span data-stu-id="4d3ce-850">CGC</span></span> 
- <span data-ttu-id="4d3ce-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="4d3ce-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="4d3ce-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="4d3ce-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="4d3ce-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="4d3ce-853">Situação cadastral</span></span> 
- <span data-ttu-id="4d3ce-854">Inscrição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-854">Inscrição</span></span> 
- <span data-ttu-id="4d3ce-855">Empresa</span><span class="sxs-lookup"><span data-stu-id="4d3ce-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="4d3ce-856">	Cartão de Identidade Nacional (RG) do Brasil</span><span class="sxs-lookup"><span data-stu-id="4d3ce-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-857">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-857">Format</span></span>

<span data-ttu-id="4d3ce-858">Registro geral (formato antigo): nove dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="4d3ce-859">Registro de identidade (RIC) (novo formato): 11 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-860">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-860">Pattern</span></span>

<span data-ttu-id="4d3ce-861">Registro Geral (formato antigo):</span><span class="sxs-lookup"><span data-stu-id="4d3ce-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="4d3ce-862">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-862">Two digits</span></span> 
- <span data-ttu-id="4d3ce-863">Um ponto </span><span class="sxs-lookup"><span data-stu-id="4d3ce-863">A period</span></span> 
- <span data-ttu-id="4d3ce-864">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-864">Three digits</span></span> 
- <span data-ttu-id="4d3ce-865">Um ponto </span><span class="sxs-lookup"><span data-stu-id="4d3ce-865">A period</span></span> 
- <span data-ttu-id="4d3ce-866">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-866">Three digits</span></span> 
- <span data-ttu-id="4d3ce-867">Um hífen</span><span class="sxs-lookup"><span data-stu-id="4d3ce-867">A hyphen</span></span> 
- <span data-ttu-id="4d3ce-868">Um dígito que é um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-868">One digit which is a check digit</span></span>

<span data-ttu-id="4d3ce-869">Registro de identidade (RIC) (novo formato):</span><span class="sxs-lookup"><span data-stu-id="4d3ce-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="4d3ce-870">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-870">10 digits</span></span> 
- <span data-ttu-id="4d3ce-871">Um hífen</span><span class="sxs-lookup"><span data-stu-id="4d3ce-871">A hyphen</span></span> 
- <span data-ttu-id="4d3ce-872">Um dígito que é um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-873">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-873">Checksum</span></span>

<span data-ttu-id="4d3ce-874">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-875">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-875">Definition</span></span>

<span data-ttu-id="4d3ce-876">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-877">A função Func_brazil_rg localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-878">Uma palavra-chave de Keyword_brazil_rg for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="4d3ce-879">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-879">The checksum passes.</span></span>

<span data-ttu-id="4d3ce-880">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-881">A função Func_brazil_rg localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-882">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-882">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-883">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-883">Keywords</span></span>

#### <a name="keyword_brazil_rg"></a><span data-ttu-id="4d3ce-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="4d3ce-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="4d3ce-885">Cédula de identidade ID nacional número de registro registro de identidade registro de geral RG (esta palavra-chave diferencia maiúsculas de minúsculas) RIC (essa palavra-chave diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="4d3ce-886">Número de conta bancária do Canadá</span><span class="sxs-lookup"><span data-stu-id="4d3ce-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-887">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-887">Format</span></span>

<span data-ttu-id="4d3ce-888">Sete ou doze dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-889">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-889">Pattern</span></span>

<span data-ttu-id="4d3ce-890">Um número de conta bancária do Canadá tem sete ou doze dígitos.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="4d3ce-891">Um número de trânsito de conta bancária do Canadá tem:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="4d3ce-892">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-892">Five digits</span></span> 
- <span data-ttu-id="4d3ce-893">Um hífen</span><span class="sxs-lookup"><span data-stu-id="4d3ce-893">A hyphen</span></span> 
- <span data-ttu-id="4d3ce-894">Três dígitos ou</span><span class="sxs-lookup"><span data-stu-id="4d3ce-894">Three digits OR</span></span>
- <span data-ttu-id="4d3ce-895">Um zero "0"</span><span class="sxs-lookup"><span data-stu-id="4d3ce-895">A zero "0"</span></span> 
- <span data-ttu-id="4d3ce-896">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-897">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-897">Checksum</span></span>

<span data-ttu-id="4d3ce-898">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-899">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-899">Definition</span></span>

<span data-ttu-id="4d3ce-900">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-901">A expressão regular Regex_canada_bank_account_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-902">Uma palavra-chave de Keyword_canada_bank_account_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="4d3ce-903">A expressão regular Regex_canada_bank_account_transit_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="4d3ce-904">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-905">A expressão regular Regex_canada_bank_account_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-906">Uma palavra-chave de Keyword_canada_bank_account_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-907">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-907">Keywords</span></span>

#### <a name="keyword_canada_bank_account_number"></a><span data-ttu-id="4d3ce-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="4d3ce-909">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="4d3ce-909">canada savings bonds</span></span>
- <span data-ttu-id="4d3ce-910">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="4d3ce-910">canada revenue agency</span></span>
- <span data-ttu-id="4d3ce-911">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="4d3ce-911">canadian financial institution</span></span>
- <span data-ttu-id="4d3ce-912">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="4d3ce-912">direct deposit form</span></span>
- <span data-ttu-id="4d3ce-913">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="4d3ce-913">canadian citizen</span></span>
- <span data-ttu-id="4d3ce-914">legal representative</span><span class="sxs-lookup"><span data-stu-id="4d3ce-914">legal representative</span></span>
- <span data-ttu-id="4d3ce-915">notary public</span><span class="sxs-lookup"><span data-stu-id="4d3ce-915">notary public</span></span>
- <span data-ttu-id="4d3ce-916">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="4d3ce-916">commissioner for oaths</span></span>
- <span data-ttu-id="4d3ce-917">child care benefit</span><span class="sxs-lookup"><span data-stu-id="4d3ce-917">child care benefit</span></span>
- <span data-ttu-id="4d3ce-918">universal child care</span><span class="sxs-lookup"><span data-stu-id="4d3ce-918">universal child care</span></span>
- <span data-ttu-id="4d3ce-919">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="4d3ce-919">canada child tax benefit</span></span>
- <span data-ttu-id="4d3ce-920">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="4d3ce-920">income tax benefit</span></span>
- <span data-ttu-id="4d3ce-921">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="4d3ce-921">harmonized sales tax</span></span>
- <span data-ttu-id="4d3ce-922">social insurance number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-922">social insurance number</span></span>
- <span data-ttu-id="4d3ce-923">income tax refund</span><span class="sxs-lookup"><span data-stu-id="4d3ce-923">income tax refund</span></span>
- <span data-ttu-id="4d3ce-924">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="4d3ce-924">child tax benefit</span></span>
- <span data-ttu-id="4d3ce-925">territorial payments</span><span class="sxs-lookup"><span data-stu-id="4d3ce-925">territorial payments</span></span>
- <span data-ttu-id="4d3ce-926">institution number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-926">institution number</span></span>
- <span data-ttu-id="4d3ce-927">deposit request</span><span class="sxs-lookup"><span data-stu-id="4d3ce-927">deposit request</span></span>
- <span data-ttu-id="4d3ce-928">banking information</span><span class="sxs-lookup"><span data-stu-id="4d3ce-928">banking information</span></span>
- <span data-ttu-id="4d3ce-929">direct deposit</span><span class="sxs-lookup"><span data-stu-id="4d3ce-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="4d3ce-930">Número de carteira de motorista do Canadá</span><span class="sxs-lookup"><span data-stu-id="4d3ce-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-931">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-931">Format</span></span>

<span data-ttu-id="4d3ce-932">Varia por província</span><span class="sxs-lookup"><span data-stu-id="4d3ce-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-933">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-933">Pattern</span></span>

<span data-ttu-id="4d3ce-934">Vários padrões que abrangem Alberta, Columbia Britânica, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Escócia, Ontário, Ilha do Príncipe Eduardo, Quebec e Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="4d3ce-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-935">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-935">Checksum</span></span>

<span data-ttu-id="4d3ce-936">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-937">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-937">Definition</span></span>

<span data-ttu-id="4d3ce-938">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-939">A função Func_[province_name]_drivers_license_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-940">Uma palavra-chave de Keyword_[province_name]_drivers_license_name for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="4d3ce-941">Uma palavra-chave de Keyword_canada_drivers_license for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-942">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-942">Keywords</span></span>

#### <a name="keyword_province_name_drivers_license_name"></a><span data-ttu-id="4d3ce-943">Keyword_ [province_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="4d3ce-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="4d3ce-944">A abreviação da província, por exemplo AB</span><span class="sxs-lookup"><span data-stu-id="4d3ce-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="4d3ce-945">O nome da província, por exemplo, Alberta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-945">The province name, for example Alberta</span></span>

#### <a name="keyword_canada_drivers_license"></a><span data-ttu-id="4d3ce-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="4d3ce-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="4d3ce-947">DISTRIBUIÇÃO</span><span class="sxs-lookup"><span data-stu-id="4d3ce-947">DL</span></span>
- <span data-ttu-id="4d3ce-948">DL</span><span class="sxs-lookup"><span data-stu-id="4d3ce-948">DLS</span></span>
- <span data-ttu-id="4d3ce-949">CDL</span><span class="sxs-lookup"><span data-stu-id="4d3ce-949">CDL</span></span>
- <span data-ttu-id="4d3ce-950">CDLS</span><span class="sxs-lookup"><span data-stu-id="4d3ce-950">CDLS</span></span>
- <span data-ttu-id="4d3ce-951">DriverLic</span><span class="sxs-lookup"><span data-stu-id="4d3ce-951">DriverLic</span></span>
- <span data-ttu-id="4d3ce-952">DriverLics</span><span class="sxs-lookup"><span data-stu-id="4d3ce-952">DriverLics</span></span>
- <span data-ttu-id="4d3ce-953">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="4d3ce-953">DriverLicense</span></span>
- <span data-ttu-id="4d3ce-954">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-954">DriverLicenses</span></span>
- <span data-ttu-id="4d3ce-955">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-955">DriverLicence</span></span>
- <span data-ttu-id="4d3ce-956">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="4d3ce-956">DriverLicences</span></span>
- <span data-ttu-id="4d3ce-957">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="4d3ce-957">Driver Lic</span></span>
- <span data-ttu-id="4d3ce-958">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="4d3ce-958">Driver Lics</span></span>
- <span data-ttu-id="4d3ce-959">Driver License</span><span class="sxs-lookup"><span data-stu-id="4d3ce-959">Driver License</span></span>
- <span data-ttu-id="4d3ce-960">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-960">Driver Licenses</span></span>
- <span data-ttu-id="4d3ce-961">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-961">Driver Licence</span></span>
- <span data-ttu-id="4d3ce-962">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="4d3ce-962">Driver Licences</span></span>
- <span data-ttu-id="4d3ce-963">DriversLic</span><span class="sxs-lookup"><span data-stu-id="4d3ce-963">DriversLic</span></span>
- <span data-ttu-id="4d3ce-964">DriversLics</span><span class="sxs-lookup"><span data-stu-id="4d3ce-964">DriversLics</span></span>
- <span data-ttu-id="4d3ce-965">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-965">DriversLicence</span></span>
- <span data-ttu-id="4d3ce-966">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="4d3ce-966">DriversLicences</span></span>
- <span data-ttu-id="4d3ce-967">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="4d3ce-967">DriversLicense</span></span>
- <span data-ttu-id="4d3ce-968">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-968">DriversLicenses</span></span>
- <span data-ttu-id="4d3ce-969">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="4d3ce-969">Drivers Lic</span></span>
- <span data-ttu-id="4d3ce-970">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="4d3ce-970">Drivers Lics</span></span>
- <span data-ttu-id="4d3ce-971">Drivers License</span><span class="sxs-lookup"><span data-stu-id="4d3ce-971">Drivers License</span></span>
- <span data-ttu-id="4d3ce-972">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-972">Drivers Licenses</span></span>
- <span data-ttu-id="4d3ce-973">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-973">Drivers Licence</span></span>
- <span data-ttu-id="4d3ce-974">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="4d3ce-974">Drivers Licences</span></span>
- <span data-ttu-id="4d3ce-975">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="4d3ce-975">Driver'Lic</span></span>
- <span data-ttu-id="4d3ce-976">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="4d3ce-976">Driver'Lics</span></span>
- <span data-ttu-id="4d3ce-977">Driver'License</span><span class="sxs-lookup"><span data-stu-id="4d3ce-977">Driver'License</span></span>
- <span data-ttu-id="4d3ce-978">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-978">Driver'Licenses</span></span>
- <span data-ttu-id="4d3ce-979">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-979">Driver'Licence</span></span>
- <span data-ttu-id="4d3ce-980">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="4d3ce-980">Driver'Licences</span></span>
- <span data-ttu-id="4d3ce-981">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="4d3ce-981">Driver' Lic</span></span>
- <span data-ttu-id="4d3ce-982">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="4d3ce-982">Driver' Lics</span></span>
- <span data-ttu-id="4d3ce-983">Driver' License</span><span class="sxs-lookup"><span data-stu-id="4d3ce-983">Driver' License</span></span>
- <span data-ttu-id="4d3ce-984">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-984">Driver' Licenses</span></span>
- <span data-ttu-id="4d3ce-985">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-985">Driver' Licence</span></span>
- <span data-ttu-id="4d3ce-986">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="4d3ce-986">Driver' Licences</span></span>
- <span data-ttu-id="4d3ce-987">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="4d3ce-987">Driver'sLic</span></span>
- <span data-ttu-id="4d3ce-988">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="4d3ce-988">Driver'sLics</span></span>
- <span data-ttu-id="4d3ce-989">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="4d3ce-989">Driver'sLicense</span></span>
- <span data-ttu-id="4d3ce-990">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-990">Driver'sLicenses</span></span>
- <span data-ttu-id="4d3ce-991">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-991">Driver'sLicence</span></span>
- <span data-ttu-id="4d3ce-992">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="4d3ce-992">Driver'sLicences</span></span>
- <span data-ttu-id="4d3ce-993">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="4d3ce-993">Driver's Lic</span></span>
- <span data-ttu-id="4d3ce-994">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="4d3ce-994">Driver's Lics</span></span>
- <span data-ttu-id="4d3ce-995">Driver's License</span><span class="sxs-lookup"><span data-stu-id="4d3ce-995">Driver's License</span></span>
- <span data-ttu-id="4d3ce-996">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-996">Driver's Licenses</span></span>
- <span data-ttu-id="4d3ce-997">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-997">Driver's Licence</span></span>
- <span data-ttu-id="4d3ce-998">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="4d3ce-998">Driver's Licences</span></span>
- <span data-ttu-id="4d3ce-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="4d3ce-999">Permis de Conduire</span></span>
- <span data-ttu-id="4d3ce-1000">id</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1000">id</span></span>
- <span data-ttu-id="4d3ce-1001">ids</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1001">ids</span></span>
- <span data-ttu-id="4d3ce-1002">idcard number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1002">idcard number</span></span>
- <span data-ttu-id="4d3ce-1003">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1003">idcard numbers</span></span>
- <span data-ttu-id="4d3ce-1004">idcard #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1004">idcard #</span></span>
- <span data-ttu-id="4d3ce-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1005">idcard #s</span></span>
- <span data-ttu-id="4d3ce-1006">idcard card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1006">idcard card</span></span>
- <span data-ttu-id="4d3ce-1007">idcard cards</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1007">idcard cards</span></span>
- <span data-ttu-id="4d3ce-1008">idcard</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1008">idcard</span></span>
- <span data-ttu-id="4d3ce-1009">identification number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1009">identification number</span></span>
- <span data-ttu-id="4d3ce-1010">identification numbers</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1010">identification numbers</span></span>
- <span data-ttu-id="4d3ce-1011">identification #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1011">identification #</span></span>
- <span data-ttu-id="4d3ce-1012">identification #s</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1012">identification #s</span></span>
- <span data-ttu-id="4d3ce-1013">identification card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1013">identification card</span></span>
- <span data-ttu-id="4d3ce-1014">identification cards</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1014">identification cards</span></span>
- <span data-ttu-id="4d3ce-1015">identificador</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1015">identification</span></span> 
- <span data-ttu-id="4d3ce-1016">DISTRIBUIÇÃO #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1016">DL#</span></span>
- <span data-ttu-id="4d3ce-1017">DL #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1017">DLS#</span></span> 
- <span data-ttu-id="4d3ce-1018">CDL #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1018">CDL#</span></span> 
- <span data-ttu-id="4d3ce-1019">CDLS #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1019">CDLS#</span></span> 
- <span data-ttu-id="4d3ce-1020">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1020">DriverLic#</span></span> 
- <span data-ttu-id="4d3ce-1021">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1021">DriverLics#</span></span> 
- <span data-ttu-id="4d3ce-1022">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1022">DriverLicense#</span></span> 
- <span data-ttu-id="4d3ce-1023">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="4d3ce-1024">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1024">DriverLicence#</span></span> 
- <span data-ttu-id="4d3ce-1025">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1025">DriverLicences#</span></span> 
- <span data-ttu-id="4d3ce-1026">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1026">Driver Lic#</span></span>
- <span data-ttu-id="4d3ce-1027">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1027">Driver Lics#</span></span> 
- <span data-ttu-id="4d3ce-1028">Driver License#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1028">Driver License#</span></span> 
- <span data-ttu-id="4d3ce-1029">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="4d3ce-1030">Driver License#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1030">Driver License#</span></span> 
- <span data-ttu-id="4d3ce-1031">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1031">Driver Licences#</span></span> 
- <span data-ttu-id="4d3ce-1032">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1032">DriversLic#</span></span> 
- <span data-ttu-id="4d3ce-1033">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1033">DriversLics#</span></span> 
- <span data-ttu-id="4d3ce-1034">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1034">DriversLicense#</span></span> 
- <span data-ttu-id="4d3ce-1035">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="4d3ce-1036">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1036">DriversLicence#</span></span> 
- <span data-ttu-id="4d3ce-1037">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1037">DriversLicences#</span></span> 
- <span data-ttu-id="4d3ce-1038">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="4d3ce-1039">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="4d3ce-1040">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1040">Drivers License#</span></span> 
- <span data-ttu-id="4d3ce-1041">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="4d3ce-1042">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="4d3ce-1043">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="4d3ce-1044">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="4d3ce-1045">Driver'Lics #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="4d3ce-1046">Driver'License #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1046">Driver'License#</span></span> 
- <span data-ttu-id="4d3ce-1047">Driver'Licenses #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="4d3ce-1048">Driver'Licence #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="4d3ce-1049">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="4d3ce-1050">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="4d3ce-1051">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="4d3ce-1052">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1052">Driver' License#</span></span> 
- <span data-ttu-id="4d3ce-1053">Driver'Licenses#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="4d3ce-1054">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="4d3ce-1055">Driver'Licences#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="4d3ce-1056">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="4d3ce-1057">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="4d3ce-1058">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="4d3ce-1059">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="4d3ce-1060">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="4d3ce-1061">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="4d3ce-1062">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="4d3ce-1063">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="4d3ce-1064">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1064">Driver's License#</span></span> 
- <span data-ttu-id="4d3ce-1065">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="4d3ce-1066">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="4d3ce-1067">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="4d3ce-1068">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="4d3ce-1069">ID #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1069">id#</span></span> 
- <span data-ttu-id="4d3ce-1070">código #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1070">ids#</span></span> 
- <span data-ttu-id="4d3ce-1071">idcard card#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1071">idcard card#</span></span> 
- <span data-ttu-id="4d3ce-1072">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1072">idcard cards#</span></span> 
- <span data-ttu-id="4d3ce-1073">idcard #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1073">idcard#</span></span> 
- <span data-ttu-id="4d3ce-1074">identification card#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1074">identification card#</span></span> 
- <span data-ttu-id="4d3ce-1075">identification cards#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1075">identification cards#</span></span> 
- <span data-ttu-id="4d3ce-1076">identificador #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="4d3ce-1077">Número de serviço de saúde do Canadá</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-1078">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1078">Format</span></span>

<span data-ttu-id="4d3ce-1079">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-1080">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1080">Pattern</span></span>

<span data-ttu-id="4d3ce-1081">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-1082">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1082">Checksum</span></span>

<span data-ttu-id="4d3ce-1083">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-1084">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1084">Definition</span></span>

<span data-ttu-id="4d3ce-1085">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-1086">A expressão regular Regex_canada_health_service_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-1087">Uma palavra-chave de Keyword_canada_health_service_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-1088">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1088">Keywords</span></span>

#### <a name="keyword_canada_health_service_number"></a><span data-ttu-id="4d3ce-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="4d3ce-1090">personal health number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1090">personal health number</span></span>
- <span data-ttu-id="4d3ce-1091">patient information</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1091">patient information</span></span>
- <span data-ttu-id="4d3ce-1092">health services</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1092">health services</span></span>
- <span data-ttu-id="4d3ce-1093">speciality services</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1093">speciality services</span></span>
- <span data-ttu-id="4d3ce-1094">automobile accident</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1094">automobile accident</span></span>
- <span data-ttu-id="4d3ce-1095">patient hospital</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1095">patient hospital</span></span>
- <span data-ttu-id="4d3ce-1096">psychiatrist</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1096">psychiatrist</span></span>
- <span data-ttu-id="4d3ce-1097">workers compensation</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1097">workers compensation</span></span>
- <span data-ttu-id="4d3ce-1098">Deficiência</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="4d3ce-1099">Número de passaporte do Canadá</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-1100">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1100">Format</span></span>

<span data-ttu-id="4d3ce-1101">Duas letras maiúsculas, seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-1102">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1102">Pattern</span></span>

<span data-ttu-id="4d3ce-1103">Duas letras maiúsculas, seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-1104">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1104">Checksum</span></span>

<span data-ttu-id="4d3ce-1105">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-1106">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1106">Definition</span></span>

<span data-ttu-id="4d3ce-1107">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-1108">A expressão regular Regex_canada_passport_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-1109">Uma palavra-chave de Keyword_canada_passport_number ou Keyword_passport for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-1110">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1110">Keywords</span></span>

#### <a name="keyword_canada_passport_number"></a><span data-ttu-id="4d3ce-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="4d3ce-1112">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1112">canadian citizenship</span></span>
- <span data-ttu-id="4d3ce-1113">canadian passport</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1113">canadian passport</span></span>
- <span data-ttu-id="4d3ce-1114">passport application</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1114">passport application</span></span>
- <span data-ttu-id="4d3ce-1115">passport photos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1115">passport photos</span></span>
- <span data-ttu-id="4d3ce-1116">certified translator</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1116">certified translator</span></span>
- <span data-ttu-id="4d3ce-1117">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1117">canadian citizens</span></span>
- <span data-ttu-id="4d3ce-1118">processing times</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1118">processing times</span></span>
- <span data-ttu-id="4d3ce-1119">renewal application</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1119">renewal application</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="4d3ce-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1120">Keyword_passport</span></span>

- <span data-ttu-id="4d3ce-1121">Passport Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1121">Passport Number</span></span>
- <span data-ttu-id="4d3ce-1122">Passport No</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1122">Passport No</span></span>
- <span data-ttu-id="4d3ce-1123">Passport #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1123">Passport #</span></span>
- <span data-ttu-id="4d3ce-1124">Passaport #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1124">Passport#</span></span>
- <span data-ttu-id="4d3ce-1125">Passportid</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1125">PassportID</span></span>
- <span data-ttu-id="4d3ce-1126">Passportno</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1126">Passportno</span></span>
- <span data-ttu-id="4d3ce-1127">passportnumber</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1127">passportnumber</span></span>
- <span data-ttu-id="4d3ce-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1128">パスポート</span></span>
- <span data-ttu-id="4d3ce-1129">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1129">パスポート番号</span></span>
- <span data-ttu-id="4d3ce-1130">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1130">パスポートのNum</span></span>
- <span data-ttu-id="4d3ce-1131">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1131">パスポート＃</span></span>
- <span data-ttu-id="4d3ce-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1132">Numéro de passeport</span></span>
- <span data-ttu-id="4d3ce-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1133">Passeport n °</span></span>
- <span data-ttu-id="4d3ce-1134">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1134">Passeport Non</span></span>
- <span data-ttu-id="4d3ce-1135">Passeport #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1135">Passeport #</span></span>
- <span data-ttu-id="4d3ce-1136">Passeport #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1136">Passeport#</span></span>
- <span data-ttu-id="4d3ce-1137">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1137">PasseportNon</span></span>
- <span data-ttu-id="4d3ce-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="4d3ce-1139">Número de identificação pessoal de saúde do Canadá (PHIN)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-1140">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1140">Format</span></span>

<span data-ttu-id="4d3ce-1141">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-1142">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1142">Pattern</span></span>

<span data-ttu-id="4d3ce-1143">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-1144">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1144">Checksum</span></span>

<span data-ttu-id="4d3ce-1145">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-1146">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1146">Definition</span></span>

<span data-ttu-id="4d3ce-1147">Uma política de DLP é de 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres: a expressão regular Regex_canada_phin localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="4d3ce-1148">São encontradas pelo menos duas palavras-chave de Keyword_canada_phin ou Keyword_canada_provinces..</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-1149">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1149">Keywords</span></span>

#### <a name="keyword_canada_phin"></a><span data-ttu-id="4d3ce-1150">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="4d3ce-1151">social insurance number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1151">social insurance number</span></span>
- <span data-ttu-id="4d3ce-1152">health information act</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1152">health information act</span></span>
- <span data-ttu-id="4d3ce-1153">income tax information</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1153">income tax information</span></span>
- <span data-ttu-id="4d3ce-1154">manitoba health</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1154">manitoba health</span></span>
- <span data-ttu-id="4d3ce-1155">health registration</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1155">health registration</span></span>
- <span data-ttu-id="4d3ce-1156">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1156">prescription purchases</span></span>
- <span data-ttu-id="4d3ce-1157">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1157">benefit eligibility</span></span>
- <span data-ttu-id="4d3ce-1158">personal health</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1158">personal health</span></span>
- <span data-ttu-id="4d3ce-1159">power of attorney</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1159">power of attorney</span></span>
- <span data-ttu-id="4d3ce-1160">registration number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1160">registration number</span></span>
- <span data-ttu-id="4d3ce-1161">personal health number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1161">personal health number</span></span>
- <span data-ttu-id="4d3ce-1162">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1162">practitioner referral</span></span>
- <span data-ttu-id="4d3ce-1163">wellness professional</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1163">wellness professional</span></span>
- <span data-ttu-id="4d3ce-1164">patient referral</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1164">patient referral</span></span>
- <span data-ttu-id="4d3ce-1165">health and wellness</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1165">health and wellness</span></span>

#### <a name="keyword_canada_provinces"></a><span data-ttu-id="4d3ce-1166">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="4d3ce-1167">Nunavut</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1167">Nunavut</span></span>
- <span data-ttu-id="4d3ce-1168">Quebec</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1168">Quebec</span></span>
- <span data-ttu-id="4d3ce-1169">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1169">Northwest Territories</span></span>
- <span data-ttu-id="4d3ce-1170">Ontário</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1170">Ontario</span></span>
- <span data-ttu-id="4d3ce-1171">British Columbia</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1171">British Columbia</span></span>
- <span data-ttu-id="4d3ce-1172">Alberta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1172">Alberta</span></span>
- <span data-ttu-id="4d3ce-1173">Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1173">Saskatchewan</span></span>
- <span data-ttu-id="4d3ce-1174">Manitoba</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1174">Manitoba</span></span>
- <span data-ttu-id="4d3ce-1175">Yukon</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1175">Yukon</span></span>
- <span data-ttu-id="4d3ce-1176">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="4d3ce-1177">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1177">New Brunswick</span></span>
- <span data-ttu-id="4d3ce-1178">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1178">Nova Scotia</span></span>
- <span data-ttu-id="4d3ce-1179">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1179">Prince Edward Island</span></span>
- <span data-ttu-id="4d3ce-1180">Canadá</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="4d3ce-1181">Número de seguro social do Canadá</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-1182">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1182">Format</span></span>

<span data-ttu-id="4d3ce-1183">Nove dígitos com espaços ou hífens opcionais</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-1184">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1184">Pattern</span></span>

<span data-ttu-id="4d3ce-1185">Binário</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1185">Formatted:</span></span>
- <span data-ttu-id="4d3ce-1186">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1186">Three digits</span></span> 
- <span data-ttu-id="4d3ce-1187">Um hífen ou espaço</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1187">A hyphen or space</span></span> 
- <span data-ttu-id="4d3ce-1188">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1188">Three digits</span></span> 
- <span data-ttu-id="4d3ce-1189">Um hífen ou espaço</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1189">A hyphen or space</span></span> 
- <span data-ttu-id="4d3ce-1190">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1190">Three digits</span></span>

<span data-ttu-id="4d3ce-1191">Não formatado: nove dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-1192">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1192">Checksum</span></span>

<span data-ttu-id="4d3ce-1193">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-1194">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1194">Definition</span></span>

<span data-ttu-id="4d3ce-1195">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-1196">A função Func_canadian_sin localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-1197">Pelo menos duas de qualquer combinação do seguinte:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="4d3ce-1198">Uma palavra-chave de Keyword_sin for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="4d3ce-1199">Uma palavra-chave de Keyword_sin_collaborative for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="4d3ce-1200">A função Func_eu_date encontra uma data no formato de data à direita.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="4d3ce-1201">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1201">The checksum passes.</span></span>

<span data-ttu-id="4d3ce-1202">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-1203">A função Func_unformatted_canadian_sin localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-1204">Uma palavra-chave de Keyword_sin for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="4d3ce-1205">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1205">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-1206">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1206">Keywords</span></span>

#### <a name="keyword_sin"></a><span data-ttu-id="4d3ce-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1207">Keyword_sin</span></span>

- <span data-ttu-id="4d3ce-1208">sin</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1208">sin</span></span> 
- <span data-ttu-id="4d3ce-1209">social insurance</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1209">social insurance</span></span> 
- <span data-ttu-id="4d3ce-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="4d3ce-1211">capitais</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1211">sins</span></span> 
- <span data-ttu-id="4d3ce-1212">es</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1212">ssn</span></span> 
- <span data-ttu-id="4d3ce-1213">CPFs</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1213">ssns</span></span> 
- <span data-ttu-id="4d3ce-1214">social security</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1214">social security</span></span> 
- <span data-ttu-id="4d3ce-1215">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="4d3ce-1216">national identification number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1216">national identification number</span></span> 
- <span data-ttu-id="4d3ce-1217">national id</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1217">national id</span></span> 
- <span data-ttu-id="4d3ce-1218">Sin #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1218">sin#</span></span> 
- <span data-ttu-id="4d3ce-1219">soc ins</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1219">soc ins</span></span> 
- <span data-ttu-id="4d3ce-1220">social ins</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1220">social ins</span></span> 

#### <a name="keyword_sin_collaborative"></a><span data-ttu-id="4d3ce-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="4d3ce-1222">driver's license</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1222">driver's license</span></span> 
- <span data-ttu-id="4d3ce-1223">drivers license</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1223">drivers license</span></span> 
- <span data-ttu-id="4d3ce-1224">driver's licence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1224">driver's licence</span></span> 
- <span data-ttu-id="4d3ce-1225">drivers licence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1225">drivers licence</span></span> 
- <span data-ttu-id="4d3ce-1226">DOB</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1226">DOB</span></span> 
- <span data-ttu-id="4d3ce-1227">Data de Nascimento</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1227">Birthdate</span></span> 
- <span data-ttu-id="4d3ce-1228">Aniversário</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1228">Birthday</span></span> 
- <span data-ttu-id="4d3ce-1229">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="4d3ce-1230">	Número do Cartão de Identidade do Chile</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-1231">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1231">Format</span></span>

<span data-ttu-id="4d3ce-1232">7-8 dígitos mais delimitadores um dígito ou letra de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-1233">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1233">Pattern</span></span>

<span data-ttu-id="4d3ce-1234">7 a 8 dígitos mais delimitadores:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="4d3ce-1235">1 a 2 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1235">1-2 digits</span></span> 
- <span data-ttu-id="4d3ce-1236">Um ponto </span><span class="sxs-lookup"><span data-stu-id="4d3ce-1236">A period</span></span> 
- <span data-ttu-id="4d3ce-1237">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1237">Three digits</span></span> 
- <span data-ttu-id="4d3ce-1238">Um ponto </span><span class="sxs-lookup"><span data-stu-id="4d3ce-1238">A period</span></span> 
- <span data-ttu-id="4d3ce-1239">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1239">Three digits</span></span> 
- <span data-ttu-id="4d3ce-1240">Um traço</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1240">A dash</span></span> 
- <span data-ttu-id="4d3ce-1241">Um dígito ou letra (não diferencia maiúscula de minúscula) que é um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-1242">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1242">Checksum</span></span>

<span data-ttu-id="4d3ce-1243">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-1244">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1244">Definition</span></span>

<span data-ttu-id="4d3ce-1245">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-1246">A função Func_chile_id_card localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-1247">Uma palavra-chave de Keyword_chile_id_card for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="4d3ce-1248">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1248">The checksum passes.</span></span>

<span data-ttu-id="4d3ce-1249">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-1250">A função Func_chile_id_card localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-1251">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1251">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-1252">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1252">Keywords</span></span>

#### <a name="keyword_chile_id_card"></a><span data-ttu-id="4d3ce-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="4d3ce-1254">Número de Identificação Nacional</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1254">National Identification Number</span></span> 
- <span data-ttu-id="4d3ce-1255">Cartão de identidade</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1255">Identity card</span></span> 
- <span data-ttu-id="4d3ce-1256">ID</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1256">ID</span></span> 
- <span data-ttu-id="4d3ce-1257">Identificador</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1257">Identification</span></span> 
- <span data-ttu-id="4d3ce-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="4d3ce-1259">SEJAM</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1259">RUN</span></span> 
- <span data-ttu-id="4d3ce-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="4d3ce-1261">ROTINA</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1261">RUT</span></span> 
- <span data-ttu-id="4d3ce-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="4d3ce-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="4d3ce-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="4d3ce-1265">Identificación</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="4d3ce-1266">	Número do Cartão de Identidade de Residentes (PRC) da China</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-1267">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1267">Format</span></span>

<span data-ttu-id="4d3ce-1268">18 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-1269">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1269">Pattern</span></span>

<span data-ttu-id="4d3ce-1270">18 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1270">18 digits:</span></span>
- <span data-ttu-id="4d3ce-1271">Seis dígitos que são um código de endereço </span><span class="sxs-lookup"><span data-stu-id="4d3ce-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="4d3ce-1272">Oito dígitos no formato AAAAMMDD que são a data de nascimento </span><span class="sxs-lookup"><span data-stu-id="4d3ce-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="4d3ce-1273">Três dígitos que são um código de pedido </span><span class="sxs-lookup"><span data-stu-id="4d3ce-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="4d3ce-1274">Um dígito que é um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-1275">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1275">Checksum</span></span>

<span data-ttu-id="4d3ce-1276">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-1277">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1277">Definition</span></span>

<span data-ttu-id="4d3ce-1278">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-1279">A função Func_china_resident_id localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-1280">Uma palavra-chave de Keyword_china_resident_id for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="4d3ce-1281">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1281">The checksum passes.</span></span>

<span data-ttu-id="4d3ce-1282">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-1283">A função Func_china_resident_id localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-1284">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1284">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-1285">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1285">Keywords</span></span>

### <a name="keyword_china_resident_id"></a><span data-ttu-id="4d3ce-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="4d3ce-1287">Cartão de Identidade da Polônia</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="4d3ce-1288">POPULAR</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1288">PRC</span></span> 
- <span data-ttu-id="4d3ce-1289">Cartão de Identificação Nacional</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1289">National Identification Card</span></span> 
- <span data-ttu-id="4d3ce-1290">身份证</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1290">身份证</span></span> 
- <span data-ttu-id="4d3ce-1291">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1291">居民 身份证</span></span> 
- <span data-ttu-id="4d3ce-1292">居民身份证</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1292">居民身份证</span></span> 
- <span data-ttu-id="4d3ce-1293">鉴定</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1293">鉴定</span></span> 
- <span data-ttu-id="4d3ce-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1294">身分證</span></span> 
- <span data-ttu-id="4d3ce-1295">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1295">居民 身份證</span></span>
- <span data-ttu-id="4d3ce-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="4d3ce-1297">Credit Card Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-1298">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1298">Format</span></span>

<span data-ttu-id="4d3ce-1299">14 a 16 dígitos que podem ser formatados ou não formatados (dddddddddddddddd) e que devem passar no teste Luhn.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1299">14 to 16 digits which can be formatted or unformatted (dddddddddddddddd) and which must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-1300">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1300">Pattern</span></span>

<span data-ttu-id="4d3ce-1301">Padrão muito complexo e robusto que detecta cartões de todas as principais marcas em todo o mundo, incluindo Visa, MasterCard, Discover Card, JCB, American Express, vales-presentes e cartões diner.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-1302">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1302">Checksum</span></span>

<span data-ttu-id="4d3ce-1303">Sim, a soma de verificação Luhn</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-1304">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1304">Definition</span></span>

<span data-ttu-id="4d3ce-1305">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-1306">A função Func_credit_card localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-1307">Uma das seguintes opções for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1307">One of the following is true:</span></span>
    - <span data-ttu-id="4d3ce-1308">Uma palavra-chave de Keyword_cc_verification for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="4d3ce-1309">Uma palavra-chave de Keyword_cc_name for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="4d3ce-1310">A função Func_expiration_date encontra uma data no formato de data à direita.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="4d3ce-1311">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1311">The checksum passes.</span></span>

<span data-ttu-id="4d3ce-1312">Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-1313">A função Func_credit_card localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-1314">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1314">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-1315">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1315">Keywords</span></span>

#### <a name="keyword_cc_verification"></a><span data-ttu-id="4d3ce-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="4d3ce-1317">card verification</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1317">card verification</span></span>
- <span data-ttu-id="4d3ce-1318">card identification number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1318">card identification number</span></span>
- <span data-ttu-id="4d3ce-1319">cvn</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1319">cvn</span></span>
- <span data-ttu-id="4d3ce-1320">CID</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1320">cid</span></span>
- <span data-ttu-id="4d3ce-1321">cvc2</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1321">cvc2</span></span>
- <span data-ttu-id="4d3ce-1322">cvv2</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1322">cvv2</span></span>
- <span data-ttu-id="4d3ce-1323">pin block</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1323">pin block</span></span>
- <span data-ttu-id="4d3ce-1324">security code</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1324">security code</span></span>
- <span data-ttu-id="4d3ce-1325">security number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1325">security number</span></span>
- <span data-ttu-id="4d3ce-1326">security no</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1326">security no</span></span>
- <span data-ttu-id="4d3ce-1327">issue number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1327">issue number</span></span>
- <span data-ttu-id="4d3ce-1328">issue no</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1328">issue no</span></span>
- <span data-ttu-id="4d3ce-1329">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1329">cryptogramme</span></span>
- <span data-ttu-id="4d3ce-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1330">numéro de sécurité</span></span>
- <span data-ttu-id="4d3ce-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1331">numero de securite</span></span>
- <span data-ttu-id="4d3ce-1332">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="4d3ce-1333">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="4d3ce-1334">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1334">prüfziffer</span></span>
- <span data-ttu-id="4d3ce-1335">prufziffer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1335">prufziffer</span></span>
- <span data-ttu-id="4d3ce-1336">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1336">sicherheits Kode</span></span>
- <span data-ttu-id="4d3ce-1337">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1337">sicherheitscode</span></span>
- <span data-ttu-id="4d3ce-1338">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="4d3ce-1339">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1339">verfalldatum</span></span>
- <span data-ttu-id="4d3ce-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1340">codice di verifica</span></span>
- <span data-ttu-id="4d3ce-1341">COD.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1341">cod.</span></span> <span data-ttu-id="4d3ce-1342">sicurezza</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1342">sicurezza</span></span>
- <span data-ttu-id="4d3ce-1343">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1343">cod sicurezza</span></span>
- <span data-ttu-id="4d3ce-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1344">n autorizzazione</span></span>
- <span data-ttu-id="4d3ce-1345">CFOP</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1345">código</span></span>
- <span data-ttu-id="4d3ce-1346">codigo</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1346">codigo</span></span>
- <span data-ttu-id="4d3ce-1347">COD.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1347">cod.</span></span> <span data-ttu-id="4d3ce-1348">seg</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1348">seg</span></span>
- <span data-ttu-id="4d3ce-1349">cod seg</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1349">cod seg</span></span>
- <span data-ttu-id="4d3ce-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1350">código de segurança</span></span>
- <span data-ttu-id="4d3ce-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1351">codigo de seguranca</span></span>
- <span data-ttu-id="4d3ce-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1352">codigo de segurança</span></span>
- <span data-ttu-id="4d3ce-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1353">código de seguranca</span></span>
- <span data-ttu-id="4d3ce-1354">cód.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1354">cód.</span></span> <span data-ttu-id="4d3ce-1355">segurança</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1355">segurança</span></span>
- <span data-ttu-id="4d3ce-1356">COD.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1356">cod.</span></span> <span data-ttu-id="4d3ce-1357">seguranca Cod.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1357">seguranca cod.</span></span> <span data-ttu-id="4d3ce-1358">segurança</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1358">segurança</span></span>
- <span data-ttu-id="4d3ce-1359">cód.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1359">cód.</span></span> <span data-ttu-id="4d3ce-1360">seguranca</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1360">seguranca</span></span>
- <span data-ttu-id="4d3ce-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1361">cód segurança</span></span>
- <span data-ttu-id="4d3ce-1362">COD seguranca COD segurança</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="4d3ce-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1363">cód seguranca</span></span>
- <span data-ttu-id="4d3ce-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1364">número de verificação</span></span>
- <span data-ttu-id="4d3ce-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1365">numero de verificacao</span></span>
- <span data-ttu-id="4d3ce-1366">ablauf</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1366">ablauf</span></span>
- <span data-ttu-id="4d3ce-1367">gültig bis</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1367">gültig bis</span></span>
- <span data-ttu-id="4d3ce-1368">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="4d3ce-1369">gultig bis</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1369">gultig bis</span></span>
- <span data-ttu-id="4d3ce-1370">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="4d3ce-1371">scadenza</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1371">scadenza</span></span>
- <span data-ttu-id="4d3ce-1372">data scad</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1372">data scad</span></span>
- <span data-ttu-id="4d3ce-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1373">fecha de expiracion</span></span>
- <span data-ttu-id="4d3ce-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1374">fecha de venc</span></span>
- <span data-ttu-id="4d3ce-1375">vencimiento</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1375">vencimiento</span></span>
- <span data-ttu-id="4d3ce-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1376">válido hasta</span></span>
- <span data-ttu-id="4d3ce-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1377">valido hasta</span></span>
- <span data-ttu-id="4d3ce-1378">vto</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1378">vto</span></span>
- <span data-ttu-id="4d3ce-1379">data de expiração</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1379">data de expiração</span></span>
- <span data-ttu-id="4d3ce-1380">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1380">data de expiracao</span></span>
- <span data-ttu-id="4d3ce-1381">data em que expira</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1381">data em que expira</span></span>
- <span data-ttu-id="4d3ce-1382">validade</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1382">validade</span></span>
- <span data-ttu-id="4d3ce-1383">coragem</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1383">valor</span></span>
- <span data-ttu-id="4d3ce-1384">vencimento</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1384">vencimento</span></span>
- <span data-ttu-id="4d3ce-1385">Venc</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1385">Venc</span></span> 

#### <a name="keyword_cc_name"></a><span data-ttu-id="4d3ce-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="4d3ce-1387">amex</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1387">amex</span></span>
- <span data-ttu-id="4d3ce-1388">american express</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1388">american express</span></span>
- <span data-ttu-id="4d3ce-1389">americanexpress</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1389">americanexpress</span></span>
- <span data-ttu-id="4d3ce-1390">Cartões</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1390">Visa</span></span>
- <span data-ttu-id="4d3ce-1391">MasterCard</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1391">mastercard</span></span>
- <span data-ttu-id="4d3ce-1392">master card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1392">master card</span></span>
- <span data-ttu-id="4d3ce-1393">MC</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1393">mc</span></span> 
- <span data-ttu-id="4d3ce-1394">MasterCards</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1394">mastercards</span></span>
- <span data-ttu-id="4d3ce-1395">master cards</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1395">master cards</span></span>
- <span data-ttu-id="4d3ce-1396">diner's Club</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1396">diner's Club</span></span>
- <span data-ttu-id="4d3ce-1397">diners club</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1397">diners club</span></span>
- <span data-ttu-id="4d3ce-1398">dinersclub</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1398">dinersclub</span></span>
- <span data-ttu-id="4d3ce-1399">discover card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1399">discover card</span></span>
- <span data-ttu-id="4d3ce-1400">discovercard</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1400">discovercard</span></span>
- <span data-ttu-id="4d3ce-1401">discover cards</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1401">discover cards</span></span>
- <span data-ttu-id="4d3ce-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1402">JCB</span></span>
- <span data-ttu-id="4d3ce-1403">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1403">japanese card bureau</span></span>
- <span data-ttu-id="4d3ce-1404">carte blanche</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1404">carte blanche</span></span>
- <span data-ttu-id="4d3ce-1405">carteblanche</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1405">carteblanche</span></span>
- <span data-ttu-id="4d3ce-1406">credit card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1406">credit card</span></span>
- <span data-ttu-id="4d3ce-1407">colocado #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1407">cc#</span></span>
- <span data-ttu-id="4d3ce-1408">CC #:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1408">cc#:</span></span>
- <span data-ttu-id="4d3ce-1409">expiration date</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1409">expiration date</span></span>
- <span data-ttu-id="4d3ce-1410">exp date</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1410">exp date</span></span>
- <span data-ttu-id="4d3ce-1411">expiry date</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1411">expiry date</span></span>
- <span data-ttu-id="4d3ce-1412">date d’expiration</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1412">date d’expiration</span></span>
- <span data-ttu-id="4d3ce-1413">date d'exp</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1413">date d'exp</span></span>
- <span data-ttu-id="4d3ce-1414">date expiration</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1414">date expiration</span></span>
- <span data-ttu-id="4d3ce-1415">bank card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1415">bank card</span></span>
- <span data-ttu-id="4d3ce-1416">bankcard</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1416">bankcard</span></span>
- <span data-ttu-id="4d3ce-1417">card number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1417">card number</span></span>
- <span data-ttu-id="4d3ce-1418">card num</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1418">card num</span></span>
- <span data-ttu-id="4d3ce-1419">cardnumber</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1419">cardnumber</span></span>
- <span data-ttu-id="4d3ce-1420">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1420">cardnumbers</span></span>
- <span data-ttu-id="4d3ce-1421">card numbers</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1421">card numbers</span></span>
- <span data-ttu-id="4d3ce-1422">CreditCard</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1422">creditcard</span></span>
- <span data-ttu-id="4d3ce-1423">credit cards</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1423">credit cards</span></span>
- <span data-ttu-id="4d3ce-1424">creditcards</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1424">creditcards</span></span>
- <span data-ttu-id="4d3ce-1425">CCN</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1425">ccn</span></span>
- <span data-ttu-id="4d3ce-1426">card holder</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1426">card holder</span></span>
- <span data-ttu-id="4d3ce-1427">aos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1427">cardholder</span></span>
- <span data-ttu-id="4d3ce-1428">card holders</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1428">card holders</span></span>
- <span data-ttu-id="4d3ce-1429">titulares de cartões</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1429">cardholders</span></span>
- <span data-ttu-id="4d3ce-1430">check card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1430">check card</span></span>
- <span data-ttu-id="4d3ce-1431">checkcard</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1431">checkcard</span></span>
- <span data-ttu-id="4d3ce-1432">check cards</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1432">check cards</span></span>
- <span data-ttu-id="4d3ce-1433">checkcards</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1433">checkcards</span></span>
- <span data-ttu-id="4d3ce-1434">debit card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1434">debit card</span></span>
- <span data-ttu-id="4d3ce-1435">debitcard</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1435">debitcard</span></span>
- <span data-ttu-id="4d3ce-1436">debit cards</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1436">debit cards</span></span>
- <span data-ttu-id="4d3ce-1437">debitcards</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1437">debitcards</span></span>
- <span data-ttu-id="4d3ce-1438">atm card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1438">atm card</span></span>
- <span data-ttu-id="4d3ce-1439">atmcard</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1439">atmcard</span></span>
- <span data-ttu-id="4d3ce-1440">atm cards</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1440">atm cards</span></span>
- <span data-ttu-id="4d3ce-1441">atmcards</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1441">atmcards</span></span>
- <span data-ttu-id="4d3ce-1442">encaminhar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1442">enroute</span></span>
- <span data-ttu-id="4d3ce-1443">en route</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1443">en route</span></span>
- <span data-ttu-id="4d3ce-1444">card type</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1444">card type</span></span>
- <span data-ttu-id="4d3ce-1445">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1445">carte bancaire</span></span>
- <span data-ttu-id="4d3ce-1446">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1446">carte de crédit</span></span>
- <span data-ttu-id="4d3ce-1447">carte de credit</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1447">carte de credit</span></span>
- <span data-ttu-id="4d3ce-1448">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1448">numéro de carte</span></span>
- <span data-ttu-id="4d3ce-1449">numero de carte</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1449">numero de carte</span></span>
- <span data-ttu-id="4d3ce-1450">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1450">nº de la carte</span></span>
- <span data-ttu-id="4d3ce-1451">nº de carte</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1451">nº de carte</span></span>
- <span data-ttu-id="4d3ce-1452">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1452">kreditkarte</span></span>
- <span data-ttu-id="4d3ce-1453">karte</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1453">karte</span></span>
- <span data-ttu-id="4d3ce-1454">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1454">karteninhaber</span></span>
- <span data-ttu-id="4d3ce-1455">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1455">karteninhabers</span></span>
- <span data-ttu-id="4d3ce-1456">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="4d3ce-1457">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="4d3ce-1458">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1458">kreditkartentyp</span></span>
- <span data-ttu-id="4d3ce-1459">eigentümername</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1459">eigentümername</span></span>
- <span data-ttu-id="4d3ce-1460">kartennr</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1460">kartennr</span></span> 
- <span data-ttu-id="4d3ce-1461">kartennummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1461">kartennummer</span></span>
- <span data-ttu-id="4d3ce-1462">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1462">kreditkartennummer</span></span>
- <span data-ttu-id="4d3ce-1463">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="4d3ce-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1464">carta di credito</span></span>
- <span data-ttu-id="4d3ce-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1465">carta credito</span></span>
- <span data-ttu-id="4d3ce-1466">carta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1466">carta</span></span>
- <span data-ttu-id="4d3ce-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1467">n carta</span></span>
- <span data-ttu-id="4d3ce-1468">nr.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1468">nr.</span></span> <span data-ttu-id="4d3ce-1469">carta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1469">carta</span></span>
- <span data-ttu-id="4d3ce-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1470">nr carta</span></span>
- <span data-ttu-id="4d3ce-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1471">numero carta</span></span>
- <span data-ttu-id="4d3ce-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1472">numero della carta</span></span>
- <span data-ttu-id="4d3ce-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1473">numero di carta</span></span>
- <span data-ttu-id="4d3ce-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1474">tarjeta credito</span></span>
- <span data-ttu-id="4d3ce-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1475">tarjeta de credito</span></span>
- <span data-ttu-id="4d3ce-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1476">tarjeta crédito</span></span>
- <span data-ttu-id="4d3ce-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="4d3ce-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1478">tarjeta de atm</span></span>
- <span data-ttu-id="4d3ce-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1479">tarjeta atm</span></span>
- <span data-ttu-id="4d3ce-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1480">tarjeta debito</span></span>
- <span data-ttu-id="4d3ce-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1481">tarjeta de debito</span></span>
- <span data-ttu-id="4d3ce-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1482">tarjeta débito</span></span>
- <span data-ttu-id="4d3ce-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1483">tarjeta de débito</span></span>
- <span data-ttu-id="4d3ce-1484">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1484">nº de tarjeta</span></span>
- <span data-ttu-id="4d3ce-1485">Não.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1485">no.</span></span> <span data-ttu-id="4d3ce-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1486">de tarjeta</span></span>
- <span data-ttu-id="4d3ce-1487">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1487">no de tarjeta</span></span>
- <span data-ttu-id="4d3ce-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1488">numero de tarjeta</span></span>
- <span data-ttu-id="4d3ce-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1489">número de tarjeta</span></span>
- <span data-ttu-id="4d3ce-1490">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1490">tarjeta no</span></span>
- <span data-ttu-id="4d3ce-1491">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1491">tarjetahabiente</span></span>
- <span data-ttu-id="4d3ce-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1492">cartão de crédito</span></span>
- <span data-ttu-id="4d3ce-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1493">cartão de credito</span></span>
- <span data-ttu-id="4d3ce-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1494">cartao de crédito</span></span>
- <span data-ttu-id="4d3ce-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1495">cartao de credito</span></span>
- <span data-ttu-id="4d3ce-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1496">cartão de débito</span></span>
- <span data-ttu-id="4d3ce-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1497">cartao de débito</span></span>
- <span data-ttu-id="4d3ce-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1498">cartão de debito</span></span>
- <span data-ttu-id="4d3ce-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1499">cartao de debito</span></span>
- <span data-ttu-id="4d3ce-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1500">débito automático</span></span>
- <span data-ttu-id="4d3ce-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1501">debito automatico</span></span>
- <span data-ttu-id="4d3ce-1502">número do cartão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1502">número do cartão</span></span>
- <span data-ttu-id="4d3ce-1503">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1503">numero do cartão</span></span> 
- <span data-ttu-id="4d3ce-1504">número do cartao</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1504">número do cartao</span></span>
- <span data-ttu-id="4d3ce-1505">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1505">numero do cartao</span></span>
- <span data-ttu-id="4d3ce-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1506">número de cartão</span></span>
- <span data-ttu-id="4d3ce-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1507">numero de cartão</span></span>
- <span data-ttu-id="4d3ce-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1508">número de cartao</span></span>
- <span data-ttu-id="4d3ce-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1509">numero de cartao</span></span>
- <span data-ttu-id="4d3ce-1510">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1510">nº do cartão</span></span>
- <span data-ttu-id="4d3ce-1511">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1511">nº do cartao</span></span>
- <span data-ttu-id="4d3ce-1512">n º.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1512">nº.</span></span> <span data-ttu-id="4d3ce-1513">do cartão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1513">do cartão</span></span>
- <span data-ttu-id="4d3ce-1514">no do cartão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1514">no do cartão</span></span>
- <span data-ttu-id="4d3ce-1515">no do cartao</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1515">no do cartao</span></span>
- <span data-ttu-id="4d3ce-1516">Não.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1516">no.</span></span> <span data-ttu-id="4d3ce-1517">do cartão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1517">do cartão</span></span>
- <span data-ttu-id="4d3ce-1518">Não.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1518">no.</span></span> <span data-ttu-id="4d3ce-1519">do cartao</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="4d3ce-1520">	Número do Cartão de Identidade da Croácia</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-1521">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1521">Format</span></span>

<span data-ttu-id="4d3ce-1522">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-1523">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1523">Pattern</span></span>

<span data-ttu-id="4d3ce-1524">Nove dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-1525">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1525">Checksum</span></span>

<span data-ttu-id="4d3ce-1526">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-1527">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1527">Definition</span></span>

<span data-ttu-id="4d3ce-1528">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-1529">A função Func_croatia_id_card localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-1530">Uma palavra-chave de Keyword_croatia_id_card for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-1531">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1531">Keywords</span></span>

#### <a name="keyword_croatia_id_card"></a><span data-ttu-id="4d3ce-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="4d3ce-1533">Cartão de identidade croata</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1533">Croatian identity card</span></span>
- <span data-ttu-id="4d3ce-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="4d3ce-1535">	Número de Identificação Pessoal (OIB) da Croácia</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-1536">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1536">Format</span></span>

<span data-ttu-id="4d3ce-1537">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-1538">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1538">Pattern</span></span>

<span data-ttu-id="4d3ce-1539">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1539">11 digits:</span></span>
- <span data-ttu-id="4d3ce-1540">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1540">10 digits</span></span> 
- <span data-ttu-id="4d3ce-1541">O dígito final é um dígito de verificação para os fins de troca de dados internacionais, as letras de RH são adicionadas antes dos onze dígitos.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-1542">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1542">Checksum</span></span>

<span data-ttu-id="4d3ce-1543">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-1544">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1544">Definition</span></span>

<span data-ttu-id="4d3ce-1545">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-1546">A função Func_croatia_oib_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-1547">Uma palavra-chave de Keyword_croatia_oib_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="4d3ce-1548">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1548">The checksum passes.</span></span>

<span data-ttu-id="4d3ce-1549">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-1550">A função Func_croatia_oib_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-1551">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1551">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-1552">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1552">Keywords</span></span>

#### <a name="keyword_croatia_oib_number"></a><span data-ttu-id="4d3ce-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="4d3ce-1554">Número de Identificação Pessoal</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1554">Personal Identification Number</span></span>
- <span data-ttu-id="4d3ce-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="4d3ce-1556">NIB</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="4d3ce-1557">Número de identidade pessoal tcheco</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-1558">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1558">Format</span></span>

<span data-ttu-id="4d3ce-1559">Nove dígitos com barra de avanço opcional (formato antigo) 10 dígitos com barra de avanço opcional (novo formato)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-1560">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1560">Pattern</span></span>

<span data-ttu-id="4d3ce-1561">Nove dígitos (formato antigo):</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="4d3ce-1562">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1562">Nine digits</span></span>

<span data-ttu-id="4d3ce-1563">OU</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1563">OR</span></span>

- <span data-ttu-id="4d3ce-1564">Seis dígitos que representam a data de nascimento</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="4d3ce-1565">Uma barra</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1565">A forward slash</span></span>
- <span data-ttu-id="4d3ce-1566">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1566">Three digits</span></span>

<span data-ttu-id="4d3ce-1567">10 dígitos (novo formato):</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1567">10 digits (new format):</span></span>
- <span data-ttu-id="4d3ce-1568">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1568">10 digits</span></span>

<span data-ttu-id="4d3ce-1569">OU</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1569">OR</span></span>

- <span data-ttu-id="4d3ce-1570">Seis dígitos que representam a data de nascimento</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="4d3ce-1571">Uma barra</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1571">A forward slash</span></span> 
- <span data-ttu-id="4d3ce-1572">Quatro dígitos onde o último dígito é um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-1573">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1573">Checksum</span></span>

<span data-ttu-id="4d3ce-1574">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-1575">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1575">Definition</span></span>

<span data-ttu-id="4d3ce-1576">Uma política de DLP é de 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres: a função Func_czech_id_card localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="4d3ce-1577">Uma palavra-chave de Keyword_czech_id_card for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="4d3ce-1578">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1578">The checksum passes.</span></span>

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="4d3ce-1579">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1579">Keywords</span></span>

- <span data-ttu-id="4d3ce-1580">número de identidade pessoal tcheco</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1580">czech personal identity number</span></span>
- <span data-ttu-id="4d3ce-1581">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="4d3ce-1582">	Número de Identificação Pessoal da Dinamarca</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-1583">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1583">Format</span></span>

<span data-ttu-id="4d3ce-1584">10 dígitos que contêm um hífen</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-1585">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1585">Pattern</span></span>

<span data-ttu-id="4d3ce-1586">10 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1586">10 digits:</span></span>
- <span data-ttu-id="4d3ce-1587">Seis dígitos no formato DDMMAA que são a data de nascimento</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="4d3ce-1588">Um hífen</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1588">A hyphen</span></span> 
- <span data-ttu-id="4d3ce-1589">Quatro dígitos em que o último é um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-1590">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1590">Checksum</span></span>

<span data-ttu-id="4d3ce-1591">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-1592">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1592">Definition</span></span>

<span data-ttu-id="4d3ce-1593">Uma política de DLP é de 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres: a expressão regular Regex_denmark_id localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="4d3ce-1594">Uma palavra-chave de Keyword_denmark_id for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="4d3ce-1595">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1595">The checksum passes.</span></span>

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-1596">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1596">Keywords</span></span>

#### <a name="keyword_denmark_id"></a><span data-ttu-id="4d3ce-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="4d3ce-1598">Número de Identificação Pessoal</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1598">Personal Identification Number</span></span>
- <span data-ttu-id="4d3ce-1599">PEDIR</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1599">CPR</span></span>
- <span data-ttu-id="4d3ce-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="4d3ce-1601">Personnummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="4d3ce-1602">Número da Drug Enforcement Agency (DEA)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-1603">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1603">Format</span></span>

<span data-ttu-id="4d3ce-1604">Duas letras seguidas por sete dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-1605">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1605">Pattern</span></span>

<span data-ttu-id="4d3ce-1606">O padrão deve incluir todos os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="4d3ce-1607">Uma letra (não diferencia maiúscula de minúscula) deste conjunto de letras possíveis: abcdefghjklmnprstux, que é um código de inscrito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="4d3ce-1608">Uma letra (não diferencia maiúscula de minúscula), que é a primeira letra do sobrenome do inscrito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="4d3ce-1609">Sete dígitos, dos quais o último é o dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-1610">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1610">Checksum</span></span>

<span data-ttu-id="4d3ce-1611">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-1612">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1612">Definition</span></span>

<span data-ttu-id="4d3ce-1613">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-1614">A função Func_dea_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-1615">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1615">The checksum passes.</span></span>

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-1616">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1616">Keywords</span></span>

<span data-ttu-id="4d3ce-1617">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="4d3ce-1618">Número de cartão de débito da UE</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-1619">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1619">Format</span></span>

<span data-ttu-id="4d3ce-1620">16 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-1621">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1621">Pattern</span></span>

<span data-ttu-id="4d3ce-1622">Padrão muito complexo e robusto</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-1623">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1623">Checksum</span></span>

<span data-ttu-id="4d3ce-1624">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-1625">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1625">Definition</span></span>

<span data-ttu-id="4d3ce-1626">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-1627">A função Func_eu_debit_card localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-1628">Pelo menos uma das seguintes opções for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="4d3ce-1629">Uma palavra-chave de Keyword_eu_debit_card for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="4d3ce-1630">Uma palavra-chave de Keyword_card_terms_dict for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="4d3ce-1631">Uma palavra-chave de Keyword_card_security_terms_dict for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="4d3ce-1632">Uma palavra-chave de Keyword_card_expiration_terms_dict for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="4d3ce-1633">A função Func_expiration_date encontra uma data no formato de data à direita.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="4d3ce-1634">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1634">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-1635">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1635">Keywords</span></span>

#### <a name="keyword_eu_debit_card"></a><span data-ttu-id="4d3ce-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="4d3ce-1637">account number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1637">account number</span></span> 
- <span data-ttu-id="4d3ce-1638">card number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1638">card number</span></span> 
- <span data-ttu-id="4d3ce-1639">card no.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1639">card no.</span></span> 
- <span data-ttu-id="4d3ce-1640">security number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1640">security number</span></span> 
- <span data-ttu-id="4d3ce-1641">colocado #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1641">cc#</span></span> 

#### <a name="keyword_card_terms_dict"></a><span data-ttu-id="4d3ce-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="4d3ce-1643">acct nbr</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1643">acct nbr</span></span> 
- <span data-ttu-id="4d3ce-1644">acct num</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1644">acct num</span></span> 
- <span data-ttu-id="4d3ce-1645">acct no</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1645">acct no</span></span> 
- <span data-ttu-id="4d3ce-1646">american express</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1646">american express</span></span> 
- <span data-ttu-id="4d3ce-1647">americanexpress</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1647">americanexpress</span></span> 
- <span data-ttu-id="4d3ce-1648">americano espresso</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1648">americano espresso</span></span> 
- <span data-ttu-id="4d3ce-1649">amex</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1649">amex</span></span> 
- <span data-ttu-id="4d3ce-1650">atm card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1650">atm card</span></span> 
- <span data-ttu-id="4d3ce-1651">atm cards</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1651">atm cards</span></span> 
- <span data-ttu-id="4d3ce-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1652">atm kaart</span></span> 
- <span data-ttu-id="4d3ce-1653">atmcard</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1653">atmcard</span></span> 
- <span data-ttu-id="4d3ce-1654">atmcards</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1654">atmcards</span></span> 
- <span data-ttu-id="4d3ce-1655">atmkaart</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1655">atmkaart</span></span> 
- <span data-ttu-id="4d3ce-1656">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1656">atmkaarten</span></span> 
- <span data-ttu-id="4d3ce-1657">bancontact</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1657">bancontact</span></span> 
- <span data-ttu-id="4d3ce-1658">bank card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1658">bank card</span></span> 
- <span data-ttu-id="4d3ce-1659">bankkaart</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1659">bankkaart</span></span> 
- <span data-ttu-id="4d3ce-1660">card holder</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1660">card holder</span></span> 
- <span data-ttu-id="4d3ce-1661">card holders</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1661">card holders</span></span> 
- <span data-ttu-id="4d3ce-1662">card num</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1662">card num</span></span> 
- <span data-ttu-id="4d3ce-1663">card number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1663">card number</span></span> 
- <span data-ttu-id="4d3ce-1664">card numbers</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1664">card numbers</span></span> 
- <span data-ttu-id="4d3ce-1665">card type</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1665">card type</span></span> 
- <span data-ttu-id="4d3ce-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1666">cardano numerico</span></span> 
- <span data-ttu-id="4d3ce-1667">aos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1667">cardholder</span></span> 
- <span data-ttu-id="4d3ce-1668">titulares de cartões</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1668">cardholders</span></span> 
- <span data-ttu-id="4d3ce-1669">cardnumber</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1669">cardnumber</span></span> 
- <span data-ttu-id="4d3ce-1670">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1670">cardnumbers</span></span> 
- <span data-ttu-id="4d3ce-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1671">carta bianca</span></span> 
- <span data-ttu-id="4d3ce-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1672">carta credito</span></span> 
- <span data-ttu-id="4d3ce-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1673">carta di credito</span></span> 
- <span data-ttu-id="4d3ce-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1674">cartao de credito</span></span> 
- <span data-ttu-id="4d3ce-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1675">cartao de crédito</span></span> 
- <span data-ttu-id="4d3ce-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1676">cartao de debito</span></span> 
- <span data-ttu-id="4d3ce-1677">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1677">cartao de débito</span></span> 
- <span data-ttu-id="4d3ce-1678">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1678">carte bancaire</span></span> 
- <span data-ttu-id="4d3ce-1679">carte blanche</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1679">carte blanche</span></span> 
- <span data-ttu-id="4d3ce-1680">carte bleue</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1680">carte bleue</span></span> 
- <span data-ttu-id="4d3ce-1681">carte de credit</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1681">carte de credit</span></span> 
- <span data-ttu-id="4d3ce-1682">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1682">carte de crédit</span></span> 
- <span data-ttu-id="4d3ce-1683">carte di credito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1683">carte di credito</span></span> 
- <span data-ttu-id="4d3ce-1684">carteblanche</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1684">carteblanche</span></span> 
- <span data-ttu-id="4d3ce-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1685">cartão de credito</span></span> 
- <span data-ttu-id="4d3ce-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1686">cartão de crédito</span></span> 
- <span data-ttu-id="4d3ce-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1687">cartão de debito</span></span> 
- <span data-ttu-id="4d3ce-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1688">cartão de débito</span></span> 
- <span data-ttu-id="4d3ce-1689">cb</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1689">cb</span></span> 
- <span data-ttu-id="4d3ce-1690">CCN</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1690">ccn</span></span> 
- <span data-ttu-id="4d3ce-1691">check card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1691">check card</span></span> 
- <span data-ttu-id="4d3ce-1692">check cards</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1692">check cards</span></span> 
- <span data-ttu-id="4d3ce-1693">checkcard</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1693">checkcard</span></span>
- <span data-ttu-id="4d3ce-1694">checkcards</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1694">checkcards</span></span> 
- <span data-ttu-id="4d3ce-1695">chequekaart</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1695">chequekaart</span></span> 
- <span data-ttu-id="4d3ce-1696">Cirrus</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1696">cirrus</span></span> 
- <span data-ttu-id="4d3ce-1697">Cirrus-EDC-maestro</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="4d3ce-1698">controlekaart</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1698">controlekaart</span></span> 
- <span data-ttu-id="4d3ce-1699">controlekaarten</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1699">controlekaarten</span></span> 
- <span data-ttu-id="4d3ce-1700">credit card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1700">credit card</span></span> 
- <span data-ttu-id="4d3ce-1701">credit cards</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1701">credit cards</span></span> 
- <span data-ttu-id="4d3ce-1702">CreditCard</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1702">creditcard</span></span> 
- <span data-ttu-id="4d3ce-1703">creditcards</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1703">creditcards</span></span> 
- <span data-ttu-id="4d3ce-1704">debetkaart</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1704">debetkaart</span></span> 
- <span data-ttu-id="4d3ce-1705">debetkaarten</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1705">debetkaarten</span></span> 
- <span data-ttu-id="4d3ce-1706">debit card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1706">debit card</span></span> 
- <span data-ttu-id="4d3ce-1707">debit cards</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1707">debit cards</span></span> 
- <span data-ttu-id="4d3ce-1708">debitcard</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1708">debitcard</span></span> 
- <span data-ttu-id="4d3ce-1709">debitcards</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1709">debitcards</span></span> 
- <span data-ttu-id="4d3ce-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1710">debito automatico</span></span> 
- <span data-ttu-id="4d3ce-1711">diners club</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1711">diners club</span></span> 
- <span data-ttu-id="4d3ce-1712">dinersclub</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1712">dinersclub</span></span> 
- <span data-ttu-id="4d3ce-1713">tect</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1713">discover</span></span> 
- <span data-ttu-id="4d3ce-1714">discover card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1714">discover card</span></span> 
- <span data-ttu-id="4d3ce-1715">discover cards</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1715">discover cards</span></span> 
- <span data-ttu-id="4d3ce-1716">discovercard</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1716">discovercard</span></span> 
- <span data-ttu-id="4d3ce-1717">discovercards</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1717">discovercards</span></span> 
- <span data-ttu-id="4d3ce-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1718">débito automático</span></span>
- <span data-ttu-id="4d3ce-1719">edc</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1719">edc</span></span> 
- <span data-ttu-id="4d3ce-1720">eigentümername</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1720">eigentümername</span></span> 
- <span data-ttu-id="4d3ce-1721">european debit card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1721">european debit card</span></span> 
- <span data-ttu-id="4d3ce-1722">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1722">hoofdkaart</span></span> 
- <span data-ttu-id="4d3ce-1723">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="4d3ce-1724">in viaggio</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1724">in viaggio</span></span> 
- <span data-ttu-id="4d3ce-1725">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1725">japanese card bureau</span></span> 
- <span data-ttu-id="4d3ce-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="4d3ce-1727">JCB</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1727">jcb</span></span> 
- <span data-ttu-id="4d3ce-1728">kaart</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1728">kaart</span></span> 
- <span data-ttu-id="4d3ce-1729">kaart num</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1729">kaart num</span></span> 
- <span data-ttu-id="4d3ce-1730">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1730">kaartaantal</span></span> 
- <span data-ttu-id="4d3ce-1731">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1731">kaartaantallen</span></span> 
- <span data-ttu-id="4d3ce-1732">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1732">kaarthouder</span></span> 
- <span data-ttu-id="4d3ce-1733">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1733">kaarthouders</span></span> 
- <span data-ttu-id="4d3ce-1734">karte</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1734">karte</span></span>  
- <span data-ttu-id="4d3ce-1735">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1735">karteninhaber</span></span> 
- <span data-ttu-id="4d3ce-1736">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1736">karteninhabers</span></span>
- <span data-ttu-id="4d3ce-1737">kartennr</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1737">kartennr</span></span> 
- <span data-ttu-id="4d3ce-1738">kartennummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1738">kartennummer</span></span> 
- <span data-ttu-id="4d3ce-1739">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1739">kreditkarte</span></span> 
- <span data-ttu-id="4d3ce-1740">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="4d3ce-1741">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="4d3ce-1742">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="4d3ce-1743">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="4d3ce-1744">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="4d3ce-1745">Maestro</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1745">maestro</span></span> 
- <span data-ttu-id="4d3ce-1746">master card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1746">master card</span></span> 
- <span data-ttu-id="4d3ce-1747">master cards</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1747">master cards</span></span> 
- <span data-ttu-id="4d3ce-1748">MasterCard</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1748">mastercard</span></span> 
- <span data-ttu-id="4d3ce-1749">MasterCards</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1749">mastercards</span></span> 
- <span data-ttu-id="4d3ce-1750">MC</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1750">mc</span></span> 
- <span data-ttu-id="4d3ce-1751">mister cash</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1751">mister cash</span></span> 
- <span data-ttu-id="4d3ce-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1752">n carta</span></span> 
- <span data-ttu-id="4d3ce-1753">carta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1753">carta</span></span> 
- <span data-ttu-id="4d3ce-1754">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1754">no de tarjeta</span></span> 
- <span data-ttu-id="4d3ce-1755">no do cartao</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1755">no do cartao</span></span> 
- <span data-ttu-id="4d3ce-1756">no do cartão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1756">no do cartão</span></span> 
- <span data-ttu-id="4d3ce-1757">Não.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1757">no.</span></span> <span data-ttu-id="4d3ce-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1758">de tarjeta</span></span> 
- <span data-ttu-id="4d3ce-1759">Não.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1759">no.</span></span> <span data-ttu-id="4d3ce-1760">do cartao</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1760">do cartao</span></span> 
- <span data-ttu-id="4d3ce-1761">Não.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1761">no.</span></span> <span data-ttu-id="4d3ce-1762">do cartão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1762">do cartão</span></span> 
- <span data-ttu-id="4d3ce-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1763">nr carta</span></span> 
- <span data-ttu-id="4d3ce-1764">nr.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1764">nr.</span></span> <span data-ttu-id="4d3ce-1765">carta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1765">carta</span></span> 
- <span data-ttu-id="4d3ce-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1766">numeri di scheda</span></span> 
- <span data-ttu-id="4d3ce-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1767">numero carta</span></span> 
- <span data-ttu-id="4d3ce-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1768">numero de cartao</span></span> 
- <span data-ttu-id="4d3ce-1769">numero de carte</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1769">numero de carte</span></span> 
- <span data-ttu-id="4d3ce-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1770">numero de cartão</span></span> 
- <span data-ttu-id="4d3ce-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1771">numero de tarjeta</span></span>
- <span data-ttu-id="4d3ce-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1772">numero della carta</span></span> 
- <span data-ttu-id="4d3ce-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1773">numero di carta</span></span> 
- <span data-ttu-id="4d3ce-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1774">numero di scheda</span></span> 
- <span data-ttu-id="4d3ce-1775">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1775">numero do cartao</span></span> 
- <span data-ttu-id="4d3ce-1776">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1776">numero do cartão</span></span> 
- <span data-ttu-id="4d3ce-1777">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1777">numéro de carte</span></span> 
- <span data-ttu-id="4d3ce-1778">nº carta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1778">nº carta</span></span> 
- <span data-ttu-id="4d3ce-1779">nº de carte</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1779">nº de carte</span></span> 
- <span data-ttu-id="4d3ce-1780">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1780">nº de la carte</span></span> 
- <span data-ttu-id="4d3ce-1781">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="4d3ce-1782">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1782">nº do cartao</span></span> 
- <span data-ttu-id="4d3ce-1783">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1783">nº do cartão</span></span> 
- <span data-ttu-id="4d3ce-1784">n º.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1784">nº.</span></span> <span data-ttu-id="4d3ce-1785">do cartão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1785">do cartão</span></span> 
- <span data-ttu-id="4d3ce-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1786">número de cartao</span></span> 
- <span data-ttu-id="4d3ce-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1787">número de cartão</span></span> 
- <span data-ttu-id="4d3ce-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1788">número de tarjeta</span></span> 
- <span data-ttu-id="4d3ce-1789">número do cartao</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1789">número do cartao</span></span> 
- <span data-ttu-id="4d3ce-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="4d3ce-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="4d3ce-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="4d3ce-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1793">scheda della banca</span></span> 
- <span data-ttu-id="4d3ce-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1794">scheda di controllo</span></span> 
- <span data-ttu-id="4d3ce-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1795">scheda di debito</span></span> 
- <span data-ttu-id="4d3ce-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1796">scheda matrice</span></span> 
- <span data-ttu-id="4d3ce-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="4d3ce-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1798">schede di controllo</span></span> 
- <span data-ttu-id="4d3ce-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1799">schede di debito</span></span> 
- <span data-ttu-id="4d3ce-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1800">schede matrici</span></span> 
- <span data-ttu-id="4d3ce-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="4d3ce-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1802">scoprono le schede</span></span> 
- <span data-ttu-id="4d3ce-1803">individual</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1803">solo</span></span> 
- <span data-ttu-id="4d3ce-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1804">supporti di scheda</span></span> 
- <span data-ttu-id="4d3ce-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1805">supporto di scheda</span></span> 
- <span data-ttu-id="4d3ce-1806">Vá</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1806">switch</span></span> 
- <span data-ttu-id="4d3ce-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1807">tarjeta atm</span></span> 
- <span data-ttu-id="4d3ce-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1808">tarjeta credito</span></span> 
- <span data-ttu-id="4d3ce-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="4d3ce-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="4d3ce-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="4d3ce-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1812">tarjeta debito</span></span> 
- <span data-ttu-id="4d3ce-1813">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1813">tarjeta no</span></span>
- <span data-ttu-id="4d3ce-1814">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="4d3ce-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1815">tipo della scheda</span></span> 
- <span data-ttu-id="4d3ce-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="4d3ce-1817">scheda</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1817">scheda</span></span> 
- <span data-ttu-id="4d3ce-1818">v pay</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1818">v pay</span></span> 
- <span data-ttu-id="4d3ce-1819">v-Pay</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1819">v-pay</span></span> 
- <span data-ttu-id="4d3ce-1820">cartões</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1820">visa</span></span> 
- <span data-ttu-id="4d3ce-1821">visa plus</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1821">visa plus</span></span> 
- <span data-ttu-id="4d3ce-1822">visa electron</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1822">visa electron</span></span> 
- <span data-ttu-id="4d3ce-1823">previsto</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1823">visto</span></span> 
- <span data-ttu-id="4d3ce-1824">visum</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1824">visum</span></span> 
- <span data-ttu-id="4d3ce-1825">vpay</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1825">vpay</span></span>   

#### <a name="keyword_card_security_terms_dict"></a><span data-ttu-id="4d3ce-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="4d3ce-1827">card identification number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1827">card identification number</span></span>
- <span data-ttu-id="4d3ce-1828">card verification</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1828">card verification</span></span> 
- <span data-ttu-id="4d3ce-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1829">cardi la verifica</span></span> 
- <span data-ttu-id="4d3ce-1830">CID</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1830">cid</span></span> 
- <span data-ttu-id="4d3ce-1831">cod seg</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1831">cod seg</span></span> 
- <span data-ttu-id="4d3ce-1832">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1832">cod seguranca</span></span> 
- <span data-ttu-id="4d3ce-1833">cod segurança</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1833">cod segurança</span></span> 
- <span data-ttu-id="4d3ce-1834">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1834">cod sicurezza</span></span> 
- <span data-ttu-id="4d3ce-1835">COD.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1835">cod.</span></span> <span data-ttu-id="4d3ce-1836">seg</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1836">seg</span></span> 
- <span data-ttu-id="4d3ce-1837">COD.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1837">cod.</span></span> <span data-ttu-id="4d3ce-1838">seguranca</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1838">seguranca</span></span> 
- <span data-ttu-id="4d3ce-1839">COD.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1839">cod.</span></span> <span data-ttu-id="4d3ce-1840">segurança</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1840">segurança</span></span> 
- <span data-ttu-id="4d3ce-1841">COD.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1841">cod.</span></span> <span data-ttu-id="4d3ce-1842">sicurezza</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1842">sicurezza</span></span> 
- <span data-ttu-id="4d3ce-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="4d3ce-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1844">codice di verifica</span></span> 
- <span data-ttu-id="4d3ce-1845">codigo</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1845">codigo</span></span> 
- <span data-ttu-id="4d3ce-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="4d3ce-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1847">codigo de segurança</span></span> 
- <span data-ttu-id="4d3ce-1848">crittogramma</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1848">crittogramma</span></span> 
- <span data-ttu-id="4d3ce-1849">cryptogram</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1849">cryptogram</span></span> 
- <span data-ttu-id="4d3ce-1850">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1850">cryptogramme</span></span> 
- <span data-ttu-id="4d3ce-1851">cv2</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1851">cv2</span></span> 
- <span data-ttu-id="4d3ce-1852">cvc</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1852">cvc</span></span> 
- <span data-ttu-id="4d3ce-1853">cvc2</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1853">cvc2</span></span> 
- <span data-ttu-id="4d3ce-1854">cvn</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1854">cvn</span></span> 
- <span data-ttu-id="4d3ce-1855">cvv</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1855">cvv</span></span> 
- <span data-ttu-id="4d3ce-1856">cvv2</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1856">cvv2</span></span> 
- <span data-ttu-id="4d3ce-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1857">cód seguranca</span></span> 
- <span data-ttu-id="4d3ce-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1858">cód segurança</span></span> 
- <span data-ttu-id="4d3ce-1859">cód.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1859">cód.</span></span> <span data-ttu-id="4d3ce-1860">seguranca</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1860">seguranca</span></span> 
- <span data-ttu-id="4d3ce-1861">cód.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1861">cód.</span></span> <span data-ttu-id="4d3ce-1862">segurança</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1862">segurança</span></span> 
- <span data-ttu-id="4d3ce-1863">CFOP</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1863">código</span></span> 
- <span data-ttu-id="4d3ce-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1864">código de seguranca</span></span> 
- <span data-ttu-id="4d3ce-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1865">código de segurança</span></span> 
- <span data-ttu-id="4d3ce-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1866">de kaart controle</span></span> 
- <span data-ttu-id="4d3ce-1867">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1867">geeft nr uit</span></span> 
- <span data-ttu-id="4d3ce-1868">issue no</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1868">issue no</span></span> 
- <span data-ttu-id="4d3ce-1869">issue number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1869">issue number</span></span> 
- <span data-ttu-id="4d3ce-1870">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="4d3ce-1871">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="4d3ce-1872">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="4d3ce-1873">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1873">kwestieaantal</span></span> 
- <span data-ttu-id="4d3ce-1874">Não.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1874">no.</span></span> <span data-ttu-id="4d3ce-1875">dell'edizione</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1875">dell'edizione</span></span> 
- <span data-ttu-id="4d3ce-1876">Não.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1876">no.</span></span> <span data-ttu-id="4d3ce-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1877">di sicurezza</span></span> 
- <span data-ttu-id="4d3ce-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1878">numero de securite</span></span> 
- <span data-ttu-id="4d3ce-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1879">numero de verificacao</span></span> 
- <span data-ttu-id="4d3ce-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="4d3ce-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="4d3ce-1882">scheda</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1882">scheda</span></span> 
- <span data-ttu-id="4d3ce-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="4d3ce-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="4d3ce-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="4d3ce-1886">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="4d3ce-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1887">número de verificação</span></span> 
- <span data-ttu-id="4d3ce-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1888">perno il blocco</span></span> 
- <span data-ttu-id="4d3ce-1889">pin block</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1889">pin block</span></span> 
- <span data-ttu-id="4d3ce-1890">prufziffer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1890">prufziffer</span></span> 
- <span data-ttu-id="4d3ce-1891">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1891">prüfziffer</span></span> 
- <span data-ttu-id="4d3ce-1892">security code</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1892">security code</span></span> 
- <span data-ttu-id="4d3ce-1893">security no</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1893">security no</span></span> 
- <span data-ttu-id="4d3ce-1894">security number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1894">security number</span></span> 
- <span data-ttu-id="4d3ce-1895">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1895">sicherheits kode</span></span> 
- <span data-ttu-id="4d3ce-1896">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1896">sicherheitscode</span></span> 
- <span data-ttu-id="4d3ce-1897">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="4d3ce-1898">speldblok</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1898">speldblok</span></span> 
- <span data-ttu-id="4d3ce-1899">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1899">veiligheid nr</span></span> 
- <span data-ttu-id="4d3ce-1900">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="4d3ce-1901">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1901">veiligheidscode</span></span> 
- <span data-ttu-id="4d3ce-1902">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="4d3ce-1903">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1903">verfalldatum</span></span> 

#### <a name="keyword_card_expiration_terms_dict"></a><span data-ttu-id="4d3ce-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="4d3ce-1905">ablauf</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1905">ablauf</span></span> 
- <span data-ttu-id="4d3ce-1906">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1906">data de expiracao</span></span> 
- <span data-ttu-id="4d3ce-1907">data de expiração</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1907">data de expiração</span></span> 
- <span data-ttu-id="4d3ce-1908">data del exp</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1908">data del exp</span></span> 
- <span data-ttu-id="4d3ce-1909">data di exp</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1909">data di exp</span></span> 
- <span data-ttu-id="4d3ce-1910">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1910">data di scadenza</span></span> 
- <span data-ttu-id="4d3ce-1911">data em que expira</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1911">data em que expira</span></span> 
- <span data-ttu-id="4d3ce-1912">data scad</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1912">data scad</span></span> 
- <span data-ttu-id="4d3ce-1913">data scadenza</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1913">data scadenza</span></span> 
- <span data-ttu-id="4d3ce-1914">date de validité</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1914">date de validité</span></span> 
- <span data-ttu-id="4d3ce-1915">datum afloop</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1915">datum afloop</span></span> 
- <span data-ttu-id="4d3ce-1916">datum van exp</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1916">datum van exp</span></span> 
- <span data-ttu-id="4d3ce-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1917">de afloop</span></span> 
- <span data-ttu-id="4d3ce-1918">espira</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1918">espira</span></span> 
- <span data-ttu-id="4d3ce-1919">espira</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1919">espira</span></span> 
- <span data-ttu-id="4d3ce-1920">exp date</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1920">exp date</span></span> 
- <span data-ttu-id="4d3ce-1921">exp datum</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1921">exp datum</span></span> 
- <span data-ttu-id="4d3ce-1922">validade</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1922">expiration</span></span> 
- <span data-ttu-id="4d3ce-1923">expirar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1923">expire</span></span> 
- <span data-ttu-id="4d3ce-1924">expira</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1924">expires</span></span> 
- <span data-ttu-id="4d3ce-1925">expiração</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1925">expiry</span></span> 
- <span data-ttu-id="4d3ce-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="4d3ce-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1927">fecha de venc</span></span> 
- <span data-ttu-id="4d3ce-1928">gultig bis</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1928">gultig bis</span></span> 
- <span data-ttu-id="4d3ce-1929">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="4d3ce-1930">gültig bis</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1930">gültig bis</span></span> 
- <span data-ttu-id="4d3ce-1931">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="4d3ce-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1932">la scadenza</span></span> 
- <span data-ttu-id="4d3ce-1933">scadenza</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1933">scadenza</span></span> 
- <span data-ttu-id="4d3ce-1934">valable</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1934">valable</span></span> 
- <span data-ttu-id="4d3ce-1935">validade</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1935">validade</span></span> 
- <span data-ttu-id="4d3ce-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1936">valido hasta</span></span> 
- <span data-ttu-id="4d3ce-1937">coragem</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1937">valor</span></span> 
- <span data-ttu-id="4d3ce-1938">venc</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1938">venc</span></span> 
- <span data-ttu-id="4d3ce-1939">vencimento</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1939">vencimento</span></span> 
- <span data-ttu-id="4d3ce-1940">vencimiento</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1940">vencimiento</span></span> 
- <span data-ttu-id="4d3ce-1941">verloopt</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1941">verloopt</span></span> 
- <span data-ttu-id="4d3ce-1942">vervaldag</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1942">vervaldag</span></span> 
- <span data-ttu-id="4d3ce-1943">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1943">vervaldatum</span></span> 
- <span data-ttu-id="4d3ce-1944">vto</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1944">vto</span></span> 
- <span data-ttu-id="4d3ce-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="4d3ce-1946">Número da carteira de motorista da UE</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1946">EU Driver's License Number</span></span>

<span data-ttu-id="4d3ce-1947">Para saber mais, confira o [tipo de informação confidencial do número da carteira de motorista da UE](eu-driver-s-license-number.md).</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="4d3ce-1948">Número de identificação nacional da UE</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1948">EU National Identification Number</span></span>

<span data-ttu-id="4d3ce-1949">Para saber mais, confira [tipo de informação confidencial do número de identificação nacional da UE](eu-national-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="4d3ce-1950">Número do Passport da UE</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1950">EU Passport Number</span></span>

<span data-ttu-id="4d3ce-1951">Para saber mais, veja [tipo de informações confidenciais do número do Passport da UE](eu-passport-number.md).</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="4d3ce-1952">Número de seguro social da UE ou ID equivalente</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="4d3ce-1953">Para saber mais, confira [número de seguridade social da UE ou tipo de informação confidencial de ID equivalente](eu-social-security-number-or-equivalent-id.md).</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="4d3ce-1954">Número de identificação do imposto da UE</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="4d3ce-1955">Para saber mais, confira [número de identificação de imposto da UE tipo de informação confidencial](eu-tax-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="4d3ce-1956">ID nacional da Finlândia</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-1957">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1957">Format</span></span>

<span data-ttu-id="4d3ce-1958">Seis dígitos mais um caractere indicando um século mais três dígitos mais um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-1959">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1959">Pattern</span></span>

<span data-ttu-id="4d3ce-1960">O padrão deve incluir todos os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="4d3ce-1961">Seis dígitos no formato DDMMAA que é uma data de nascimento</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="4d3ce-1962">Marcador do século (qualquer '-', '+' ou 'a')</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="4d3ce-1963">Número de identificação pessoal de três dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="4d3ce-1964">Um dígito ou letra (não diferencia maiúscula de minúscula), que é um dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-1965">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1965">Checksum</span></span>

<span data-ttu-id="4d3ce-1966">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-1967">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1967">Definition</span></span>

<span data-ttu-id="4d3ce-1968">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-1969">A função Func_finnish_national_id localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-1970">Uma palavra-chave de Keyword_finnish_national_id for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="4d3ce-1971">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1971">The checksum passes.</span></span>

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-1972">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1972">Keywords</span></span>

- <span data-ttu-id="4d3ce-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="4d3ce-1974">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="4d3ce-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="4d3ce-1976">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1976">Personbeteckning</span></span>
- <span data-ttu-id="4d3ce-1977">Personnummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="4d3ce-1978">Número de Passaporte da Finlândia</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1978">Finland Passport Number</span></span>

<span data-ttu-id="4d3ce-1979">Combinação de formato de nove letras e dígitos combinação de padrões de nove letras e dígitos: duas letras (não diferencia maiúsculas de minúsculas) sete dígitos soma de verificação sem definição uma política de DLP é de 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de um proximidade de 300 caracteres: a expressão regular Regex_finland_passport_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1979">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="4d3ce-1980">Uma palavra-chave de Keyword_finland_passport_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1980">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
<span data-ttu-id="4d3ce-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="4d3ce-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span></span>
<span data-ttu-id="4d3ce-1982">Palavras-chave Keyword_finland_passport_number Passport Passi</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1982">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="4d3ce-1983">Número de carteira de motorista da França</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1983">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-1984">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1984">Format</span></span>

<span data-ttu-id="4d3ce-1985">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1985">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-1986">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1986">Pattern</span></span>

<span data-ttu-id="4d3ce-1987">12 dígitos com a validação para descontar padrões similares, como números de telefone em francês</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1987">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-1988">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1988">Checksum</span></span>

<span data-ttu-id="4d3ce-1989">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1989">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-1990">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1990">Definition</span></span>

<span data-ttu-id="4d3ce-1991">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1991">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-1992">A função Func_french_drivers_license localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1992">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-1993">Pelo menos uma das seguintes opções for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1993">At least one of the following is true:</span></span>
- <span data-ttu-id="4d3ce-1994">Uma palavra-chave de Keyword_french_drivers_license for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1994">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="4d3ce-1995">A função Func_eu_date encontra uma data no formato de data à direita.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1995">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-1996">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1996">Keywords</span></span>

#### <a name="keyword_french_drivers_license"></a><span data-ttu-id="4d3ce-1997">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1997">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="4d3ce-1998">drivers licence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1998">drivers licence</span></span>
- <span data-ttu-id="4d3ce-1999">drivers license</span><span class="sxs-lookup"><span data-stu-id="4d3ce-1999">drivers license</span></span>
- <span data-ttu-id="4d3ce-2000">driving licence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2000">driving licence</span></span>
- <span data-ttu-id="4d3ce-2001">driving licence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2001">driving license</span></span>
- <span data-ttu-id="4d3ce-2002">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2002">permis de conduire</span></span>
- <span data-ttu-id="4d3ce-2003">licence number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2003">licence number</span></span>
- <span data-ttu-id="4d3ce-2004">license number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2004">license number</span></span>
- <span data-ttu-id="4d3ce-2005">licence numbers</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2005">licence numbers</span></span>
- <span data-ttu-id="4d3ce-2006">license numbers</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2006">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="4d3ce-2007">Cartão de identificação nacional da França (CNI)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2007">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2008">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2008">Format</span></span>

<span data-ttu-id="4d3ce-2009">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2009">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2010">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2010">Pattern</span></span>

<span data-ttu-id="4d3ce-2011">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2011">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2012">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2012">Checksum</span></span>

<span data-ttu-id="4d3ce-2013">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2013">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2014">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2014">Definition</span></span>

<span data-ttu-id="4d3ce-2015">Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2015">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2016">A expressão regular Regex_france_cni localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2016">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-2017">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2017">Keywords</span></span>

<span data-ttu-id="4d3ce-2018">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2018">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="4d3ce-2019">Número de passaporte da França</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2019">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2020">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2020">Format</span></span>

<span data-ttu-id="4d3ce-2021">Nove letras e dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2021">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2022">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2022">Pattern</span></span>

<span data-ttu-id="4d3ce-2023">Nove letras e dígitos:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2023">Nine digits and letters:</span></span>
- <span data-ttu-id="4d3ce-2024">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2024">Two digits</span></span> 
- <span data-ttu-id="4d3ce-2025">Duas letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2025">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="4d3ce-2026">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2026">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2027">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2027">Checksum</span></span>

<span data-ttu-id="4d3ce-2028">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2028">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2029">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2029">Definition</span></span>

<span data-ttu-id="4d3ce-2030">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2030">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2031">A função Func_fr_passport localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2031">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2032">Uma palavra-chave de Keyword_passport for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2032">A keyword from Keyword_passport is found.</span></span>

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-2033">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2033">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="4d3ce-2034">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2034">Keyword_passport</span></span>

- <span data-ttu-id="4d3ce-2035">Passport Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2035">Passport Number</span></span>
- <span data-ttu-id="4d3ce-2036">Passport No</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2036">Passport No</span></span>
- <span data-ttu-id="4d3ce-2037">Passport #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2037">Passport #</span></span>
- <span data-ttu-id="4d3ce-2038">Passaport #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2038">Passport#</span></span>
- <span data-ttu-id="4d3ce-2039">Passportid</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2039">PassportID</span></span>
- <span data-ttu-id="4d3ce-2040">Passportno</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2040">Passportno</span></span>
- <span data-ttu-id="4d3ce-2041">passportnumber</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2041">passportnumber</span></span>
- <span data-ttu-id="4d3ce-2042">パスポート</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2042">パスポート</span></span>
- <span data-ttu-id="4d3ce-2043">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2043">パスポート番号</span></span>
- <span data-ttu-id="4d3ce-2044">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2044">パスポートのNum</span></span>
- <span data-ttu-id="4d3ce-2045">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2045">パスポート ＃</span></span> 
- <span data-ttu-id="4d3ce-2046">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2046">Numéro de passeport</span></span>
- <span data-ttu-id="4d3ce-2047">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2047">Passeport n °</span></span>
- <span data-ttu-id="4d3ce-2048">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2048">Passeport Non</span></span>
- <span data-ttu-id="4d3ce-2049">Passeport #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2049">Passeport #</span></span>
- <span data-ttu-id="4d3ce-2050">Passeport #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2050">Passeport#</span></span>
- <span data-ttu-id="4d3ce-2051">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2051">PasseportNon</span></span>
- <span data-ttu-id="4d3ce-2052">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2052">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="4d3ce-2053">Número de seguridade social da França (INSEE)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2053">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2054">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2054">Format</span></span>

<span data-ttu-id="4d3ce-2055">15 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2055">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2056">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2056">Pattern</span></span>

<span data-ttu-id="4d3ce-2057">Deve corresponder a um dos dois padrões:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2057">Must match one of two patterns:</span></span>
- <span data-ttu-id="4d3ce-2058">13 dígitos seguidos de um espaço seguido de dois dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2058">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="4d3ce-2059">ou</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2059">or</span></span>
- <span data-ttu-id="4d3ce-2060">15 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2060">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2061">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2061">Checksum</span></span>

<span data-ttu-id="4d3ce-2062">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2062">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2063">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2063">Definition</span></span>

<span data-ttu-id="4d3ce-2064">Uma política de DLP tem 95% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2064">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2065">A função Func_french_insee ou Func_fr_insee localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2065">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2066">Uma palavra-chave de Keyword_fr_insee for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2066">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="4d3ce-2067">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2067">The checksum passes.</span></span>

<span data-ttu-id="4d3ce-2068">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2068">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2069">A função Func_french_insee ou Func_fr_insee localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2069">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2070">Nenhuma palavra-chave de Keyword_fr_insee for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2070">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="4d3ce-2071">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2071">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-2072">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2072">Keywords</span></span>

#### <a name="keyword_fr_insee"></a><span data-ttu-id="4d3ce-2073">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2073">Keyword_fr_insee</span></span>

- <span data-ttu-id="4d3ce-2074">INSEE</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2074">insee</span></span>
- <span data-ttu-id="4d3ce-2075">securité sociale</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2075">securité sociale</span></span>
- <span data-ttu-id="4d3ce-2076">securite sociale</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2076">securite sociale</span></span>
- <span data-ttu-id="4d3ce-2077">national id</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2077">national id</span></span>
- <span data-ttu-id="4d3ce-2078">national identification</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2078">national identification</span></span>
- <span data-ttu-id="4d3ce-2079">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2079">numéro d'identité</span></span>
- <span data-ttu-id="4d3ce-2080">no d'identité</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2080">no d'identité</span></span>
- <span data-ttu-id="4d3ce-2081">Não.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2081">no.</span></span> <span data-ttu-id="4d3ce-2082">d'identité</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2082">d'identité</span></span>
- <span data-ttu-id="4d3ce-2083">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2083">numero d'identite</span></span>
- <span data-ttu-id="4d3ce-2084">no d'identite</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2084">no d'identite</span></span>
- <span data-ttu-id="4d3ce-2085">Não.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2085">no.</span></span> <span data-ttu-id="4d3ce-2086">d'identite</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2086">d'identite</span></span>
- <span data-ttu-id="4d3ce-2087">social security number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2087">social security number</span></span>
- <span data-ttu-id="4d3ce-2088">social security code</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2088">social security code</span></span>
- <span data-ttu-id="4d3ce-2089">social insurance number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2089">social insurance number</span></span>
- <span data-ttu-id="4d3ce-2090">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2090">le numéro d'identification nationale</span></span>
- <span data-ttu-id="4d3ce-2091">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2091">d'identité nationale</span></span>
- <span data-ttu-id="4d3ce-2092">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2092">numéro de sécurité sociale</span></span>
- <span data-ttu-id="4d3ce-2093">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2093">le code de la sécurité sociale</span></span>
- <span data-ttu-id="4d3ce-2094">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2094">numéro d'assurance sociale</span></span>
- <span data-ttu-id="4d3ce-2095">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2095">numéro de sécu</span></span>
- <span data-ttu-id="4d3ce-2096">code sécu</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2096">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="4d3ce-2097">Número de carteira de motorista da Alemanha</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2097">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2098">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2098">Format</span></span>

<span data-ttu-id="4d3ce-2099">Combinação de 11 dígitos e letras</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2099">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2100">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2100">Pattern</span></span>

<span data-ttu-id="4d3ce-2101">11 dígitos e letras (não diferenciam maiúsculas de minúsculas):</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2101">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="4d3ce-2102">Um dígito ou letra</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2102">A digit or letter</span></span> 
- <span data-ttu-id="4d3ce-2103">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2103">Two digits</span></span> 
- <span data-ttu-id="4d3ce-2104">Seis dígitos ou letras</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2104">Six digits or letters</span></span> 
- <span data-ttu-id="4d3ce-2105">Um dígito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2105">A digit</span></span> 
- <span data-ttu-id="4d3ce-2106">Um dígito ou letra</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2106">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2107">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2107">Checksum</span></span>

<span data-ttu-id="4d3ce-2108">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2108">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2109">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2109">Definition</span></span>

<span data-ttu-id="4d3ce-2110">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2110">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2111">A função Func_german_drivers_license localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2111">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2112">Pelo menos uma das seguintes opções for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2112">At least one of the following is true:</span></span>
    - <span data-ttu-id="4d3ce-2113">Uma palavra-chave de Keyword_german_drivers_license_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2113">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="4d3ce-2114">Uma palavra-chave de Keyword_german_drivers_license_collaborative for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2114">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="4d3ce-2115">Uma palavra-chave de Keyword_german_drivers_license for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2115">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="4d3ce-2116">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2116">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-2117">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2117">Keywords</span></span>

#### <a name="keyword_german_drivers_license_number"></a><span data-ttu-id="4d3ce-2118">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2118">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="4d3ce-2119">Führerschein</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2119">Führerschein</span></span>
- <span data-ttu-id="4d3ce-2120">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2120">Fuhrerschein</span></span>
- <span data-ttu-id="4d3ce-2121">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2121">Fuehrerschein</span></span>
- <span data-ttu-id="4d3ce-2122">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2122">Führerscheinnummer</span></span>
- <span data-ttu-id="4d3ce-2123">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2123">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="4d3ce-2124">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2124">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="4d3ce-2125">Führerschein-</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2125">Führerschein-</span></span> 
- <span data-ttu-id="4d3ce-2126">Fuhrerschein-</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2126">Fuhrerschein-</span></span> 
- <span data-ttu-id="4d3ce-2127">Fuehrerschein-</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2127">Fuehrerschein-</span></span> 
- <span data-ttu-id="4d3ce-2128">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2128">FührerscheinnummerNr</span></span>
- <span data-ttu-id="4d3ce-2129">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2129">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="4d3ce-2130">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2130">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="4d3ce-2131">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2131">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="4d3ce-2132">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2132">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="4d3ce-2133">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2133">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="4d3ce-2134">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2134">Führerschein- Nr</span></span>
- <span data-ttu-id="4d3ce-2135">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2135">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="4d3ce-2136">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2136">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="4d3ce-2137">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2137">Führerschein- Klasse</span></span> 
- <span data-ttu-id="4d3ce-2138">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2138">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="4d3ce-2139">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2139">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="4d3ce-2140">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2140">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="4d3ce-2141">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2141">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="4d3ce-2142">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2142">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="4d3ce-2143">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2143">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="4d3ce-2144">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2144">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="4d3ce-2145">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2145">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="4d3ce-2146">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2146">Führerschein- Nr</span></span> 
- <span data-ttu-id="4d3ce-2147">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2147">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="4d3ce-2148">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2148">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="4d3ce-2149">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2149">Führerschein- Klasse</span></span> 
- <span data-ttu-id="4d3ce-2150">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2150">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="4d3ce-2151">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2151">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="4d3ce-2152">DISTRIBUIÇÃO</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2152">DL</span></span> 
- <span data-ttu-id="4d3ce-2153">DL</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2153">DLS</span></span>
- <span data-ttu-id="4d3ce-2154">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2154">Driv Lic</span></span> 
- <span data-ttu-id="4d3ce-2155">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2155">Driv Licen</span></span> 
- <span data-ttu-id="4d3ce-2156">Driv License</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2156">Driv License</span></span>
- <span data-ttu-id="4d3ce-2157">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2157">Driv Licenses</span></span> 
- <span data-ttu-id="4d3ce-2158">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2158">Driv Licence</span></span> 
- <span data-ttu-id="4d3ce-2159">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2159">Driv Licences</span></span> 
- <span data-ttu-id="4d3ce-2160">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2160">Driv Lic</span></span> 
- <span data-ttu-id="4d3ce-2161">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2161">Driver Licen</span></span> 
- <span data-ttu-id="4d3ce-2162">Driver License</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2162">Driver License</span></span> 
- <span data-ttu-id="4d3ce-2163">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2163">Driver Licenses</span></span> 
- <span data-ttu-id="4d3ce-2164">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2164">Driver Licence</span></span> 
- <span data-ttu-id="4d3ce-2165">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2165">Driver Licences</span></span> 
- <span data-ttu-id="4d3ce-2166">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2166">Drivers Lic</span></span> 
- <span data-ttu-id="4d3ce-2167">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2167">Drivers Licen</span></span> 
- <span data-ttu-id="4d3ce-2168">Drivers License</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2168">Drivers License</span></span> 
- <span data-ttu-id="4d3ce-2169">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2169">Drivers Licenses</span></span> 
- <span data-ttu-id="4d3ce-2170">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2170">Drivers Licence</span></span> 
- <span data-ttu-id="4d3ce-2171">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2171">Drivers Licences</span></span> 
- <span data-ttu-id="4d3ce-2172">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2172">Driver's Lic</span></span> 
- <span data-ttu-id="4d3ce-2173">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2173">Driver's Licen</span></span> 
- <span data-ttu-id="4d3ce-2174">Driver's License</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2174">Driver's License</span></span> 
- <span data-ttu-id="4d3ce-2175">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2175">Driver's Licenses</span></span> 
- <span data-ttu-id="4d3ce-2176">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2176">Driver's Licence</span></span> 
- <span data-ttu-id="4d3ce-2177">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2177">Driver's Licences</span></span> 
- <span data-ttu-id="4d3ce-2178">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2178">Driving Lic</span></span> 
- <span data-ttu-id="4d3ce-2179">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2179">Driving Licen</span></span> 
- <span data-ttu-id="4d3ce-2180">Driving License</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2180">Driving License</span></span> 
- <span data-ttu-id="4d3ce-2181">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2181">Driving Licenses</span></span> 
- <span data-ttu-id="4d3ce-2182">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2182">Driving Licence</span></span> 
- <span data-ttu-id="4d3ce-2183">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2183">Driving Licences</span></span>

#### <a name="keyword_german_drivers_license_collaborative"></a><span data-ttu-id="4d3ce-2184">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2184">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="4d3ce-2185">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2185">Nr-Führerschein</span></span> 
- <span data-ttu-id="4d3ce-2186">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2186">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="4d3ce-2187">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2187">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="4d3ce-2188">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2188">No-Führerschein</span></span> 
- <span data-ttu-id="4d3ce-2189">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2189">No-Fuhrerschein</span></span> 
- <span data-ttu-id="4d3ce-2190">No-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2190">No-Fuehrerschein</span></span> 
- <span data-ttu-id="4d3ce-2191">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2191">N-Führerschein</span></span> 
- <span data-ttu-id="4d3ce-2192">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2192">N-Fuhrerschein</span></span> 
- <span data-ttu-id="4d3ce-2193">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2193">N-Fuehrerschein</span></span>
- <span data-ttu-id="4d3ce-2194">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2194">Nr-Führerschein</span></span> 
- <span data-ttu-id="4d3ce-2195">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2195">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="4d3ce-2196">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2196">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="4d3ce-2197">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2197">No-Führerschein</span></span> 
- <span data-ttu-id="4d3ce-2198">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2198">No-Fuhrerschein</span></span> 
- <span data-ttu-id="4d3ce-2199">No-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2199">No-Fuehrerschein</span></span> 
- <span data-ttu-id="4d3ce-2200">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2200">N-Führerschein</span></span> 
- <span data-ttu-id="4d3ce-2201">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2201">N-Fuhrerschein</span></span> 
- <span data-ttu-id="4d3ce-2202">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2202">N-Fuehrerschein</span></span> 

#### <a name="keyword_german_drivers_license"></a><span data-ttu-id="4d3ce-2203">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2203">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="4d3ce-2204">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2204">ausstellungsdatum</span></span>
- <span data-ttu-id="4d3ce-2205">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2205">ausstellungsort</span></span>
- <span data-ttu-id="4d3ce-2206">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2206">ausstellende behöde</span></span>
- <span data-ttu-id="4d3ce-2207">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2207">ausstellende behorde</span></span>
- <span data-ttu-id="4d3ce-2208">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2208">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="4d3ce-2209">Número de passaporte da Alemanha</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2209">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2210">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2210">Format</span></span>

<span data-ttu-id="4d3ce-2211">10 dígitos ou letras</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2211">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2212">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2212">Pattern</span></span>

<span data-ttu-id="4d3ce-2213">O padrão deve incluir todos os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2213">Pattern must include all of the following:</span></span>
- <span data-ttu-id="4d3ce-2214">Primeiro caractere é um dígito ou uma letra desse conjunto (C, F, G, H, J, K)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2214">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="4d3ce-2215">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2215">Three digits</span></span> 
- <span data-ttu-id="4d3ce-2216">Cinco dígitos ou letras a partir desse conjunto (C, -H, J N, P, R, T, V-Z)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2216">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="4d3ce-2217">Um dígito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2217">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2218">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2218">Checksum</span></span>

<span data-ttu-id="4d3ce-2219">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2219">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2220">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2220">Definition</span></span>

<span data-ttu-id="4d3ce-2221">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2221">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2222">A função Func_german_passport localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2222">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2223">Uma palavra-chave de qualquer uma das cinco listas de palavras-chave for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2223">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="4d3ce-2224">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2224">The checksum passes.</span></span>

<span data-ttu-id="4d3ce-2225">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2226">A função Func_german_passport_data localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2226">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2227">Uma palavra-chave de qualquer uma das cinco listas de palavras-chave for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2227">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="4d3ce-2228">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2228">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-2229">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2229">Keywords</span></span>

#### <a name="keyword_german_passport"></a><span data-ttu-id="4d3ce-2230">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2230">Keyword_german_passport</span></span>

- <span data-ttu-id="4d3ce-2231">reisepass</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2231">reisepass</span></span>
- <span data-ttu-id="4d3ce-2232">reisepasse</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2232">reisepasse</span></span>
- <span data-ttu-id="4d3ce-2233">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2233">reisepassnummer</span></span>
- <span data-ttu-id="4d3ce-2234">Passaport</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2234">passport</span></span>
- <span data-ttu-id="4d3ce-2235">Passports</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2235">passports</span></span>

#### <a name="keyword_german_passport_collaborative"></a><span data-ttu-id="4d3ce-2236">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2236">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="4d3ce-2237">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2237">geburtsdatum</span></span>
- <span data-ttu-id="4d3ce-2238">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2238">ausstellungsdatum</span></span>
- <span data-ttu-id="4d3ce-2239">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2239">ausstellungsort</span></span>

#### <a name="keyword_german_passport_number"></a><span data-ttu-id="4d3ce-2240">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2240">Keyword_german_passport_number</span></span>

<span data-ttu-id="4d3ce-2241">No-Reisepass NR-Reisepass</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2241">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keyword_german_passport1"></a><span data-ttu-id="4d3ce-2242">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2242">Keyword_german_passport1</span></span>

<span data-ttu-id="4d3ce-2243">Reisepass-Nr</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2243">Reisepass-Nr</span></span>

#### <a name="keyword_german_passport2"></a><span data-ttu-id="4d3ce-2244">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2244">Keyword_german_passport2</span></span>

<span data-ttu-id="4d3ce-2245">bnationalit. t</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2245">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="4d3ce-2246">Número da carteira de identidade alemã</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2246">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2247">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2247">Format</span></span>

<span data-ttu-id="4d3ce-2248">Desde 1 de novembro de 2010: nove letras e dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2248">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="4d3ce-2249">De 1 de abril de 1987 até 31 de outubro de 2010:10 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2249">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2250">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2250">Pattern</span></span>

<span data-ttu-id="4d3ce-2251">Desde 1º de novembro de 2010:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2251">Since 1 November 2010:</span></span>
- <span data-ttu-id="4d3ce-2252">Uma letra (não diferencia maiúscula de minúscula)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2252">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="4d3ce-2253">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2253">Eight digits</span></span>

<span data-ttu-id="4d3ce-2254">De 1 de abril de 1987 até 31 de outubro de 2010:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2254">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="4d3ce-2255">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2255">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2256">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2256">Checksum</span></span>

<span data-ttu-id="4d3ce-2257">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2257">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2258">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2258">Definition</span></span>

<span data-ttu-id="4d3ce-2259">Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2259">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2260">A expressão regular Regex_germany_id_card localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2260">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2261">Uma palavra-chave de Keyword_germany_id_card for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2261">A keyword from Keyword_germany_id_card is found.</span></span>

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-2262">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2262">Keywords</span></span>

#### <a name="keyword_germany_id_card"></a><span data-ttu-id="4d3ce-2263">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2263">Keyword_germany_id_card</span></span>

- <span data-ttu-id="4d3ce-2264">Cartão de Identidade</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2264">Identity Card</span></span>
- <span data-ttu-id="4d3ce-2265">ID</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2265">ID</span></span>
- <span data-ttu-id="4d3ce-2266">Identificador</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2266">Identification</span></span>
- <span data-ttu-id="4d3ce-2267">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2267">Personalausweis</span></span>
- <span data-ttu-id="4d3ce-2268">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2268">Identifizierungsnummer</span></span>
- <span data-ttu-id="4d3ce-2269">Ausweis</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2269">Ausweis</span></span>
- <span data-ttu-id="4d3ce-2270">Identifikation</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2270">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="4d3ce-2271">Cartão de Identificação Nacional da Grécia</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2271">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2272">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2272">Format</span></span>

<span data-ttu-id="4d3ce-2273">Combinação de 7 a 8 letras e números mais um traço</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2273">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2274">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2274">Pattern</span></span>

<span data-ttu-id="4d3ce-2275">Sete letras e números (formato antigo):</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2275">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="4d3ce-2276">Uma letra (qualquer letra do alfabeto grego) </span><span class="sxs-lookup"><span data-stu-id="4d3ce-2276">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="4d3ce-2277">Um traço</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2277">A dash</span></span> 
- <span data-ttu-id="4d3ce-2278">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2278">Six digits</span></span>

<span data-ttu-id="4d3ce-2279">Oito letras e números (novo formato):</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2279">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="4d3ce-2280">Duas letras cujos caracteres maiúsculos ocorre em alfabetos latino e grego (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="4d3ce-2280">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="4d3ce-2281">Um traço</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2281">A dash</span></span> 
- <span data-ttu-id="4d3ce-2282">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2282">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2283">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2283">Checksum</span></span>

<span data-ttu-id="4d3ce-2284">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2284">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2285">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2285">Definition</span></span>

<span data-ttu-id="4d3ce-2286">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2286">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2287">A expressão regular Regex_greece_id_card localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2287">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2288">Uma palavra-chave de Keyword_greece_id_card for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2288">A keyword from Keyword_greece_id_card is found.</span></span>

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-2289">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2289">Keywords</span></span>

#### <a name="keyword_greece_id_card"></a><span data-ttu-id="4d3ce-2290">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2290">Keyword_greece_id_card</span></span>

- <span data-ttu-id="4d3ce-2291">Cartão de identidade grego</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2291">Greek identity Card</span></span>
- <span data-ttu-id="4d3ce-2292">Tautotita</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2292">Tautotita</span></span>
- <span data-ttu-id="4d3ce-2293">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2293">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="4d3ce-2294">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2294">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="4d3ce-2295">Número do Cartão de Identidade de Hong Kong (HKID)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2295">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2296">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2296">Format</span></span>

<span data-ttu-id="4d3ce-2297">Combinação de 8 a 9 letras e números mais parênteses opcionais ao redor do caractere final</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2297">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2298">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2298">Pattern</span></span>

<span data-ttu-id="4d3ce-2299">Combinação de 8 a 9 letras:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2299">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="4d3ce-2300">1 a 2 letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2300">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="4d3ce-2301">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2301">Six digits</span></span> 
- <span data-ttu-id="4d3ce-2302">O caractere final (qualquer dígito ou a letra A), que é o dígito de verificação e é opcionalmente colocado entre parênteses.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2302">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2303">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2303">Checksum</span></span>

<span data-ttu-id="4d3ce-2304">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2304">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2305">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2305">Definition</span></span>

<span data-ttu-id="4d3ce-2306">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2306">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2307">A função Func_hong_kong_id_card localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2307">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2308">Uma palavra-chave de Keyword_hong_kong_id_card for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2308">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="4d3ce-2309">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2309">The checksum passes.</span></span>

<span data-ttu-id="4d3ce-2310">Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2310">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2311">A função Func_hong_kong_id_card localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2311">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2312">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2312">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-2313">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2313">Keywords</span></span>

#### <a name="keyword_hong_kong_id_card"></a><span data-ttu-id="4d3ce-2314">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2314">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="4d3ce-2315">cartão de identidade de Hong Kong</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2315">hong kong identity card</span></span>
- <span data-ttu-id="4d3ce-2316">HKIDC</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2316">HKIDC</span></span>
- <span data-ttu-id="4d3ce-2317">id card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2317">id card</span></span>
- <span data-ttu-id="4d3ce-2318">cartão de identidade</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2318">identity card</span></span>
- <span data-ttu-id="4d3ce-2319">cartão de identidade HK</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2319">hk identity card</span></span>
- <span data-ttu-id="4d3ce-2320">ID de Hong Kong</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2320">hong kong id</span></span>
- <span data-ttu-id="4d3ce-2321">香港身份證</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2321">香港身份證</span></span>
- <span data-ttu-id="4d3ce-2322">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2322">香港永久性居民身份證</span></span>
- <span data-ttu-id="4d3ce-2323">身份證</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2323">身份證</span></span>
- <span data-ttu-id="4d3ce-2324">身份証</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2324">身份証</span></span>
- <span data-ttu-id="4d3ce-2325">身分證</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2325">身分證</span></span>
- <span data-ttu-id="4d3ce-2326">身分証</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2326">身分証</span></span>
- <span data-ttu-id="4d3ce-2327">香港身份証</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2327">香港身份証</span></span>
- <span data-ttu-id="4d3ce-2328">香港身分證</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2328">香港身分證</span></span>
- <span data-ttu-id="4d3ce-2329">香港身分証</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2329">香港身分証</span></span>
- <span data-ttu-id="4d3ce-2330">香港身份證</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2330">香港身份證</span></span>
- <span data-ttu-id="4d3ce-2331">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2331">香港居民身份證</span></span>
- <span data-ttu-id="4d3ce-2332">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2332">香港居民身份証</span></span>
- <span data-ttu-id="4d3ce-2333">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2333">香港居民身分證</span></span>
- <span data-ttu-id="4d3ce-2334">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2334">香港居民身分証</span></span>
- <span data-ttu-id="4d3ce-2335">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2335">香港永久性居民身份証</span></span>
- <span data-ttu-id="4d3ce-2336">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2336">香港永久性居民身分證</span></span>
- <span data-ttu-id="4d3ce-2337">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2337">香港永久性居民身分証</span></span>
- <span data-ttu-id="4d3ce-2338">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2338">香港永久性居民身份證</span></span>
- <span data-ttu-id="4d3ce-2339">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2339">香港非永久性居民身份證</span></span>
- <span data-ttu-id="4d3ce-2340">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2340">香港非永久性居民身份証</span></span>
- <span data-ttu-id="4d3ce-2341">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2341">香港非永久性居民身分證</span></span>
- <span data-ttu-id="4d3ce-2342">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2342">香港非永久性居民身分証</span></span>
- <span data-ttu-id="4d3ce-2343">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2343">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="4d3ce-2344">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2344">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="4d3ce-2345">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2345">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="4d3ce-2346">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2346">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="4d3ce-2347">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2347">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="4d3ce-2348">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2348">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="4d3ce-2349">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2349">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="4d3ce-2350">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2350">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="4d3ce-2351">Número da Conta Permanente da Índia (PAN)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2351">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2352">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2352">Format</span></span>

<span data-ttu-id="4d3ce-2353">10 letras ou dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2353">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2354">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2354">Pattern</span></span>

<span data-ttu-id="4d3ce-2355">10 letras ou dígitos.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2355">10 letters or digits:</span></span>
- <span data-ttu-id="4d3ce-2356">Cinco letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2356">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="4d3ce-2357">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2357">Four digits</span></span> 
- <span data-ttu-id="4d3ce-2358">Uma letra que é um dígito de verificação alfabético</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2358">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2359">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2359">Checksum</span></span>

<span data-ttu-id="4d3ce-2360">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2360">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2361">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2361">Definition</span></span>

<span data-ttu-id="4d3ce-2362">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2362">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2363">A expressão regular Regex_india_permanent_account_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2363">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2364">Uma palavra-chave de Keyword_india_permanent_account_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2364">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="4d3ce-2365">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2365">The checksum passes.</span></span>

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-2366">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2366">Keywords</span></span>

#### <a name="keyword_india_permanent_account_number"></a><span data-ttu-id="4d3ce-2367">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2367">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="4d3ce-2368">Número da Conta Permanente</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2368">Permanent Account Number</span></span> 
- <span data-ttu-id="4d3ce-2369">APLICAR</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2369">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="4d3ce-2370">Número de Identificação Exclusivo da Índia (Aadhaar)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2370">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2371">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2371">Format</span></span>

<span data-ttu-id="4d3ce-2372">12 dígitos contendo espaços opcionais ou traços</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2372">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2373">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2373">Pattern</span></span>

<span data-ttu-id="4d3ce-2374">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2374">12 digits:</span></span>
- <span data-ttu-id="4d3ce-2375">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2375">Four digits</span></span> 
- <span data-ttu-id="4d3ce-2376">Um espaço ou um traço opcional </span><span class="sxs-lookup"><span data-stu-id="4d3ce-2376">An optional space or dash</span></span> 
- <span data-ttu-id="4d3ce-2377">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2377">Four digits</span></span> 
- <span data-ttu-id="4d3ce-2378">Um espaço ou um traço opcional </span><span class="sxs-lookup"><span data-stu-id="4d3ce-2378">An optional space or dash</span></span> 
- <span data-ttu-id="4d3ce-2379">O dígito final que é o dígito de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2379">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2380">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2380">Checksum</span></span>

<span data-ttu-id="4d3ce-2381">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2381">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2382">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2382">Definition</span></span>

<span data-ttu-id="4d3ce-2383">Uma política de DLP é de 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres: a função Func_india_aadhaar localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2383">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="4d3ce-2384">Uma palavra-chave de Keyword_india_aadhar for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2384">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="4d3ce-2385">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2385">The checksum passes.</span></span>
<span data-ttu-id="4d3ce-2386">Uma política de DLP é de 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres: a função Func_india_aadhaar localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2386">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="4d3ce-2387">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2387">The checksum passes.</span></span>
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
### <a name="keywords"></a><span data-ttu-id="4d3ce-2388">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2388">Keywords</span></span>
   
#### <a name="keyword_india_aadhar"></a><span data-ttu-id="4d3ce-2389">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2389">Keyword_india_aadhar</span></span>
- <span data-ttu-id="4d3ce-2390">Aadhar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2390">Aadhar</span></span>
- <span data-ttu-id="4d3ce-2391">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2391">Aadhaar</span></span>
- <span data-ttu-id="4d3ce-2392">UID</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2392">UID</span></span>
- <span data-ttu-id="4d3ce-2393">आधार</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2393">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="4d3ce-2394">Número do Cartão de Identidade da Indonésia (KTP)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2394">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2395">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2395">Format</span></span>

<span data-ttu-id="4d3ce-2396">16 dígitos contendo pontos opcionais</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2396">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2397">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2397">Pattern</span></span>

<span data-ttu-id="4d3ce-2398">16 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2398">16 digits:</span></span>
- <span data-ttu-id="4d3ce-2399">Código de província de dois dígitos </span><span class="sxs-lookup"><span data-stu-id="4d3ce-2399">Two-digit province code</span></span> 
- <span data-ttu-id="4d3ce-2400">Um ponto (opcional) </span><span class="sxs-lookup"><span data-stu-id="4d3ce-2400">A period (optional)</span></span> 
- <span data-ttu-id="4d3ce-2401">Código de dois dígitos da regência ou da cidade </span><span class="sxs-lookup"><span data-stu-id="4d3ce-2401">Two-digit regency or city code</span></span> 
- <span data-ttu-id="4d3ce-2402">Código de dois dígitos do subdistrito </span><span class="sxs-lookup"><span data-stu-id="4d3ce-2402">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="4d3ce-2403">Um ponto (opcional) </span><span class="sxs-lookup"><span data-stu-id="4d3ce-2403">A period (optional)</span></span> 
- <span data-ttu-id="4d3ce-2404">Seis dígitos no formato DDMMAA que são a data de nascimento</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2404">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="4d3ce-2405">Um ponto (opcional) </span><span class="sxs-lookup"><span data-stu-id="4d3ce-2405">A period (optional)</span></span> 
- <span data-ttu-id="4d3ce-2406">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2406">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2407">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2407">Checksum</span></span>

<span data-ttu-id="4d3ce-2408">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2408">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2409">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2409">Definition</span></span>

<span data-ttu-id="4d3ce-2410">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2410">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2411">A expressão regular Regex_indonesia_id_card localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2411">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2412">Uma palavra-chave de Keyword_indonesia_id_card for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2412">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="4d3ce-2413">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2413">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2414">A expressão regular Regex_indonesia_id_card localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2414">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-2415">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2415">Keywords</span></span>
   
#### <a name="keyword_indonesia_id_card"></a><span data-ttu-id="4d3ce-2416">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2416">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="4d3ce-2417">KTP</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2417">KTP</span></span>
- <span data-ttu-id="4d3ce-2418">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2418">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="4d3ce-2419">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2419">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="4d3ce-2420">Número da Conta Bancária Internacional (IBAN)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2420">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2421">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2421">Format</span></span>

<span data-ttu-id="4d3ce-2422">Código do país (duas letras) mais dígitos de verificação (dois dígitos) mais Bban número (até 30 caracteres)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2422">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2423">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2423">Pattern</span></span>

<span data-ttu-id="4d3ce-2424">O padrão deve incluir todos os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2424">Pattern must include all of the following:</span></span>

- <span data-ttu-id="4d3ce-2425">Código de país de duas letras</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2425">Two-letter country code</span></span>
- <span data-ttu-id="4d3ce-2426">Dois dígitos de verificação (seguidos por um espaço opcional)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2426">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="4d3ce-2427">1-7 grupos de quatro letras ou dígitos (podem ser separados por espaços)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2427">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="4d3ce-2428">1 a 3 letras ou dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2428">1-3 letters or digits</span></span>

<span data-ttu-id="4d3ce-2429">O formato de cada país é um pouco diferente.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2429">The format for each country is slightly different.</span></span> <span data-ttu-id="4d3ce-2430">O tipo de informação confidencial do IBAN cobre estes 60 países:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2430">The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="4d3ce-2431">AD, AE, Al, at, AZ, BA, be, BG, BH, ch, CR, Cy, cz, de, DK, do, EE, es, Fi, fo, FR, GB, GE, GI, GL, GR, HR, Hu, IE, Il, se,-, KZ, lb, li, o (a) e o (a) , NL, no, pl, pt, Ro, RS, SA, se, si, SK, SM, TN, TR, VG</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2431">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2432">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2432">Checksum</span></span>

<span data-ttu-id="4d3ce-2433">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2433">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2434">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2434">Definition</span></span>

<span data-ttu-id="4d3ce-2435">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2435">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2436">A função Func_iban localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2436">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2437">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2437">The checksum passes.</span></span>

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-2438">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2438">Keywords</span></span>

<span data-ttu-id="4d3ce-2439">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2439">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="4d3ce-2440">Endereço IP</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2440">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2441">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2441">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="4d3ce-2442">IPv4</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2442">IPv4:</span></span>
<span data-ttu-id="4d3ce-2443">Padrão complexo que é responsável por versões formatadas (pontos) e não formatadas (sem pontos) dos endereços IPv4</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2443">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="4d3ce-2444">IPv6</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2444">IPv6:</span></span>
<span data-ttu-id="4d3ce-2445">Padrão complexo que é responsável por números IPv6 formatados (que incluem dois pontos)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2445">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2446">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2446">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2447">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2447">Checksum</span></span>

<span data-ttu-id="4d3ce-2448">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2448">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2449">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2449">Definition</span></span>

<span data-ttu-id="4d3ce-2450">Para IPv6, uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2450">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2451">A expressão regular Regex_ipv6_address localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2451">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2452">Nenhuma palavra-chave de Keyword_ipaddress for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2452">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="4d3ce-2453">Para IPv4, uma política de DLP tem 95% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2453">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2454">A expressão regular Regex_ipv4_address localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2454">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2455">Uma palavra-chave de Keyword_ipaddress for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2455">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="4d3ce-2456">Para IPv6, uma política de DLP tem 95% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2456">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2457">A expressão regular Regex_ipv6_address localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2457">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2458">Nenhuma palavra-chave de Keyword_ipaddress for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2458">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-2459">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2459">Keywords</span></span>

#### <a name="keyword_ipaddress"></a><span data-ttu-id="4d3ce-2460">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2460">Keyword_ipaddress</span></span>

- <span data-ttu-id="4d3ce-2461">IP (esta palavra-chave diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2461">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="4d3ce-2462">ip address</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2462">ip address</span></span> 
- <span data-ttu-id="4d3ce-2463">endereços ip</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2463">ip addresses</span></span>
- <span data-ttu-id="4d3ce-2464">internet protocol</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2464">internet protocol</span></span>
- <span data-ttu-id="4d3ce-2465">IP כתובת ה</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2465">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="4d3ce-2466">Classificação internacional do Diseases (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2466">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2467">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2467">Format</span></span>

<span data-ttu-id="4d3ce-2468">Dictionary</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2468">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2469">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2469">Pattern</span></span>

<span data-ttu-id="4d3ce-2470">Palavra-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2470">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2471">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2471">Checksum</span></span>

<span data-ttu-id="4d3ce-2472">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2472">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2473">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2473">Definition</span></span>

<span data-ttu-id="4d3ce-2474">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2474">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2475">Uma palavra-chave de Dictionary_icd_10_updated for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2475">A keyword from Dictionary_icd_10_updated is found.</span></span>
- <span data-ttu-id="4d3ce-2476">Uma palavra-chave de Dictionary_icd_10_codes for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2476">A keyword from Dictionary_icd_10_codes is found.</span></span>

<span data-ttu-id="4d3ce-2477">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2477">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2478">Uma palavra-chave de Dictionary_icd_10_ atualizada é encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2478">A keyword from Dictionary_icd_10_ updated is found.</span></span>

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

<span data-ttu-id="4d3ce-2479">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2479">Keywords</span></span>

<span data-ttu-id="4d3ce-2480">Qualquer termo do dicionário de palavra-chave Dictionary_icd_10_updated, que se baseia na [classificação internacional do Diseases, décimo revisão, modificação clínica (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604).</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2480">Any term from the Dictionary_icd_10_updated keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="4d3ce-2481">Esse tipo procura apenas o termo, não os códigos de seguro.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2481">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="4d3ce-2482">Qualquer termo do dicionário de palavra-chave Dictionary_icd_10_codes, que se baseia na [classificação internacional do Diseases, décimo revisão, modificação clínica (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604).</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2482">Any term from the Dictionary_icd_10_codes keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="4d3ce-2483">Este tipo procura apenas por códigos de seguro, não a descrição.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2483">This type looks only for insurance codes, not the description.</span></span>

## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="4d3ce-2484">Classificação internacional do Diseases (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2484">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2485">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2485">Format</span></span>

<span data-ttu-id="4d3ce-2486">Dictionary</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2486">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2487">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2487">Pattern</span></span>

<span data-ttu-id="4d3ce-2488">Palavra-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2488">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2489">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2489">Checksum</span></span>

<span data-ttu-id="4d3ce-2490">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2490">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2491">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2491">Definition</span></span>

<span data-ttu-id="4d3ce-2492">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2492">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2493">Uma palavra-chave de Dictionary_icd_9_updated for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2493">A keyword from Dictionary_icd_9_updated is found.</span></span>
- <span data-ttu-id="4d3ce-2494">Uma palavra-chave de Dictionary_icd_9_codes for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2494">A keyword from Dictionary_icd_9_codes is found.</span></span>

<span data-ttu-id="4d3ce-2495">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2495">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2496">Uma palavra-chave de Dictionary_icd_9_updated for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2496">A keyword from Dictionary_icd_9_updated is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-2497">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2497">Keywords</span></span>

<span data-ttu-id="4d3ce-2498">Qualquer termo do dicionário de palavra-chave Dictionary_icd_9_updated, que se baseia na [classificação internacional do Diseases, Nona revisão, modificação clínica (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605).</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2498">Any term from the Dictionary_icd_9_updated keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="4d3ce-2499">Esse tipo procura apenas o termo, não os códigos de seguro.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2499">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="4d3ce-2500">Qualquer termo do dicionário de palavra-chave Dictionary_icd_9_codes, que se baseia na [classificação internacional do Diseases, Nona revisão, modificação clínica (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605).</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2500">Any term from the Dictionary_icd_9_codes keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="4d3ce-2501">Este tipo procura apenas por códigos de seguro, não a descrição.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2501">This type looks only for insurance codes, not the description.</span></span>

## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="4d3ce-2502">Número de Serviço Público Pessoal (PPS) da Irlanda</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2502">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2503">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2503">Format</span></span>

<span data-ttu-id="4d3ce-2504">Formato antigo (até 31 de dezembro de 2012):</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2504">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="4d3ce-2505">Sete dígitos seguidos de 1 a 2 letras </span><span class="sxs-lookup"><span data-stu-id="4d3ce-2505">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="4d3ce-2506">Novo formato (1 Jan 2013 e posterior):</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2506">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="4d3ce-2507">Sete dígitos seguidos de duas letras</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2507">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2508">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2508">Pattern</span></span>

<span data-ttu-id="4d3ce-2509">Formato antigo (até 31 de dezembro de 2012):</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2509">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="4d3ce-2510">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="4d3ce-2510">Seven digits</span></span> 
- <span data-ttu-id="4d3ce-2511">1 a 2 letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2511">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="4d3ce-2512">Novo formato (1 Jan 2013 e posterior):</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2512">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="4d3ce-2513">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="4d3ce-2513">Seven digits</span></span> 
- <span data-ttu-id="4d3ce-2514">Uma letra (não diferencia maiúsculas de minúsculas) que é um dígito de verificação alfabético </span><span class="sxs-lookup"><span data-stu-id="4d3ce-2514">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="4d3ce-2515">A letra "A" ou "H" (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2515">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2516">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2516">Checksum</span></span>

<span data-ttu-id="4d3ce-2517">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2517">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2518">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2518">Definition</span></span>

<span data-ttu-id="4d3ce-2519">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2520">A função Func_ireland_pps localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2520">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2521">Uma das seguintes opções for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2521">One of the following is true:</span></span>
    - <span data-ttu-id="4d3ce-2522">Uma palavra-chave de Keyword_ireland_pps for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2522">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="4d3ce-2523">A função Func_eu_date encontra uma data no formato de data à direita.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2523">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="4d3ce-2524">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2524">The checksum passes.</span></span>

<span data-ttu-id="4d3ce-2525">Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2525">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2526">A função Func_ireland_pps localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2526">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2527">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2527">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-2528">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2528">Keywords</span></span>

#### <a name="keyword_ireland_pps"></a><span data-ttu-id="4d3ce-2529">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2529">Keyword_ireland_pps</span></span>

- <span data-ttu-id="4d3ce-2530">Número do Serviço Público Pessoal</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2530">Personal Public Service Number</span></span> 
- <span data-ttu-id="4d3ce-2531">Número PPS</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2531">PPS Number</span></span> 
- <span data-ttu-id="4d3ce-2532">Núm PPS</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2532">PPS Num</span></span> 
- <span data-ttu-id="4d3ce-2533">Nº PPS</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2533">PPS No.</span></span> 
- <span data-ttu-id="4d3ce-2534"># PPS</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2534">PPS #</span></span> 
- <span data-ttu-id="4d3ce-2535">PPS #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2535">PPS#</span></span> 
- <span data-ttu-id="4d3ce-2536">PPSN</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2536">PPSN</span></span> 
- <span data-ttu-id="4d3ce-2537">Cartão dos Serviços Públicos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2537">Public Services Card</span></span> 
- <span data-ttu-id="4d3ce-2538">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2538">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="4d3ce-2539">Uimh.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2539">Uimh.</span></span> <span data-ttu-id="4d3ce-2540">PSP</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2540">PSP</span></span> 
- <span data-ttu-id="4d3ce-2541">PSP</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2541">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="4d3ce-2542">Número de conta bancária de Israel</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2542">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2543">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2543">Format</span></span>

<span data-ttu-id="4d3ce-2544">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2544">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2545">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2545">Pattern</span></span>

<span data-ttu-id="4d3ce-2546">Binário</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2546">Formatted:</span></span>
- <span data-ttu-id="4d3ce-2547">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2547">Two digits</span></span> 
- <span data-ttu-id="4d3ce-2548">Um traço</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2548">A dash</span></span> 
- <span data-ttu-id="4d3ce-2549">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2549">Three digits</span></span> 
- <span data-ttu-id="4d3ce-2550">Um traço</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2550">A dash</span></span> 
- <span data-ttu-id="4d3ce-2551">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2551">Eight digits</span></span>

<span data-ttu-id="4d3ce-2552">Não formatado</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2552">Unformatted:</span></span>
- <span data-ttu-id="4d3ce-2553">13 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2553">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2554">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2554">Checksum</span></span>

<span data-ttu-id="4d3ce-2555">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2555">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2556">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2556">Definition</span></span>

<span data-ttu-id="4d3ce-2557">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2558">A expressão regular Regex_israel_bank_account_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2558">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2559">Uma palavra-chave de Keyword_israel_bank_account_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2559">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-2560">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2560">Keywords</span></span>

#### <a name="keyword_israel_bank_account_number"></a><span data-ttu-id="4d3ce-2561">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2561">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="4d3ce-2562">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2562">Bank Account Number</span></span> 
- <span data-ttu-id="4d3ce-2563">Bank Account</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2563">Bank Account</span></span> 
- <span data-ttu-id="4d3ce-2564">Account Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2564">Account Number</span></span> 
- <span data-ttu-id="4d3ce-2565">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2565">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="4d3ce-2566">ID nacional de Israel</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2566">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2567">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2567">Format</span></span>

<span data-ttu-id="4d3ce-2568">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2568">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2569">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2569">Pattern</span></span>

<span data-ttu-id="4d3ce-2570">Nove dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2570">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2571">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2571">Checksum</span></span>

<span data-ttu-id="4d3ce-2572">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2572">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2573">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2573">Definition</span></span>

<span data-ttu-id="4d3ce-2574">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2574">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2575">A função Func_israeli_national_id_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2575">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2576">Uma palavra-chave de Keyword_Israel_National_ID for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2576">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="4d3ce-2577">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2577">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-2578">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2578">Keywords</span></span>

#### <a name="keyword_israel_national_id"></a><span data-ttu-id="4d3ce-2579">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2579">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="4d3ce-2580">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2580">מספר זהות</span></span> 
- <span data-ttu-id="4d3ce-2581">Número de identificação nacional</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2581">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="4d3ce-2582">Número de carteira de motorista da Itália</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2582">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2583">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2583">Format</span></span>

<span data-ttu-id="4d3ce-2584">Uma combinação de 10 letras e dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2584">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2585">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2585">Pattern</span></span>

- <span data-ttu-id="4d3ce-2586">Uma combinação de 10 letras e dígitos:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2586">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="4d3ce-2587">Uma letra (não diferencia maiúscula de minúscula)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2587">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="4d3ce-2588">A letra "A" ou "V" (não diferencia maiúscula de minúscula)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2588">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="4d3ce-2589">Sete letras (não diferenciam maiúsculas de minúsculas), dígitos ou o caractere de sublinhado</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2589">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="4d3ce-2590">Uma letra (não diferencia maiúscula de minúscula)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2590">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2591">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2591">Checksum</span></span>

<span data-ttu-id="4d3ce-2592">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2592">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2593">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2593">Definition</span></span>

<span data-ttu-id="4d3ce-2594">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2594">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2595">A expressão regular Regex_italy_drivers_license_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2595">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2596">Uma palavra-chave de Keyword_italy_drivers_license_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2596">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-2597">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2597">Keywords</span></span>

#### <a name="keyword_italy_drivers_license_number"></a><span data-ttu-id="4d3ce-2598">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2598">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="4d3ce-2599">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2599">numero di patente di guida</span></span> 
- <span data-ttu-id="4d3ce-2600">patente di guida</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2600">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="4d3ce-2601">Número de conta bancária do Japão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2601">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2602">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2602">Format</span></span>

<span data-ttu-id="4d3ce-2603">Sete ou oito dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2603">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2604">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2604">Pattern</span></span>

<span data-ttu-id="4d3ce-2605">Número da Conta Bancária:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2605">Bank account number:</span></span>
- <span data-ttu-id="4d3ce-2606">Sete ou oito dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2606">Seven or eight digits</span></span>
- <span data-ttu-id="4d3ce-2607">Código da agência de conta bancária:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2607">Bank account branch code:</span></span>
- <span data-ttu-id="4d3ce-2608">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2608">Four digits</span></span> 
- <span data-ttu-id="4d3ce-2609">Um espaço ou um traço (opcional)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2609">A space or dash (optional)</span></span> 
- <span data-ttu-id="4d3ce-2610">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2610">Three digits</span></span>

<span data-ttu-id="4d3ce-2611">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2611">Checksum</span></span>

<span data-ttu-id="4d3ce-2612">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2612">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2613">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2613">Definition</span></span>

<span data-ttu-id="4d3ce-2614">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2614">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2615">A função Func_jp_bank_account localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2615">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2616">Uma palavra-chave de Keyword_jp_bank_account for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2616">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="4d3ce-2617">Uma das seguintes opções for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2617">One of the following is true:</span></span>
- <span data-ttu-id="4d3ce-2618">A função Func_jp_bank_account_branch_code localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2618">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2619">Uma palavra-chave de Keyword_jp_bank_branch_code for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2619">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="4d3ce-2620">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2620">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2621">A função Func_jp_bank_account localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2621">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2622">Uma palavra-chave de Keyword_jp_bank_account for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2622">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-2623">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2623">Keywords</span></span>

#### <a name="keyword_jp_bank_account"></a><span data-ttu-id="4d3ce-2624">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2624">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="4d3ce-2625">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2625">Checking Account Number</span></span> 
- <span data-ttu-id="4d3ce-2626">Checking Account</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2626">Checking Account</span></span> 
- <span data-ttu-id="4d3ce-2627">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2627">Checking Account #</span></span> 
- <span data-ttu-id="4d3ce-2628">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2628">Checking Acct Number</span></span> 
- <span data-ttu-id="4d3ce-2629">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2629">Checking Acct #</span></span> 
- <span data-ttu-id="4d3ce-2630">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2630">Checking Acct No.</span></span> 
- <span data-ttu-id="4d3ce-2631">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2631">Checking Account No.</span></span> 
- <span data-ttu-id="4d3ce-2632">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2632">Bank Account Number</span></span> 
- <span data-ttu-id="4d3ce-2633">Bank Account</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2633">Bank Account</span></span> 
- <span data-ttu-id="4d3ce-2634">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2634">Bank Account #</span></span> 
- <span data-ttu-id="4d3ce-2635">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2635">Bank Acct Number</span></span> 
- <span data-ttu-id="4d3ce-2636">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2636">Bank Acct #</span></span> 
- <span data-ttu-id="4d3ce-2637">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2637">Bank Acct No.</span></span> 
- <span data-ttu-id="4d3ce-2638">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2638">Bank Account No.</span></span> 
- <span data-ttu-id="4d3ce-2639">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2639">Savings Account Number</span></span> 
- <span data-ttu-id="4d3ce-2640">Savings Account</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2640">Savings Account</span></span> 
- <span data-ttu-id="4d3ce-2641">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2641">Savings Account #</span></span> 
- <span data-ttu-id="4d3ce-2642">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2642">Savings Acct Number</span></span> 
- <span data-ttu-id="4d3ce-2643">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2643">Savings Acct #</span></span> 
- <span data-ttu-id="4d3ce-2644">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2644">Savings Acct No.</span></span> 
- <span data-ttu-id="4d3ce-2645">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2645">Savings Account No.</span></span> 
- <span data-ttu-id="4d3ce-2646">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2646">Debit Account Number</span></span> 
- <span data-ttu-id="4d3ce-2647">Debit Account</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2647">Debit Account</span></span> 
- <span data-ttu-id="4d3ce-2648">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2648">Debit Account #</span></span> 
- <span data-ttu-id="4d3ce-2649">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2649">Debit Acct Number</span></span> 
- <span data-ttu-id="4d3ce-2650">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2650">Debit Acct #</span></span> 
- <span data-ttu-id="4d3ce-2651">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2651">Debit Acct No.</span></span> 
- <span data-ttu-id="4d3ce-2652">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2652">Debit Account No.</span></span> 
- <span data-ttu-id="4d3ce-2653">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2653">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="4d3ce-2654">#アカウントの確認 、 勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2654">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="4d3ce-2655">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2655">＃勘定の確認</span></span> 
- <span data-ttu-id="4d3ce-2656">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2656">勘定番号の確認</span></span> 
- <span data-ttu-id="4d3ce-2657">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2657">口座番号の確認</span></span> 
- <span data-ttu-id="4d3ce-2658">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2658">銀行口座番号</span></span> 
- <span data-ttu-id="4d3ce-2659">銀行口座</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2659">銀行口座</span></span> 
- <span data-ttu-id="4d3ce-2660">銀行口座＃</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2660">銀行口座＃</span></span> 
- <span data-ttu-id="4d3ce-2661">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2661">銀行の勘定番号</span></span> 
- <span data-ttu-id="4d3ce-2662">銀行のacct＃</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2662">銀行のacct＃</span></span> 
- <span data-ttu-id="4d3ce-2663">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2663">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="4d3ce-2664">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2664">銀行口座番号</span></span>
- <span data-ttu-id="4d3ce-2665">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2665">普通預金口座番号</span></span> 
- <span data-ttu-id="4d3ce-2666">預金口座</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2666">預金口座</span></span> 
- <span data-ttu-id="4d3ce-2667">貯蓄口座＃</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2667">貯蓄口座＃</span></span> 
- <span data-ttu-id="4d3ce-2668">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2668">貯蓄勘定の数</span></span> 
- <span data-ttu-id="4d3ce-2669">貯蓄勘定＃</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2669">貯蓄勘定＃</span></span> 
- <span data-ttu-id="4d3ce-2670">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2670">貯蓄勘定番号</span></span> 
- <span data-ttu-id="4d3ce-2671">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2671">普通預金口座番号</span></span> 
- <span data-ttu-id="4d3ce-2672">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2672">引き落とし口座番号</span></span> 
- <span data-ttu-id="4d3ce-2673">口座番号</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2673">口座番号</span></span> 
- <span data-ttu-id="4d3ce-2674">口座番号＃</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2674">口座番号＃</span></span> 
- <span data-ttu-id="4d3ce-2675">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2675">デビットのacct番号</span></span> 
- <span data-ttu-id="4d3ce-2676">デビット勘定＃</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2676">デビット勘定＃</span></span> 
- <span data-ttu-id="4d3ce-2677">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2677">デビットACCTの番号</span></span> 
- <span data-ttu-id="4d3ce-2678">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2678">デビット口座番号</span></span> 

#### <a name="keyword_jp_bank_branch_code"></a><span data-ttu-id="4d3ce-2679">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2679">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="4d3ce-2680">Otemachi</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2680">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="4d3ce-2681">Número de carteira de motorista do Japão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2681">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2682">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2682">Format</span></span>

<span data-ttu-id="4d3ce-2683">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2683">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2684">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2684">Pattern</span></span>

<span data-ttu-id="4d3ce-2685">12 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2685">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2686">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2686">Checksum</span></span>

<span data-ttu-id="4d3ce-2687">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2687">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2688">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2688">Definition</span></span>

<span data-ttu-id="4d3ce-2689">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2689">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2690">A função Func_jp_drivers_license_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2690">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2691">Uma palavra-chave de Keyword_jp_drivers_license_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2691">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-2692">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2692">Keywords</span></span>

#### <a name="keyword_jp_drivers_license_number"></a><span data-ttu-id="4d3ce-2693">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2693">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="4d3ce-2694">distribuição #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2694">dl#</span></span> 
- <span data-ttu-id="4d3ce-2695">DISTRIBUIÇÃO</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2695">DL＃</span></span> 
- <span data-ttu-id="4d3ce-2696">DL #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2696">dls#</span></span> 
- <span data-ttu-id="4d3ce-2697">DL</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2697">DLS＃</span></span> 
- <span data-ttu-id="4d3ce-2698">driver license</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2698">driver license</span></span> 
- <span data-ttu-id="4d3ce-2699">driver licenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2699">driver licenses</span></span> 
- <span data-ttu-id="4d3ce-2700">drivers license</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2700">drivers license</span></span> 
- <span data-ttu-id="4d3ce-2701">driver's license</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2701">driver's license</span></span> 
- <span data-ttu-id="4d3ce-2702">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2702">drivers licenses</span></span> 
- <span data-ttu-id="4d3ce-2703">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2703">driver's licenses</span></span> 
- <span data-ttu-id="4d3ce-2704">driving licence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2704">driving licence</span></span> 
- <span data-ttu-id="4d3ce-2705">driver'lic #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2705">lic#</span></span> 
- <span data-ttu-id="4d3ce-2706">DRIVER'LIC</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2706">LIC＃</span></span> 
- <span data-ttu-id="4d3ce-2707">driver'lics #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2707">lics#</span></span> 
- <span data-ttu-id="4d3ce-2708">state id</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2708">state id</span></span> 
- <span data-ttu-id="4d3ce-2709">state identification</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2709">state identification</span></span> 
- <span data-ttu-id="4d3ce-2710">state identification number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2710">state identification number</span></span> 
- <span data-ttu-id="4d3ce-2711">低所得国＃</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2711">低所得国＃</span></span> 
- <span data-ttu-id="4d3ce-2712">免許証</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2712">免許証</span></span> 
- <span data-ttu-id="4d3ce-2713">状態ID</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2713">状態ID</span></span>
- <span data-ttu-id="4d3ce-2714">状態の識別</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2714">状態の識別</span></span> 
- <span data-ttu-id="4d3ce-2715">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2715">状態の識別番号</span></span> 
- <span data-ttu-id="4d3ce-2716">運転免許</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2716">運転免許</span></span> 
- <span data-ttu-id="4d3ce-2717">運転免許証</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2717">運転免許証</span></span> 
- <span data-ttu-id="4d3ce-2718">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2718">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="4d3ce-2719">Número de passaporte do Japão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2719">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2720">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2720">Format</span></span>

<span data-ttu-id="4d3ce-2721">Duas letras seguidas por sete dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2721">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2722">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2722">Pattern</span></span>

<span data-ttu-id="4d3ce-2723">Duas letras (não diferencia maiúsculas de minúsculas) seguidas de sete dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2723">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2724">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2724">Checksum</span></span>

<span data-ttu-id="4d3ce-2725">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2725">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2726">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2726">Definition</span></span>

<span data-ttu-id="4d3ce-2727">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2728">A função Func_jp_passport localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2728">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2729">Uma palavra-chave de Keyword_jp_passport for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2729">A keyword from Keyword_jp_passport is found.</span></span>

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-2730">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2730">Keywords</span></span>

#### <a name="keyword_jp_passport"></a><span data-ttu-id="4d3ce-2731">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2731">Keyword_jp_passport</span></span>

- <span data-ttu-id="4d3ce-2732">パスポート</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2732">パスポート</span></span> 
- <span data-ttu-id="4d3ce-2733">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2733">パスポート番号</span></span> 
- <span data-ttu-id="4d3ce-2734">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2734">パスポートのNum</span></span> 
- <span data-ttu-id="4d3ce-2735">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2735">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="4d3ce-2736">Número de registro de residente do Japão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2736">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2737">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2737">Format</span></span>

<span data-ttu-id="4d3ce-2738">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2738">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2739">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2739">Pattern</span></span>

<span data-ttu-id="4d3ce-2740">11 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2740">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2741">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2741">Checksum</span></span>

<span data-ttu-id="4d3ce-2742">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2742">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2743">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2743">Definition</span></span>

<span data-ttu-id="4d3ce-2744">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2744">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2745">A função Func_jp_resident_registration_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2745">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2746">Uma palavra-chave de Keyword_jp_resident_registration_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2746">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-2747">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2747">Keywords</span></span>

#### <a name="keyword_jp_resident_registration_number"></a><span data-ttu-id="4d3ce-2748">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2748">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="4d3ce-2749">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2749">Resident Registration Number</span></span>
- <span data-ttu-id="4d3ce-2750">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2750">Resident Register Number</span></span> 
- <span data-ttu-id="4d3ce-2751">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2751">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="4d3ce-2752">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2752">Resident Registration No.</span></span> 
- <span data-ttu-id="4d3ce-2753">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2753">Resident Register No.</span></span> 
- <span data-ttu-id="4d3ce-2754">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2754">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="4d3ce-2755">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2755">Basic Resident Register No.</span></span> 
- <span data-ttu-id="4d3ce-2756">住民登録番号、登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2756">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="4d3ce-2757">住民基本登録番号、登録番号</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2757">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="4d3ce-2758">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2758">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="4d3ce-2759">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2759">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="4d3ce-2760">Número de seguro social do Japão (SIN)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2760">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2761">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2761">Format</span></span>

<span data-ttu-id="4d3ce-2762">7 a 12 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2762">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2763">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2763">Pattern</span></span>

<span data-ttu-id="4d3ce-2764">7 a 12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2764">7-12 digits:</span></span>
- <span data-ttu-id="4d3ce-2765">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2765">Four digits</span></span> 
- <span data-ttu-id="4d3ce-2766">Um hífen (opcional)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2766">A hyphen (optional)</span></span> 
- <span data-ttu-id="4d3ce-2767">Seis dígitos ou</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2767">Six digits OR</span></span>
- <span data-ttu-id="4d3ce-2768">7 a 12 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2768">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2769">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2769">Checksum</span></span>

<span data-ttu-id="4d3ce-2770">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2770">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2771">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2771">Definition</span></span>

<span data-ttu-id="4d3ce-2772">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2772">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2773">A função Func_jp_sin localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2773">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2774">Uma palavra-chave de Keyword_jp_sin for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2774">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="4d3ce-2775">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2775">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2776">A função Func_jp_sin_pre_1997 localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2776">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2777">Uma palavra-chave de Keyword_jp_sin for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2777">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-2778">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2778">Keywords</span></span>

#### <a name="keyword_jp_sin"></a><span data-ttu-id="4d3ce-2779">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2779">Keyword_jp_sin</span></span>

- <span data-ttu-id="4d3ce-2780">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2780">Social Insurance No.</span></span> 
- <span data-ttu-id="4d3ce-2781">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2781">Social Insurance Num</span></span> 
- <span data-ttu-id="4d3ce-2782">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2782">Social Insurance Number</span></span> 
- <span data-ttu-id="4d3ce-2783">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2783">社会保険のテンキー</span></span> 
- <span data-ttu-id="4d3ce-2784">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2784">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="4d3ce-2785">Número do cartão de residência japonês</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2785">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2786">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2786">Format</span></span>

<span data-ttu-id="4d3ce-2787">12 letras e dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2787">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2788">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2788">Pattern</span></span>

<span data-ttu-id="4d3ce-2789">12 letras e dígitos:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2789">12 letters and digits:</span></span>
- <span data-ttu-id="4d3ce-2790">Duas letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2790">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="4d3ce-2791">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2791">Eight digits</span></span> 
- <span data-ttu-id="4d3ce-2792">Duas letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2792">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2793">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2793">Checksum</span></span>

<span data-ttu-id="4d3ce-2794">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2794">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2795">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2795">Definition</span></span>

<span data-ttu-id="4d3ce-2796">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2796">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2797">A expressão regular Regex_jp_residence_card_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2797">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2798">Uma palavra-chave de Keyword_jp_residence_card_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2798">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-2799">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2799">Keywords</span></span>

#### <a name="keyword_jp_residence_card_number"></a><span data-ttu-id="4d3ce-2800">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2800">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="4d3ce-2801">Número do cartão de residência</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2801">Residence card number</span></span>
- <span data-ttu-id="4d3ce-2802">Número do cartão de residência</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2802">Residence card no</span></span>
- <span data-ttu-id="4d3ce-2803">Cartão de residência #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2803">Residence card #</span></span>
- <span data-ttu-id="4d3ce-2804">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2804">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="4d3ce-2805">Número do Cartão de Identificação da Malásia</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2805">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2806">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2806">Format</span></span>

<span data-ttu-id="4d3ce-2807">12 dígitos contendo hifens opcionais</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2807">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2808">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2808">Pattern</span></span>

<span data-ttu-id="4d3ce-2809">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2809">12 digits:</span></span>
- <span data-ttu-id="4d3ce-2810">Seis dígitos no formato AAMMDD que são a data de nascimento</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2810">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="4d3ce-2811">Um traço (opcional)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2811">A dash (optional)</span></span> 
- <span data-ttu-id="4d3ce-2812">Código do local de nascimento de duas letras </span><span class="sxs-lookup"><span data-stu-id="4d3ce-2812">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="4d3ce-2813">Um traço (opcional)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2813">A dash (optional)</span></span> 
- <span data-ttu-id="4d3ce-2814">Três dígitos aleatórios </span><span class="sxs-lookup"><span data-stu-id="4d3ce-2814">Three random digits</span></span> 
- <span data-ttu-id="4d3ce-2815">Código de sexo de um dígito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2815">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2816">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2816">Checksum</span></span>

<span data-ttu-id="4d3ce-2817">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2817">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2818">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2818">Definition</span></span>

<span data-ttu-id="4d3ce-2819">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2819">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2820">A expressão regular Regex_malaysia_id_card_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2820">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2821">Uma palavra-chave de Keyword_malaysia_id_card_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2821">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-2822">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2822">Keywords</span></span>
   
#### <a name="keyword_malaysia_id_card_number"></a><span data-ttu-id="4d3ce-2823">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2823">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="4d3ce-2824">cartão de aplicativo digital</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2824">digital application card</span></span>
- <span data-ttu-id="4d3ce-2825">e/c</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2825">i/c</span></span>
- <span data-ttu-id="4d3ce-2826">e/c não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2826">i/c no</span></span>
- <span data-ttu-id="4d3ce-2827">Liga</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2827">ic</span></span>
- <span data-ttu-id="4d3ce-2828">IC não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2828">ic no</span></span>
- <span data-ttu-id="4d3ce-2829">id card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2829">id card</span></span>
- <span data-ttu-id="4d3ce-2830">Cartão de identificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2830">identification Card</span></span>
- <span data-ttu-id="4d3ce-2831">cartão de identidade</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2831">identity card</span></span>
- <span data-ttu-id="4d3ce-2832">k/p</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2832">k/p</span></span>
- <span data-ttu-id="4d3ce-2833">n/p não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2833">k/p no</span></span>
- <span data-ttu-id="4d3ce-2834">kad akuan diri</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2834">kad akuan diri</span></span>
- <span data-ttu-id="4d3ce-2835">kad aplikasi digital</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2835">kad aplikasi digital</span></span>
- <span data-ttu-id="4d3ce-2836">kad pengenalan Malásia</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2836">kad pengenalan malaysia</span></span>
- <span data-ttu-id="4d3ce-2837">KP</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2837">kp</span></span>
- <span data-ttu-id="4d3ce-2838">KP não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2838">kp no</span></span>
- <span data-ttu-id="4d3ce-2839">mykad</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2839">mykad</span></span>
- <span data-ttu-id="4d3ce-2840">mykas</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2840">mykas</span></span>
- <span data-ttu-id="4d3ce-2841">mykid</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2841">mykid</span></span>
- <span data-ttu-id="4d3ce-2842">mypr</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2842">mypr</span></span>
- <span data-ttu-id="4d3ce-2843">mytentera</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2843">mytentera</span></span>
- <span data-ttu-id="4d3ce-2844">cartão de identidade da Malásia</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2844">malaysia identity card</span></span>
- <span data-ttu-id="4d3ce-2845">cartão de identidade do Malasiano</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2845">malaysian identity card</span></span>
- <span data-ttu-id="4d3ce-2846">nric</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2846">nric</span></span>
- <span data-ttu-id="4d3ce-2847">cartão de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2847">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="4d3ce-2848">Número do Serviço do Cidadão (BSN) da Holland</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2848">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2849">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2849">Format</span></span>

<span data-ttu-id="4d3ce-2850">8 a 9 dígitos contendo espaços opcionais</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2850">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2851">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2851">Pattern</span></span>

<span data-ttu-id="4d3ce-2852">8 a 9 dígitos.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2852">8-9 digits:</span></span>
- <span data-ttu-id="4d3ce-2853">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2853">Three digits</span></span> 
- <span data-ttu-id="4d3ce-2854">Um espaço (opcional)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2854">A space (optional)</span></span> 
- <span data-ttu-id="4d3ce-2855">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2855">Three digits</span></span> 
- <span data-ttu-id="4d3ce-2856">Um espaço (opcional)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2856">A space (optional)</span></span> 
- <span data-ttu-id="4d3ce-2857">2 a 3 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2857">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2858">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2858">Checksum</span></span>

<span data-ttu-id="4d3ce-2859">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2859">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2860">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2860">Definition</span></span>

<span data-ttu-id="4d3ce-2861">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2861">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2862">A função Func_netherlands_bsn localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2862">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2863">Uma palavra-chave de Keyword_netherlands_bsn for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2863">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="4d3ce-2864">A função Func_eu_date2 localiza uma data no formato de data à direita.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2864">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="4d3ce-2865">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2865">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-2866">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2866">Keywords</span></span>

#### <a name="keyword_netherlands_bsn"></a><span data-ttu-id="4d3ce-2867">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2867">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="4d3ce-2868">Número do serviço do cidadão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2868">Citizen service number</span></span> 
- <span data-ttu-id="4d3ce-2869">BSN</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2869">BSN</span></span> 
- <span data-ttu-id="4d3ce-2870">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2870">Burgerservicenummer</span></span> 
- <span data-ttu-id="4d3ce-2871">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2871">Sofinummer</span></span> 
- <span data-ttu-id="4d3ce-2872">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2872">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="4d3ce-2873">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2873">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="4d3ce-2874">Número do Ministério da Saúde da Nova Zelândia</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2874">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2875">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2875">Format</span></span>

<span data-ttu-id="4d3ce-2876">Três letras, um espaço (opcional) e quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2876">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2877">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2877">Pattern</span></span>

<span data-ttu-id="4d3ce-2878">Três letras (não diferencia maiúsculas de minúsculas) um espaço (opcional) quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2878">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2879">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2879">Checksum</span></span>

<span data-ttu-id="4d3ce-2880">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2880">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2881">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2881">Definition</span></span>

<span data-ttu-id="4d3ce-2882">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2882">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2883">A função Func_new_zealand_ministry_of_health_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2883">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2884">Uma palavra-chave de Keyword_nz_terms for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2884">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="4d3ce-2885">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2885">The checksum passes.</span></span>

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

<span data-ttu-id="4d3ce-2886">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2886">Keywords</span></span>

<span data-ttu-id="4d3ce-2887">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2887">Keyword_nz_terms</span></span>

- <span data-ttu-id="4d3ce-2888">NHI</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2888">NHI</span></span> 
- <span data-ttu-id="4d3ce-2889">Nova Zelândia</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2889">New Zealand</span></span> 
- <span data-ttu-id="4d3ce-2890">Integridade</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2890">Health</span></span> 
- <span data-ttu-id="4d3ce-2891">tratamento</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2891">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="4d3ce-2892">Número de Identificação da Noruega</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2892">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2893">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2893">Format</span></span>

<span data-ttu-id="4d3ce-2894">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2894">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2895">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2895">Pattern</span></span>

<span data-ttu-id="4d3ce-2896">11 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2896">11 digits:</span></span>
- <span data-ttu-id="4d3ce-2897">Seis dígitos no formato DDMMAA que são a data de nascimento</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2897">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="4d3ce-2898">Número individual de três dígitos </span><span class="sxs-lookup"><span data-stu-id="4d3ce-2898">Three-digit individual number</span></span> 
- <span data-ttu-id="4d3ce-2899">Dois dígitos de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2899">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2900">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2900">Checksum</span></span>

<span data-ttu-id="4d3ce-2901">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2901">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2902">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2902">Definition</span></span>

<span data-ttu-id="4d3ce-2903">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2903">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2904">A função Func_norway_id_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2904">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2905">Uma palavra-chave de Keyword_norway_id_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2905">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="4d3ce-2906">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2906">The checksum passes.</span></span>
- <span data-ttu-id="4d3ce-2907">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2907">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2908">A função Func_norway_id_numbe localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2908">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2909">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2909">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-2910">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2910">Keywords</span></span>

#### <a name="keyword_norway_id_number"></a><span data-ttu-id="4d3ce-2911">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2911">Keyword_norway_id_number</span></span>

- <span data-ttu-id="4d3ce-2912">Número de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2912">Personal identification number</span></span>
- <span data-ttu-id="4d3ce-2913">Número de Identificação Norueguês</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2913">Norwegian ID Number</span></span>
- <span data-ttu-id="4d3ce-2914">Número de Identificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2914">ID Number</span></span>
- <span data-ttu-id="4d3ce-2915">Identificador</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2915">Identification</span></span>
- <span data-ttu-id="4d3ce-2916">Personnummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2916">Personnummer</span></span>
- <span data-ttu-id="4d3ce-2917">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2917">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="4d3ce-2918">Número de Identificação Multiuso Unificada das Filipinas</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2918">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2919">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2919">Format</span></span>

<span data-ttu-id="4d3ce-2920">12 dígitos separados por hifens</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2920">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2921">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2921">Pattern</span></span>

<span data-ttu-id="4d3ce-2922">12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2922">12 digits:</span></span>
- <span data-ttu-id="4d3ce-2923">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2923">Four digits</span></span> 
- <span data-ttu-id="4d3ce-2924">Um hífen</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2924">A hyphen</span></span> 
- <span data-ttu-id="4d3ce-2925">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="4d3ce-2925">Seven digits</span></span> 
- <span data-ttu-id="4d3ce-2926">Um hífen</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2926">A hyphen</span></span> 
- <span data-ttu-id="4d3ce-2927">Um dígito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2927">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2928">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2928">Checksum</span></span>

<span data-ttu-id="4d3ce-2929">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2929">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2930">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2930">Definition</span></span>

<span data-ttu-id="4d3ce-2931">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2931">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2932">A expressão regular Regex_philippines_unified_id localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2932">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2933">Uma palavra-chave de Keyword_philippines_id for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2933">A keyword from Keyword_philippines_id is found.</span></span>

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-2934">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2934">Keywords</span></span>
   
#### <a name="keyword_philippines_id"></a><span data-ttu-id="4d3ce-2935">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2935">Keyword_philippines_id</span></span>

- <span data-ttu-id="4d3ce-2936">Identificação Multiuso Unificada</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2936">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="4d3ce-2937">UMID</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2937">UMID</span></span> 
- <span data-ttu-id="4d3ce-2938">Cartão de Identidade</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2938">Identity Card</span></span> 
- <span data-ttu-id="4d3ce-2939">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2939">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="4d3ce-2940">Cartão de Identificação da Polônia</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2940">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2941">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2941">Format</span></span>

<span data-ttu-id="4d3ce-2942">Três letras e seis dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2942">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2943">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2943">Pattern</span></span>

<span data-ttu-id="4d3ce-2944">Três letras (não diferenciam maiúsculas de minúsculas) seguidas de seis dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2944">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2945">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2945">Checksum</span></span>

<span data-ttu-id="4d3ce-2946">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2946">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2947">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2947">Definition</span></span>

<span data-ttu-id="4d3ce-2948">Uma política de DLP é de 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres: a função Func_polish_national_id localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2948">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="4d3ce-2949">Uma palavra-chave de Keyword_polish_national_id_passport_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2949">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="4d3ce-2950">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2950">The checksum passes.</span></span>

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-2951">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2951">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="4d3ce-2952">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2952">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="4d3ce-2953">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2953">Dowód osobisty</span></span>
- <span data-ttu-id="4d3ce-2954">Numer dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2954">Numer dowodu osobistego</span></span>
- <span data-ttu-id="4d3ce-2955">Nazwa i numer dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2955">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="4d3ce-2956">Nazwa i NR dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2956">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="4d3ce-2957">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2957">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="4d3ce-2958">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2958">Dowód Tożsamości</span></span>
- <span data-ttu-id="4d3ce-2959">Dow.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2959">dow.</span></span> <span data-ttu-id="4d3ce-2960">Opera.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2960">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="4d3ce-2961">ID nacional da Polônia (PESEL)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2961">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2962">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2962">Format</span></span>

<span data-ttu-id="4d3ce-2963">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2963">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2964">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2964">Pattern</span></span>

<span data-ttu-id="4d3ce-2965">11 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2965">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2966">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2966">Checksum</span></span>

<span data-ttu-id="4d3ce-2967">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2967">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2968">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2968">Definition</span></span>

<span data-ttu-id="4d3ce-2969">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2969">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2970">A função Func_pesel_identification_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2970">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2971">Uma palavra-chave de Keyword_pesel_identification_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2971">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="4d3ce-2972">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2972">The checksum passes.</span></span>

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-2973">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2973">Keywords</span></span>

#### <a name="keyword_pesel_identification_number"></a><span data-ttu-id="4d3ce-2974">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2974">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="4d3ce-2975">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2975">Nr PESEL</span></span>
- <span data-ttu-id="4d3ce-2976">PESEL</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2976">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="4d3ce-2977">Passaporte da Polônia</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2977">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2978">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2978">Format</span></span>

<span data-ttu-id="4d3ce-2979">Duas letras e sete dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2979">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2980">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2980">Pattern</span></span>

<span data-ttu-id="4d3ce-2981">Duas letras (não diferencia maiúsculas de minúsculas) seguidas de sete dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2981">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-2982">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2982">Checksum</span></span>

<span data-ttu-id="4d3ce-2983">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2983">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-2984">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2984">Definition</span></span>

<span data-ttu-id="4d3ce-2985">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2985">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-2986">A função Func_polish_passport_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2986">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-2987">Uma palavra-chave de Keyword_polish_national_id_passport_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2987">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="4d3ce-2988">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2988">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-2989">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2989">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="4d3ce-2990">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2990">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="4d3ce-2991">Numer paszportu</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2991">Numer paszportu</span></span>
- <span data-ttu-id="4d3ce-2992">Nr.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2992">Nr.</span></span> <span data-ttu-id="4d3ce-2993">Paszportu</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2993">Paszportu</span></span>
- <span data-ttu-id="4d3ce-2994">Paszport</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2994">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="4d3ce-2995">Número do Cartão de Cidadão de Portugal</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2995">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-2996">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2996">Format</span></span>

<span data-ttu-id="4d3ce-2997">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2997">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-2998">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2998">Pattern</span></span>

<span data-ttu-id="4d3ce-2999">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-2999">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-3000">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3000">Checksum</span></span>

<span data-ttu-id="4d3ce-3001">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3001">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-3002">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3002">Definition</span></span>

<span data-ttu-id="4d3ce-3003">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3003">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3004">A expressão regular Regex_portugal_citizen_card localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3004">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3005">Uma palavra-chave de Keyword_portugal_citizen_card for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3005">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-3006">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3006">Keywords</span></span>

#### <a name="keyword_portugal_citizen_card"></a><span data-ttu-id="4d3ce-3007">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3007">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="4d3ce-3008">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3008">Citizen Card</span></span>
- <span data-ttu-id="4d3ce-3009">Cartão de Identidade Nacional</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3009">National ID Card</span></span>
- <span data-ttu-id="4d3ce-3010">CC</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3010">CC</span></span>
- <span data-ttu-id="4d3ce-3011">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3011">Cartão de Cidadão</span></span>
- <span data-ttu-id="4d3ce-3012">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3012">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="4d3ce-3013">ID nacional da Arábia Saudita</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3013">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-3014">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3014">Format</span></span>

<span data-ttu-id="4d3ce-3015">10 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3015">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-3016">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3016">Pattern</span></span>

<span data-ttu-id="4d3ce-3017">10 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3017">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-3018">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3018">Checksum</span></span>

<span data-ttu-id="4d3ce-3019">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3019">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-3020">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3020">Definition</span></span>

<span data-ttu-id="4d3ce-3021">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3021">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3022">A expressão regular Regex_saudi_arabia_national_id localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3022">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3023">Uma palavra-chave de Keyword_saudi_arabia_national_id for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3023">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-3024">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3024">Keywords</span></span>

#### <a name="keyword_saudi_arabia_national_id"></a><span data-ttu-id="4d3ce-3025">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3025">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="4d3ce-3026">Identification Card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3026">Identification Card</span></span> 
- <span data-ttu-id="4d3ce-3027">I card number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3027">I card number</span></span> 
- <span data-ttu-id="4d3ce-3028">ID number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3028">ID number</span></span> 
- <span data-ttu-id="4d3ce-3029">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3029">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="4d3ce-3030">Número do Cartão de Identidade do Registro Nacional (NRIC) de Cingapura</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3030">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-3031">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3031">Format</span></span>

<span data-ttu-id="4d3ce-3032">Nove letras e dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3032">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-3033">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3033">Pattern</span></span>

- <span data-ttu-id="4d3ce-3034">Nove letras e dígitos:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3034">Nine letters and digits:</span></span>
- <span data-ttu-id="4d3ce-3035">A letra "F", "G", "S" ou "T" (não diferenciam maiúsculas de minúsculas) </span><span class="sxs-lookup"><span data-stu-id="4d3ce-3035">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="4d3ce-3036">Sete dígitos </span><span class="sxs-lookup"><span data-stu-id="4d3ce-3036">Seven digits</span></span> 
- <span data-ttu-id="4d3ce-3037">Um dígito de verificação alfabético</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3037">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-3038">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3038">Checksum</span></span>

<span data-ttu-id="4d3ce-3039">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3039">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-3040">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3040">Definition</span></span>

<span data-ttu-id="4d3ce-3041">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3041">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3042">A expressão regular Regex_singapore_nric localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3042">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3043">Uma palavra-chave de Keyword_singapore_nric for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3043">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="4d3ce-3044">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3044">The checksum passes.</span></span>

<span data-ttu-id="4d3ce-3045">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3045">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3046">A expressão regular Regex_singapore_nric localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3046">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3047">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3047">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-3048">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3048">Keywords</span></span>
   
#### <a name="keyword_singapore_nric"></a><span data-ttu-id="4d3ce-3049">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3049">Keyword_singapore_nric</span></span>

- <span data-ttu-id="4d3ce-3050">Número do Cartão de Identidade do Registro Nacional</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3050">National Registration Identity Card</span></span> 
- <span data-ttu-id="4d3ce-3051">Número do Cartão de Identidade</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3051">Identity Card Number</span></span> 
- <span data-ttu-id="4d3ce-3052">NRIC</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3052">NRIC</span></span> 
- <span data-ttu-id="4d3ce-3053">Liga</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3053">IC</span></span> 
- <span data-ttu-id="4d3ce-3054">Número de Identificação Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3054">Foreign Identification Number</span></span> 
- <span data-ttu-id="4d3ce-3055">ALETA</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3055">FIN</span></span> 
- <span data-ttu-id="4d3ce-3056">身份证</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3056">身份证</span></span> 
- <span data-ttu-id="4d3ce-3057">身份證</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3057">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="4d3ce-3058">Número de Identificação da África do Sul</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3058">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-3059">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3059">Format</span></span>

<span data-ttu-id="4d3ce-3060">13 dígitos que podem conter espaços</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3060">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-3061">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3061">Pattern</span></span>

<span data-ttu-id="4d3ce-3062">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3062">13 digits:</span></span>
- <span data-ttu-id="4d3ce-3063">Seis dígitos no formato AAMMDD que são a data de nascimento</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3063">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="4d3ce-3064">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3064">Four digits</span></span> 
- <span data-ttu-id="4d3ce-3065">Indicador de cidadania de um dígito </span><span class="sxs-lookup"><span data-stu-id="4d3ce-3065">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="4d3ce-3066">O dígito "8" ou "9" </span><span class="sxs-lookup"><span data-stu-id="4d3ce-3066">The digit "8" or "9"</span></span> 
- <span data-ttu-id="4d3ce-3067">Um dígito que é um dígito de soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3067">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-3068">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3068">Checksum</span></span>

<span data-ttu-id="4d3ce-3069">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3069">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-3070">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3070">Definition</span></span>

<span data-ttu-id="4d3ce-3071">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3071">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3072">A função Func_south_africa_identification_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3072">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3073">Uma palavra-chave de Keyword_south_africa_identification_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3073">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="4d3ce-3074">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3074">The checksum passes.</span></span>

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-3075">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3075">Keywords</span></span>
   
#### <a name="keyword_south_africa_identification_number"></a><span data-ttu-id="4d3ce-3076">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3076">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="4d3ce-3077">Cartão de identidade</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3077">Identity card</span></span>
- <span data-ttu-id="4d3ce-3078">ID</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3078">ID</span></span>
- <span data-ttu-id="4d3ce-3079">Identificador</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3079">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="4d3ce-3080">Número do Registro de Residentes da Coreia do Sul</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3080">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-3081">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3081">Format</span></span>

<span data-ttu-id="4d3ce-3082">13 dígitos que contém um hifen</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3082">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-3083">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3083">Pattern</span></span>

<span data-ttu-id="4d3ce-3084">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3084">13 digits:</span></span>
- <span data-ttu-id="4d3ce-3085">Seis dígitos no formato AAMMDD que são a data de nascimento</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3085">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="4d3ce-3086">Um hífen</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3086">A hyphen</span></span> 
- <span data-ttu-id="4d3ce-3087">Um dígito determinado pelo século e pelo sexo </span><span class="sxs-lookup"><span data-stu-id="4d3ce-3087">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="4d3ce-3088">Código da região de nascimento de quatro dígitos </span><span class="sxs-lookup"><span data-stu-id="4d3ce-3088">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="4d3ce-3089">Um dígito usado para diferenciar as pessoas para as quais os números anteriores são idênticos </span><span class="sxs-lookup"><span data-stu-id="4d3ce-3089">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="4d3ce-3090">Um dígito de verificação.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3090">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-3091">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3091">Checksum</span></span>

<span data-ttu-id="4d3ce-3092">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3092">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-3093">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3093">Definition</span></span>

<span data-ttu-id="4d3ce-3094">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3094">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3095">A função Func_south_korea_resident_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3095">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3096">Uma palavra-chave de Keyword_south_korea_resident_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3096">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="4d3ce-3097">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3097">The checksum passes.</span></span>

<span data-ttu-id="4d3ce-3098">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3098">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3099">A função Func_south_korea_resident_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3099">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3100">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3100">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-3101">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3101">Keywords</span></span>
   
#### <a name="keyword_south_korea_resident_number"></a><span data-ttu-id="4d3ce-3102">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3102">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="4d3ce-3103">Cartão de identidade nacional</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3103">National ID card</span></span> 
- <span data-ttu-id="4d3ce-3104">Número de Registro do Cidadão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3104">Citizen's Registration Number</span></span> 
- <span data-ttu-id="4d3ce-3105">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3105">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="4d3ce-3106">RRN</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3106">RRN</span></span> 
- <span data-ttu-id="4d3ce-3107">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3107">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="4d3ce-3108">Número de seguridade social da Espanha (SSN)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3108">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-3109">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3109">Format</span></span>

<span data-ttu-id="4d3ce-3110">11 a 12 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3110">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-3111">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3111">Pattern</span></span>

<span data-ttu-id="4d3ce-3112">11-12 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3112">11-12 digits:</span></span>
- <span data-ttu-id="4d3ce-3113">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3113">Two digits</span></span> 
- <span data-ttu-id="4d3ce-3114">Uma barra (opcional)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3114">A forward slash (optional)</span></span> 
- <span data-ttu-id="4d3ce-3115">7 a 8 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3115">7-8 digits</span></span> 
- <span data-ttu-id="4d3ce-3116">Uma barra (opcional)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3116">A forward slash (optional)</span></span> 
- <span data-ttu-id="4d3ce-3117">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3117">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-3118">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3118">Checksum</span></span>

<span data-ttu-id="4d3ce-3119">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3119">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-3120">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3120">Definition</span></span>

<span data-ttu-id="4d3ce-3121">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3121">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3122">A função Func_spanish_social_security_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3122">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3123">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3123">The checksum passes.</span></span>

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-3124">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3124">Keywords</span></span>

<span data-ttu-id="4d3ce-3125">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3125">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="4d3ce-3126">Cadeia de caracteres de conexão do SQL Server</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3126">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-3127">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3127">Format</span></span>

<span data-ttu-id="4d3ce-3128">A cadeia de caracteres "User ID", "User ID", "UID" ou "UserId" seguida dos caracteres e cadeias de caracteres descritos no padrão abaixo.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3128">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-3129">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3129">Pattern</span></span>

- <span data-ttu-id="4d3ce-3130">A cadeia de caracteres "User ID", "User ID", "UID" ou "UserId"</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3130">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="4d3ce-3131">Qualquer combinação entre 1-200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3131">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="4d3ce-3132">A cadeia de caracteres "password" ou "pwd", onde "pwd" não é precedida por uma letra minúscula</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3132">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="4d3ce-3133">Um sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3133">An equal sign (=)</span></span>
- <span data-ttu-id="4d3ce-3134">Qualquer caractere que não seja um cifrão ($), símbolo de porcentagem (%), maior que símbolo (>), no símbolo (@), aspas ("), ponto e vírgula (;), chave esquerda ([) ou colchete esquerdo ({)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3134">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="4d3ce-3135">Qualquer combinação de 7-128 caracteres que não seja um ponto-e-vírgula (;), barra (/) ou aspas (")</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3135">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="4d3ce-3136">Um ponto e vírgula (;) ou aspas (")</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3136">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-3137">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3137">Checksum</span></span>

<span data-ttu-id="4d3ce-3138">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3138">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-3139">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3139">Definition</span></span>

<span data-ttu-id="4d3ce-3140">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3140">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3141">A expressão regular CEP_Regex_SQLServerConnectionString localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3141">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3142">Uma palavra-chave de CEP_GlobalFilter **não** é encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3142">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="4d3ce-3143">A expressão regular CEP_PasswordPlaceHolder não **localiza o** conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3143">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3144">A expressão regular CEP_CommonExampleKeywords não **localiza o** conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3144">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-3145">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3145">Keywords</span></span>

#### <a name="cep_globalfilter"></a><span data-ttu-id="4d3ce-3146">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3146">CEP_GlobalFilter</span></span>

- <span data-ttu-id="4d3ce-3147">algumas-senha</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3147">some-password</span></span>
- <span data-ttu-id="4d3ce-3148">somepassword</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3148">somepassword</span></span>
- <span data-ttu-id="4d3ce-3149">secretPassword</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3149">secretPassword</span></span>
- <span data-ttu-id="4d3ce-3150">ISV</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3150">sample</span></span>

#### <a name="cep_passwordplaceholder"></a><span data-ttu-id="4d3ce-3151">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3151">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="4d3ce-3152">(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3152">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="4d3ce-3153">Senha ou pwd seguidos por 0-2 espaços, um sinal de igual (=), 0-2 espaços e um asterisco (\*)--ou--</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3153">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="4d3ce-3154">Senha ou pwd seguido por:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3154">Password or pwd followed by:</span></span>
    - <span data-ttu-id="4d3ce-3155">Sinal de igual (=)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3155">Equal sign (=)</span></span>
    - <span data-ttu-id="4d3ce-3156">Sinal de menor que (<)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3156">Less than symbol (<)</span></span>
    - <span data-ttu-id="4d3ce-3157">Qualquer combinação de 1-200 caracteres que sejam letras maiúsculas ou minúsculas, dígitos, um asterisco (\*), hífen (-), sublinhado (_) ou caractere de espaço em branco</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3157">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="4d3ce-3158">Símbolo maior que (>)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3158">Greater than symbol (>)</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="4d3ce-3159">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3159">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="4d3ce-3160">(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3160">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="4d3ce-3161">contoso</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3161">contoso</span></span>
- <span data-ttu-id="4d3ce-3162">fabrikam</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3162">fabrikam</span></span>
- <span data-ttu-id="4d3ce-3163">Northwind</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3163">northwind</span></span>
- <span data-ttu-id="4d3ce-3164">área restrita</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3164">sandbox</span></span>
- <span data-ttu-id="4d3ce-3165">onebox</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3165">onebox</span></span>
- <span data-ttu-id="4d3ce-3166">localhost</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3166">localhost</span></span>
- <span data-ttu-id="4d3ce-3167">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3167">127.0.0.1</span></span>
- <span data-ttu-id="4d3ce-3168">testacs.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3168">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="4d3ce-3169">suplementos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3169">com</span></span>
- <span data-ttu-id="4d3ce-3170">s-int.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3170">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="4d3ce-3171">Netlogon</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3171">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="4d3ce-3172">ID nacional da Suécia</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3172">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-3173">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3173">Format</span></span>

<span data-ttu-id="4d3ce-3174">10 ou 12 dígitos e um delimitador opcional</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3174">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-3175">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3175">Pattern</span></span>

<span data-ttu-id="4d3ce-3176">10 ou 12 dígitos e um delimitador opcional:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3176">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="4d3ce-3177">2 a 4 dígitos (opcionais)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3177">2-4 digits (optional)</span></span> 
- <span data-ttu-id="4d3ce-3178">Seis dígitos no formato de data AAMMDD</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3178">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="4d3ce-3179">Um delimitador de "-" ou "+" (opcional), mais</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3179">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="4d3ce-3180">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3180">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-3181">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3181">Checksum</span></span>

<span data-ttu-id="4d3ce-3182">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3182">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-3183">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3183">Definition</span></span>

<span data-ttu-id="4d3ce-3184">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3184">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3185">A função Func_swedish_national_identifier localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3185">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3186">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3186">The checksum passes.</span></span>

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-3187">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3187">Keywords</span></span>

<span data-ttu-id="4d3ce-3188">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3188">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="4d3ce-3189">Número de passaporte da Suécia</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3189">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-3190">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3190">Format</span></span>

<span data-ttu-id="4d3ce-3191">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3191">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-3192">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3192">Pattern</span></span>

<span data-ttu-id="4d3ce-3193">Oito dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3193">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-3194">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3194">Checksum</span></span>

<span data-ttu-id="4d3ce-3195">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3195">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-3196">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3196">Definition</span></span>

<span data-ttu-id="4d3ce-3197">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3197">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3198">A expressão regular Regex_sweden_passport_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3198">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3199">Uma das seguintes opções for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3199">One of the following is true:</span></span>
    - <span data-ttu-id="4d3ce-3200">Uma palavra-chave de Keyword_passport for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3200">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="4d3ce-3201">Uma palavra-chave de Keyword_sweden_passport for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3201">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-3202">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3202">Keywords</span></span>
   
#### <a name="keyword_sweden_passport"></a><span data-ttu-id="4d3ce-3203">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3203">Keyword_sweden_passport</span></span>

- <span data-ttu-id="4d3ce-3204">visa requirements</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3204">visa requirements</span></span> 
- <span data-ttu-id="4d3ce-3205">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3205">Alien Registration Card</span></span> 
- <span data-ttu-id="4d3ce-3206">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3206">Schengen visas</span></span> 
- <span data-ttu-id="4d3ce-3207">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3207">Schengen visa</span></span> 
- <span data-ttu-id="4d3ce-3208">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3208">Visa Processing</span></span> 
- <span data-ttu-id="4d3ce-3209">Visa Type</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3209">Visa Type</span></span> 
- <span data-ttu-id="4d3ce-3210">Single Entry</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3210">Single Entry</span></span> 
- <span data-ttu-id="4d3ce-3211">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3211">Multiple Entry</span></span> 
- <span data-ttu-id="4d3ce-3212">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3212">G3 Processing Fees</span></span> 

#### <a name="keyword_passport"></a><span data-ttu-id="4d3ce-3213">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3213">Keyword_passport</span></span>

- <span data-ttu-id="4d3ce-3214">Passport Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3214">Passport Number</span></span> 
- <span data-ttu-id="4d3ce-3215">Passport No</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3215">Passport No</span></span> 
- <span data-ttu-id="4d3ce-3216">Passport #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3216">Passport #</span></span> 
- <span data-ttu-id="4d3ce-3217">Passaport #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3217">Passport#</span></span> 
- <span data-ttu-id="4d3ce-3218">Passportid</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3218">PassportID</span></span> 
- <span data-ttu-id="4d3ce-3219">Passportno</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3219">Passportno</span></span> 
- <span data-ttu-id="4d3ce-3220">passportnumber</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3220">passportnumber</span></span> 
- <span data-ttu-id="4d3ce-3221">パスポート</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3221">パスポート</span></span> 
- <span data-ttu-id="4d3ce-3222">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3222">パスポート番号</span></span> 
- <span data-ttu-id="4d3ce-3223">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3223">パスポートのNum</span></span> 
- <span data-ttu-id="4d3ce-3224">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3224">パスポート＃</span></span> 
- <span data-ttu-id="4d3ce-3225">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3225">Numéro de passeport</span></span> 
- <span data-ttu-id="4d3ce-3226">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3226">Passeport n °</span></span> 
- <span data-ttu-id="4d3ce-3227">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3227">Passeport Non</span></span> 
- <span data-ttu-id="4d3ce-3228">Passeport #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3228">Passeport #</span></span> 
- <span data-ttu-id="4d3ce-3229">Passeport #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3229">Passeport#</span></span> 
- <span data-ttu-id="4d3ce-3230">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3230">PasseportNon</span></span> 
- <span data-ttu-id="4d3ce-3231">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3231">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="4d3ce-3232">Código SWIFT</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3232">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-3233">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3233">Format</span></span>

<span data-ttu-id="4d3ce-3234">Quatro letras seguidas por 5 a 31 letras ou dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3234">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-3235">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3235">Pattern</span></span>

<span data-ttu-id="4d3ce-3236">Quatro letras seguidas por 5 a 31 letras ou dígitos:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3236">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="4d3ce-3237">Código bancário de quatro letras (não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3237">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="4d3ce-3238">Um espaço opcional</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3238">An optional space</span></span> 
- <span data-ttu-id="4d3ce-3239">4 a 28 letras ou dígitos (o número de conta bancária básica (BBAN))</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3239">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="4d3ce-3240">Um espaço opcional</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3240">An optional space</span></span> 
- <span data-ttu-id="4d3ce-3241">1 a 3 letras ou dígitos (restante do BBAN)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3241">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-3242">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3242">Checksum</span></span>

<span data-ttu-id="4d3ce-3243">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3243">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-3244">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3244">Definition</span></span>

<span data-ttu-id="4d3ce-3245">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3245">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3246">A expressão regular Regex_swift localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3246">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3247">Uma palavra-chave de Keyword_swift for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3247">A keyword from Keyword_swift is found.</span></span>

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-3248">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3248">Keywords</span></span>
   
#### <a name="keyword_swift"></a><span data-ttu-id="4d3ce-3249">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3249">Keyword_swift</span></span>

- <span data-ttu-id="4d3ce-3250">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3250">international organization for standardization 9362</span></span> 
- <span data-ttu-id="4d3ce-3251">iso 9362</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3251">iso 9362</span></span> 
- <span data-ttu-id="4d3ce-3252">iso9362</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3252">iso9362</span></span> 
- <span data-ttu-id="4d3ce-3253">Swift\#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3253">swift\#</span></span> 
- <span data-ttu-id="4d3ce-3254">swiftcode</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3254">swiftcode</span></span> 
- <span data-ttu-id="4d3ce-3255">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3255">swiftnumber</span></span> 
- <span data-ttu-id="4d3ce-3256">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3256">swiftroutingnumber</span></span> 
- <span data-ttu-id="4d3ce-3257">swift code</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3257">swift code</span></span> 
- <span data-ttu-id="4d3ce-3258">swift number #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3258">swift number #</span></span> 
- <span data-ttu-id="4d3ce-3259">swift routing number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3259">swift routing number</span></span> 
- <span data-ttu-id="4d3ce-3260">bic number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3260">bic number</span></span> 
- <span data-ttu-id="4d3ce-3261">bic code</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3261">bic code</span></span> 
- <span data-ttu-id="4d3ce-3262">bic\#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3262">bic \#</span></span> 
- <span data-ttu-id="4d3ce-3263">bic\#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3263">bic\#</span></span> 
- <span data-ttu-id="4d3ce-3264">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3264">bank identifier code</span></span> 
- <span data-ttu-id="4d3ce-3265">標準化 9362</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3265">標準化9362</span></span> 
- <span data-ttu-id="4d3ce-3266">迅速＃</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3266">迅速＃</span></span> 
- <span data-ttu-id="4d3ce-3267">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3267">SWIFTコード</span></span> 
- <span data-ttu-id="4d3ce-3268">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3268">SWIFT番号</span></span> 
- <span data-ttu-id="4d3ce-3269">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3269">迅速なルーティング番号</span></span> 
- <span data-ttu-id="4d3ce-3270">BIC番号</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3270">BIC番号</span></span> 
- <span data-ttu-id="4d3ce-3271">BICコード</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3271">BICコード</span></span> 
- <span data-ttu-id="4d3ce-3272">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3272">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="4d3ce-3273">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3273">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="4d3ce-3274">rápida\#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3274">rapide \#</span></span> 
- <span data-ttu-id="4d3ce-3275">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3275">code SWIFT</span></span> 
- <span data-ttu-id="4d3ce-3276">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3276">le numéro de swift</span></span> 
- <span data-ttu-id="4d3ce-3277">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3277">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="4d3ce-3278">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3278">le numéro BIC</span></span> 
- <span data-ttu-id="4d3ce-3279">\#BIC</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3279">\# BIC</span></span> 
- <span data-ttu-id="4d3ce-3280">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3280">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="4d3ce-3281">ID nacional de Taiwan</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3281">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-3282">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3282">Format</span></span>

<span data-ttu-id="4d3ce-3283">Uma letra (em inglês) seguida de nove dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3283">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-3284">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3284">Pattern</span></span>

<span data-ttu-id="4d3ce-3285">Uma letra (em inglês) seguida de nove dígitos:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3285">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="4d3ce-3286">Uma letra (em inglês, não diferencia maiúscula de minúscula)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3286">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="4d3ce-3287">O dígito "1" ou "2"</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3287">The digit "1" or "2"</span></span> 
- <span data-ttu-id="4d3ce-3288">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3288">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-3289">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3289">Checksum</span></span>

<span data-ttu-id="4d3ce-3290">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3290">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-3291">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3291">Definition</span></span>

<span data-ttu-id="4d3ce-3292">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3292">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3293">A função Func_taiwanese_national_id localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3293">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3294">Uma palavra-chave de Keyword_taiwanese_national_id for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3294">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="4d3ce-3295">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3295">The checksum passes.</span></span>

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-3296">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3296">Keywords</span></span>

#### <a name="keyword_taiwanese_national_id"></a><span data-ttu-id="4d3ce-3297">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3297">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="4d3ce-3298">身份證字號</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3298">身份證字號</span></span> 
- <span data-ttu-id="4d3ce-3299">身份證</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3299">身份證</span></span> 
- <span data-ttu-id="4d3ce-3300">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3300">身份證號碼</span></span> 
- <span data-ttu-id="4d3ce-3301">身份證號</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3301">身份證號</span></span> 
- <span data-ttu-id="4d3ce-3302">身分證字號</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3302">身分證字號</span></span> 
- <span data-ttu-id="4d3ce-3303">身分證</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3303">身分證</span></span> 
- <span data-ttu-id="4d3ce-3304">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3304">身分證號碼</span></span> 
- <span data-ttu-id="4d3ce-3305">身份證號</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3305">身份證號</span></span> 
- <span data-ttu-id="4d3ce-3306">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3306">身分證統一編號</span></span> 
- <span data-ttu-id="4d3ce-3307">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3307">國民身分證統一編號</span></span> 
- <span data-ttu-id="4d3ce-3308">簽名</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3308">簽名</span></span> 
- <span data-ttu-id="4d3ce-3309">蓋章</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3309">蓋章</span></span> 
- <span data-ttu-id="4d3ce-3310">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3310">簽名或蓋章</span></span> 
- <span data-ttu-id="4d3ce-3311">簽章</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3311">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="4d3ce-3312">	Número de passaporte de Taiwan</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3312">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-3313">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3313">Format</span></span>

- <span data-ttu-id="4d3ce-3314">Número de passaporte biométrico: nove dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3314">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="4d3ce-3315">Número de passaporte não biométrico: nove dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3315">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-3316">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3316">Pattern</span></span>
<span data-ttu-id="4d3ce-3317">Número de passaporte biométrico:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3317">Biometric passport number:</span></span>
- <span data-ttu-id="4d3ce-3318">O dígito "3" </span><span class="sxs-lookup"><span data-stu-id="4d3ce-3318">The digit "3"</span></span> 
- <span data-ttu-id="4d3ce-3319">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3319">Eight digits</span></span>

<span data-ttu-id="4d3ce-3320">Número de passaporte não biométrico:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3320">Non-biometric passport number:</span></span>
- <span data-ttu-id="4d3ce-3321">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3321">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-3322">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3322">Checksum</span></span>

<span data-ttu-id="4d3ce-3323">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3323">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-3324">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3324">Definition</span></span>

<span data-ttu-id="4d3ce-3325">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3325">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3326">A expressão regular Regex_taiwan_passport localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3326">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3327">Uma palavra-chave de Keyword_taiwan_passport for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3327">A keyword from Keyword_taiwan_passport is found.</span></span>

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-3328">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3328">Keywords</span></span>

#### <a name="keyword_taiwan_passport"></a><span data-ttu-id="4d3ce-3329">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3329">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="4d3ce-3330">Número de passaporte ROC</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3330">ROC passport number</span></span> 
- <span data-ttu-id="4d3ce-3331">Número de passaporte</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3331">Passport number</span></span> 
- <span data-ttu-id="4d3ce-3332">Nº de passaporte</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3332">Passport no</span></span> 
- <span data-ttu-id="4d3ce-3333">Núm de Passaporte</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3333">Passport Num</span></span> 
- <span data-ttu-id="4d3ce-3334">Passport #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3334">Passport #</span></span> 
- <span data-ttu-id="4d3ce-3335">护照</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3335">护照</span></span> 
- <span data-ttu-id="4d3ce-3336">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3336">中華民國護照</span></span> 
- <span data-ttu-id="4d3ce-3337">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3337">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="4d3ce-3338">Número do Certificado de residente de Taiwan (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3338">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-3339">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3339">Format</span></span>

<span data-ttu-id="4d3ce-3340">10 letras e dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3340">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-3341">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3341">Pattern</span></span>

<span data-ttu-id="4d3ce-3342">10 letras e dígitos:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3342">10 letters and digits:</span></span>
- <span data-ttu-id="4d3ce-3343">Duas letras (não diferenciam maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3343">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="4d3ce-3344">Oito dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3344">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-3345">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3345">Checksum</span></span>

<span data-ttu-id="4d3ce-3346">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3346">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-3347">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3347">Definition</span></span>

<span data-ttu-id="4d3ce-3348">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3348">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3349">A expressão regular Regex_taiwan_resident_certificate localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3349">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3350">Uma palavra-chave de Keyword_taiwan_resident_certificate for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3350">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-3351">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3351">Keywords</span></span>

#### <a name="keyword_taiwan_resident_certificate"></a><span data-ttu-id="4d3ce-3352">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3352">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="4d3ce-3353">Certificado de Residente</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3353">Resident Certificate</span></span> 
- <span data-ttu-id="4d3ce-3354">Cert de Residente</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3354">Resident Cert</span></span> 
- <span data-ttu-id="4d3ce-3355">Cert. de Residente
</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3355">Resident Cert.</span></span> 
- <span data-ttu-id="4d3ce-3356">Cartão de identificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3356">Identification card</span></span> 
- <span data-ttu-id="4d3ce-3357">Certificado de Residente Alien</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3357">Alien Resident Certificate</span></span> 
- <span data-ttu-id="4d3ce-3358">ARC</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3358">ARC</span></span> 
- <span data-ttu-id="4d3ce-3359">Certificado de Residente da Área de Taiwan</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3359">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="4d3ce-3360">TARC</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3360">TARC</span></span> 
- <span data-ttu-id="4d3ce-3361">居留證</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3361">居留證</span></span> 
- <span data-ttu-id="4d3ce-3362">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3362">外僑居留證</span></span> 
- <span data-ttu-id="4d3ce-3363">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3363">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="4d3ce-3364">Código de identificação de população em tailandês</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3364">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-3365">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3365">Format</span></span>

<span data-ttu-id="4d3ce-3366">13 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3366">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-3367">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3367">Pattern</span></span>

<span data-ttu-id="4d3ce-3368">13 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3368">13 digits:</span></span>
- <span data-ttu-id="4d3ce-3369">O primeiro dígito não é 0 ou 9</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3369">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="4d3ce-3370">12 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3370">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-3371">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3371">Checksum</span></span>

<span data-ttu-id="4d3ce-3372">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3372">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-3373">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3373">Definition</span></span>

<span data-ttu-id="4d3ce-3374">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3374">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3375">A função Func_Thai_Citizen_Id localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3375">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3376">Uma palavra-chave de Keyword_Thai_Citizen_Id for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3376">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="4d3ce-3377">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3377">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3378">A função Func_Thai_Citizen_Id localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3378">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-3379">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3379">Keywords</span></span>

#### <a name="keyword_thai_citizen_id"></a><span data-ttu-id="4d3ce-3380">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3380">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="4d3ce-3381">Número de Identificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3381">ID Number</span></span>
- <span data-ttu-id="4d3ce-3382">Número de identificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3382">Identification Number</span></span>
- <span data-ttu-id="4d3ce-3383">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3383">บัตรประชาชน</span></span>
- <span data-ttu-id="4d3ce-3384">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3384">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="4d3ce-3385">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3385">บัตรประชาชน</span></span>
- <span data-ttu-id="4d3ce-3386">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3386">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="4d3ce-3387">Número de identificação nacional turco</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3387">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-3388">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3388">Format</span></span>

<span data-ttu-id="4d3ce-3389">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3389">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-3390">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3390">Pattern</span></span>

<span data-ttu-id="4d3ce-3391">11 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3391">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-3392">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3392">Checksum</span></span>

<span data-ttu-id="4d3ce-3393">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3393">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-3394">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3394">Definition</span></span>

<span data-ttu-id="4d3ce-3395">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3395">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3396">A função Func_Turkish_National_Id localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3396">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3397">Uma palavra-chave de Keyword_Turkish_National_Id for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3397">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="4d3ce-3398">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3398">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3399">A função Func_Turkish_National_Id localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3399">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-3400">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3400">Keywords</span></span>

#### <a name="keyword_turkish_national_id"></a><span data-ttu-id="4d3ce-3401">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3401">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="4d3ce-3402">Kimlik TC não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3402">TC Kimlik No</span></span>
- <span data-ttu-id="4d3ce-3403">TC Kimlik numarası</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3403">TC Kimlik numarası</span></span>
- <span data-ttu-id="4d3ce-3404">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3404">Vatandaşlık numarası</span></span>
- <span data-ttu-id="4d3ce-3405">Vatandaşlık não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3405">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="4d3ce-p144">Número de carteira de motorista do Reino Unido</span><span class="sxs-lookup"><span data-stu-id="4d3ce-p144">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-3408">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3408">Format</span></span>

<span data-ttu-id="4d3ce-3409">Combinação de 18 letras e dígitos no formato especificado</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3409">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-3410">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3410">Pattern</span></span>

<span data-ttu-id="4d3ce-3411">18 letras e dígitos:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3411">18 letters and digits:</span></span>
- <span data-ttu-id="4d3ce-3412">Cinco letras (não diferenciam maiúsculas de minúsculas) ou o dígito "9" em vez de uma letra</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3412">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="4d3ce-3413">Um dígito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3413">One digit</span></span> 
- <span data-ttu-id="4d3ce-3414">Cinco dígitos no formato de data MMDDY para data de nascimento (o sétimo caractere é incrementado por 50 se o driver for fêmea, ou seja, 51 a 62 em vez de 01 a 12)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3414">Five digits in the date format MMDDY for date of birth (7th character is incremented by 50 if driver is female, i.e. 51 to 62 instead of 01 to 12)</span></span>
- <span data-ttu-id="4d3ce-3415">Duas letras (não diferenciam maiúsculas de minúsculas) ou o dígito "9" em vez de uma letra</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3415">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="4d3ce-3416">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3416">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-3417">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3417">Checksum</span></span>

<span data-ttu-id="4d3ce-3418">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3418">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-3419">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3419">Definition</span></span>

<span data-ttu-id="4d3ce-3420">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3420">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3421">A função Func_uk_drivers_license localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3421">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3422">Uma palavra-chave de Keyword_uk_drivers_license for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3422">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="4d3ce-3423">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3423">The checksum passes.</span></span>

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-3424">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3424">Keywords</span></span>

#### <a name="keyword_uk_drivers_license"></a><span data-ttu-id="4d3ce-3425">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3425">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="4d3ce-3426">DVLA</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3426">DVLA</span></span> 
- <span data-ttu-id="4d3ce-3427">light vans</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3427">light vans</span></span> 
- <span data-ttu-id="4d3ce-3428">quadbikes</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3428">quadbikes</span></span> 
- <span data-ttu-id="4d3ce-3429">motor cars</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3429">motor cars</span></span> 
- <span data-ttu-id="4d3ce-3430">125cc</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3430">125cc</span></span> 
- <span data-ttu-id="4d3ce-3431">sidecar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3431">sidecar</span></span> 
- <span data-ttu-id="4d3ce-3432">tricycles</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3432">tricycles</span></span> 
- <span data-ttu-id="4d3ce-3433">motorcycles</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3433">motorcycles</span></span> 
- <span data-ttu-id="4d3ce-3434">photocard licence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3434">photocard licence</span></span> 
- <span data-ttu-id="4d3ce-3435">learner drivers</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3435">learner drivers</span></span> 
- <span data-ttu-id="4d3ce-3436">licence holder</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3436">licence holder</span></span> 
- <span data-ttu-id="4d3ce-3437">licence holders</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3437">licence holders</span></span> 
- <span data-ttu-id="4d3ce-3438">driving licences</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3438">driving licences</span></span> 
- <span data-ttu-id="4d3ce-3439">driving licence</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3439">driving licence</span></span> 
- <span data-ttu-id="4d3ce-3440">dual control car</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3440">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="4d3ce-p145">Número de Título de Eleitor do Reino Unido</span><span class="sxs-lookup"><span data-stu-id="4d3ce-p145">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-3443">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3443">Format</span></span>

<span data-ttu-id="4d3ce-3444">Duas letras seguidas por 1 a 4 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3444">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-3445">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3445">Pattern</span></span>

<span data-ttu-id="4d3ce-3446">Duas letras (não diferencia maiúsculas de minúsculas) seguidas de 1 a 4 anos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3446">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-3447">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3447">Checksum</span></span>

<span data-ttu-id="4d3ce-3448">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3448">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-3449">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3449">Definition</span></span>

<span data-ttu-id="4d3ce-3450">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3450">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3451">A expressão regular Regex_uk_electoral localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3451">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3452">Uma palavra-chave de Keyword_uk_electoral for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3452">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-3453">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3453">Keywords</span></span>

#### <a name="keyword_uk_electoral"></a><span data-ttu-id="4d3ce-3454">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3454">Keyword_uk_electoral</span></span>

- <span data-ttu-id="4d3ce-3455">council nomination</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3455">council nomination</span></span> 
- <span data-ttu-id="4d3ce-3456">nomination form</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3456">nomination form</span></span> 
- <span data-ttu-id="4d3ce-3457">electoral register</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3457">electoral register</span></span> 
- <span data-ttu-id="4d3ce-3458">electoral roll</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3458">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="4d3ce-p146">Número do serviço de saúde nacional do Reino Unido</span><span class="sxs-lookup"><span data-stu-id="4d3ce-p146">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-3461">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3461">Format</span></span>

<span data-ttu-id="4d3ce-3462">10 a 17 dígitos separados por espaços</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3462">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-3463">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3463">Pattern</span></span>

<span data-ttu-id="4d3ce-3464">10 a 17 dígitos:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3464">10-17 digits:</span></span>
- <span data-ttu-id="4d3ce-3465">3 ou 10 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3465">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="4d3ce-3466">Um espaço</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3466">A space</span></span> 
- <span data-ttu-id="4d3ce-3467">Três dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3467">Three digits</span></span> 
- <span data-ttu-id="4d3ce-3468">Um espaço</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3468">A space</span></span> 
- <span data-ttu-id="4d3ce-3469">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3469">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-3470">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3470">Checksum</span></span>

<span data-ttu-id="4d3ce-3471">Sim</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3471">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-3472">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3472">Definition</span></span>

<span data-ttu-id="4d3ce-3473">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3474">A função Func_uk_nhs_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3474">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3475">Uma das seguintes opções for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3475">One of the following is true:</span></span>
    - <span data-ttu-id="4d3ce-3476">Uma palavra-chave de Keyword_uk_nhs_number for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3476">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="4d3ce-3477">Uma palavra-chave de Keyword_uk_nhs_number1 for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3477">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="4d3ce-3478">Uma palavra-chave de Keyword_uk_nhs_number_dob for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3478">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="4d3ce-3479">A soma de verificação passa.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3479">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-3480">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3480">Keywords</span></span>
   
#### <a name="keyword_uk_nhs_number"></a><span data-ttu-id="4d3ce-3481">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3481">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="4d3ce-3482">national health service</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3482">national health service</span></span> 
- <span data-ttu-id="4d3ce-3483">NHS</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3483">nhs</span></span> 
- <span data-ttu-id="4d3ce-3484">health services authority</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3484">health services authority</span></span> 
- <span data-ttu-id="4d3ce-3485">health authority</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3485">health authority</span></span>

#### <a name="keyword_uk_nhs_number1"></a><span data-ttu-id="4d3ce-3486">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3486">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="4d3ce-3487">patient id</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3487">patient id</span></span> 
- <span data-ttu-id="4d3ce-3488">patient identification</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3488">patient identification</span></span> 
- <span data-ttu-id="4d3ce-3489">patient no</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3489">patient no</span></span> 
- <span data-ttu-id="4d3ce-3490">patient number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3490">patient number</span></span>

#### <a name="keyword_uk_nhs_number_dob"></a><span data-ttu-id="4d3ce-3491">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3491">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="4d3ce-3492">GP</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3492">GP</span></span> 
- <span data-ttu-id="4d3ce-3493">DOB</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3493">DOB</span></span> 
- <span data-ttu-id="4d3ce-3494">D. O. B</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3494">D.O.B</span></span> 
- <span data-ttu-id="4d3ce-3495">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3495">Date of Birth</span></span> 
- <span data-ttu-id="4d3ce-3496">Birth Date</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3496">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="4d3ce-p147">Número de seguro nacional do Reino Unido (NINO)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-p147">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-3499">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3499">Format</span></span>

<span data-ttu-id="4d3ce-3500">7 caracteres ou 9 caracteres separados por espaços ou traços</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3500">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-3501">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3501">Pattern</span></span>

<span data-ttu-id="4d3ce-3502">Dois padrões possíveis:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3502">Two possible patterns:</span></span>

- <span data-ttu-id="4d3ce-3503">Duas letras (NINOs válidas usam apenas determinados caracteres neste prefixo, que esse padrão valida; não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3503">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="4d3ce-3504">Seis dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3504">Six digits</span></span>
- <span data-ttu-id="4d3ce-3505">"A", "B", "C" ou "(como o prefixo, apenas determinados caracteres são permitidos no sufixo; não diferencia maiúsculas de minúsculas)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3505">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="4d3ce-3506">OU</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3506">OR</span></span>

- <span data-ttu-id="4d3ce-3507">Duas letras</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3507">Two letters</span></span>
- <span data-ttu-id="4d3ce-3508">Um espaço ou um traço</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3508">A space or dash</span></span>
- <span data-ttu-id="4d3ce-3509">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3509">Two digits</span></span>
- <span data-ttu-id="4d3ce-3510">Um espaço ou um traço</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3510">A space or dash</span></span>
- <span data-ttu-id="4d3ce-3511">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3511">Two digits</span></span>
- <span data-ttu-id="4d3ce-3512">Um espaço ou um traço</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3512">A space or dash</span></span>
- <span data-ttu-id="4d3ce-3513">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3513">Two digits</span></span>
- <span data-ttu-id="4d3ce-3514">Um espaço ou um traço</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3514">A space or dash</span></span>
- <span data-ttu-id="4d3ce-3515">' A ', ' B ', ' C' ou ' d'</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3515">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-3516">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3516">Checksum</span></span>

<span data-ttu-id="4d3ce-3517">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3517">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-3518">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3518">Definition</span></span>

<span data-ttu-id="4d3ce-3519">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3520">A função Func_uk_nino localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3520">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3521">Uma palavra-chave de Keyword_uk_nino for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3521">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="4d3ce-3522">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3522">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3523">A função Func_uk_nino localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3523">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3524">Nenhuma palavra-chave de Keyword_uk_nino for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3524">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-3525">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3525">Keywords</span></span>

#### <a name="keyword_uk_nino"></a><span data-ttu-id="4d3ce-3526">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3526">Keyword_uk_nino</span></span>

- <span data-ttu-id="4d3ce-3527">national insurance number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3527">national insurance number</span></span> 
- <span data-ttu-id="4d3ce-3528">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3528">national insurance contributions</span></span> 
- <span data-ttu-id="4d3ce-3529">protection act</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3529">protection act</span></span> 
- <span data-ttu-id="4d3ce-3530">seguro</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3530">insurance</span></span> 
- <span data-ttu-id="4d3ce-3531">social security number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3531">social security number</span></span> 
- <span data-ttu-id="4d3ce-3532">insurance application</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3532">insurance application</span></span> 
- <span data-ttu-id="4d3ce-3533">medical application</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3533">medical application</span></span> 
- <span data-ttu-id="4d3ce-3534">social insurance</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3534">social insurance</span></span> 
- <span data-ttu-id="4d3ce-3535">medical attention</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3535">medical attention</span></span> 
- <span data-ttu-id="4d3ce-3536">social security</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3536">social security</span></span> 
- <span data-ttu-id="4d3ce-3537">great britain</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3537">great britain</span></span> 
- <span data-ttu-id="4d3ce-3538">seguro</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3538">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="4d3ce-p148">Número de passaporte dos EUA/Reino Unido</span><span class="sxs-lookup"><span data-stu-id="4d3ce-p148">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-3541">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3541">Format</span></span>

<span data-ttu-id="4d3ce-3542">Nove dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3542">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-3543">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3543">Pattern</span></span>

<span data-ttu-id="4d3ce-3544">Nove dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3544">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-3545">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3545">Checksum</span></span>

<span data-ttu-id="4d3ce-3546">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3546">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-3547">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3547">Definition</span></span>

<span data-ttu-id="4d3ce-3548">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3548">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3549">A função Func_usa_uk_passport localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3549">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3550">Uma palavra-chave de Keyword_passport for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3550">A keyword from Keyword_passport is found.</span></span>

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-3551">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3551">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="4d3ce-3552">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3552">Keyword_passport</span></span>

- <span data-ttu-id="4d3ce-3553">Passport Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3553">Passport Number</span></span> 
- <span data-ttu-id="4d3ce-3554">Passport No</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3554">Passport No</span></span> 
- <span data-ttu-id="4d3ce-3555">Passport #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3555">Passport #</span></span> 
- <span data-ttu-id="4d3ce-3556">Passaport #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3556">Passport#</span></span> 
- <span data-ttu-id="4d3ce-3557">Passportid</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3557">PassportID</span></span> 
- <span data-ttu-id="4d3ce-3558">Passportno</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3558">Passportno</span></span> 
- <span data-ttu-id="4d3ce-3559">passportnumber</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3559">passportnumber</span></span> 
- <span data-ttu-id="4d3ce-3560">パスポート</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3560">パスポート</span></span> 
- <span data-ttu-id="4d3ce-3561">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3561">パスポート番号</span></span> 
- <span data-ttu-id="4d3ce-3562">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3562">パスポートのNum</span></span> 
- <span data-ttu-id="4d3ce-3563">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3563">パスポート＃</span></span> 
- <span data-ttu-id="4d3ce-3564">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3564">Numéro de passeport</span></span> 
- <span data-ttu-id="4d3ce-3565">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3565">Passeport n °</span></span> 
- <span data-ttu-id="4d3ce-3566">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3566">Passeport Non</span></span> 
- <span data-ttu-id="4d3ce-3567">Passeport #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3567">Passeport #</span></span> 
- <span data-ttu-id="4d3ce-3568">Passeport #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3568">Passeport#</span></span> 
- <span data-ttu-id="4d3ce-3569">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3569">PasseportNon</span></span> 
- <span data-ttu-id="4d3ce-3570">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3570">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="4d3ce-3571">Número de conta bancária dos EUA</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3571">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-3572">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3572">Format</span></span>

<span data-ttu-id="4d3ce-3573">8 a 17 dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3573">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-3574">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3574">Pattern</span></span>

<span data-ttu-id="4d3ce-3575">8 a 17 dígitos consecutivos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3575">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-3576">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3576">Checksum</span></span>

<span data-ttu-id="4d3ce-3577">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3577">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-3578">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3578">Definition</span></span>

<span data-ttu-id="4d3ce-3579">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3579">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3580">A expressão regular Regex_usa_bank_account_number localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3580">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3581">Uma palavra-chave de Keyword_usa_Bank_Account for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3581">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-3582">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3582">Keywords</span></span>

#### <a name="keyword_usa_bank_account"></a><span data-ttu-id="4d3ce-3583">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3583">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="4d3ce-3584">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3584">Checking Account Number</span></span> 
- <span data-ttu-id="4d3ce-3585">Checking Account</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3585">Checking Account</span></span> 
- <span data-ttu-id="4d3ce-3586">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3586">Checking Account #</span></span> 
- <span data-ttu-id="4d3ce-3587">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3587">Checking Acct Number</span></span> 
- <span data-ttu-id="4d3ce-3588">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3588">Checking Acct #</span></span> 
- <span data-ttu-id="4d3ce-3589">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3589">Checking Acct No.</span></span> 
- <span data-ttu-id="4d3ce-3590">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3590">Checking Account No.</span></span> 
- <span data-ttu-id="4d3ce-3591">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3591">Bank Account Number</span></span> 
- <span data-ttu-id="4d3ce-3592">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3592">Bank Account #</span></span> 
- <span data-ttu-id="4d3ce-3593">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3593">Bank Acct Number</span></span> 
- <span data-ttu-id="4d3ce-3594">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3594">Bank Acct #</span></span> 
- <span data-ttu-id="4d3ce-3595">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3595">Bank Acct No.</span></span> 
- <span data-ttu-id="4d3ce-3596">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3596">Bank Account No.</span></span> 
- <span data-ttu-id="4d3ce-3597">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3597">Savings Account Number</span></span> 
- <span data-ttu-id="4d3ce-3598">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3598">Savings Account.</span></span> 
- <span data-ttu-id="4d3ce-3599">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3599">Savings Account #</span></span> 
- <span data-ttu-id="4d3ce-3600">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3600">Savings Acct Number</span></span> 
- <span data-ttu-id="4d3ce-3601">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3601">Savings Acct #</span></span> 
- <span data-ttu-id="4d3ce-3602">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3602">Savings Acct No.</span></span> 
- <span data-ttu-id="4d3ce-3603">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3603">Savings Account No.</span></span> 
- <span data-ttu-id="4d3ce-3604">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3604">Debit Account Number</span></span> 
- <span data-ttu-id="4d3ce-3605">Debit Account</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3605">Debit Account</span></span> 
- <span data-ttu-id="4d3ce-3606">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3606">Debit Account #</span></span> 
- <span data-ttu-id="4d3ce-3607">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3607">Debit Acct Number</span></span> 
- <span data-ttu-id="4d3ce-3608">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3608">Debit Acct #</span></span> 
- <span data-ttu-id="4d3ce-3609">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3609">Debit Acct No.</span></span> 
- <span data-ttu-id="4d3ce-3610">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3610">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="4d3ce-3611">Número de carteira de motorista dos EUA</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3611">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-3612">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3612">Format</span></span>

<span data-ttu-id="4d3ce-3613">Depende do estado</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3613">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-3614">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3614">Pattern</span></span>

<span data-ttu-id="4d3ce-3615">Depende do estado – por exemplo, Nova York:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3615">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="4d3ce-3616">Nove dígitos formatados como DDD DDD DDD corresponderão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3616">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="4d3ce-3617">Nove dígitos como ddddddddd não serão correspondentes.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3617">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-3618">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3618">Checksum</span></span>

<span data-ttu-id="4d3ce-3619">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3619">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-3620">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3620">Definition</span></span>

<span data-ttu-id="4d3ce-3621">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3621">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3622">A função Func_new_york_drivers_license_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3622">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3623">Uma palavra-chave de Keyword_[state_name]_drivers_license_name for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3623">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="4d3ce-3624">Uma palavra-chave de Keyword_us_drivers_license for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3624">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="4d3ce-3625">Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3626">A função Func_new_york_drivers_license_number localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3626">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3627">Uma palavra-chave de Keyword_[state_name]_drivers_license_name for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3627">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="4d3ce-3628">Uma palavra-chave de Keyword_us_drivers_license_abbreviations for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3628">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="4d3ce-3629">Nenhuma palavra-chave de Keyword_us_drivers_license for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3629">No keyword from Keyword_us_drivers_license is found.</span></span>

```xml
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
```

### <a name="keywords"></a><span data-ttu-id="4d3ce-3630">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3630">Keywords</span></span>

#### <a name="keyword_us_drivers_license_abbreviations"></a><span data-ttu-id="4d3ce-3631">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3631">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="4d3ce-3632">DISTRIBUIÇÃO</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3632">DL</span></span> 
- <span data-ttu-id="4d3ce-3633">DL</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3633">DLS</span></span> 
- <span data-ttu-id="4d3ce-3634">CDL</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3634">CDL</span></span> 
- <span data-ttu-id="4d3ce-3635">CDLS</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3635">CDLS</span></span> 
- <span data-ttu-id="4d3ce-3636">ID</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3636">ID</span></span> 
- <span data-ttu-id="4d3ce-3637">Código</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3637">IDs</span></span> 
- <span data-ttu-id="4d3ce-3638">DISTRIBUIÇÃO #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3638">DL#</span></span> 
- <span data-ttu-id="4d3ce-3639">DL #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3639">DLS#</span></span> 
- <span data-ttu-id="4d3ce-3640">CDL #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3640">CDL#</span></span> 
- <span data-ttu-id="4d3ce-3641">CDLS #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3641">CDLS#</span></span> 
- <span data-ttu-id="4d3ce-3642">ID #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3642">ID#</span></span>
- <span data-ttu-id="4d3ce-3643">Código #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3643">IDs#</span></span> 
- <span data-ttu-id="4d3ce-3644">ID number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3644">ID number</span></span> 
- <span data-ttu-id="4d3ce-3645">ID numbers</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3645">ID numbers</span></span> 
- <span data-ttu-id="4d3ce-3646">DRIVER'LIC</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3646">LIC</span></span> 
- <span data-ttu-id="4d3ce-3647">DRIVER'LIC #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3647">LIC#</span></span> 

#### <a name="keyword_us_drivers_license"></a><span data-ttu-id="4d3ce-3648">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3648">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="4d3ce-3649">DriverLic</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3649">DriverLic</span></span> 
- <span data-ttu-id="4d3ce-3650">DriverLics</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3650">DriverLics</span></span> 
- <span data-ttu-id="4d3ce-3651">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3651">DriverLicense</span></span> 
- <span data-ttu-id="4d3ce-3652">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3652">DriverLicenses</span></span> 
- <span data-ttu-id="4d3ce-3653">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3653">Driver Lic</span></span> 
- <span data-ttu-id="4d3ce-3654">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3654">Driver Lics</span></span> 
- <span data-ttu-id="4d3ce-3655">Driver License</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3655">Driver License</span></span> 
- <span data-ttu-id="4d3ce-3656">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3656">Driver Licenses</span></span> 
- <span data-ttu-id="4d3ce-3657">DriversLic</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3657">DriversLic</span></span> 
- <span data-ttu-id="4d3ce-3658">DriversLics</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3658">DriversLics</span></span> 
- <span data-ttu-id="4d3ce-3659">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3659">DriversLicense</span></span> 
- <span data-ttu-id="4d3ce-3660">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3660">DriversLicenses</span></span> 
- <span data-ttu-id="4d3ce-3661">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3661">Drivers Lic</span></span> 
- <span data-ttu-id="4d3ce-3662">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3662">Drivers Lics</span></span> 
- <span data-ttu-id="4d3ce-3663">Drivers License</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3663">Drivers License</span></span> 
- <span data-ttu-id="4d3ce-3664">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3664">Drivers Licenses</span></span> 
- <span data-ttu-id="4d3ce-3665">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3665">Driver'Lic</span></span> 
- <span data-ttu-id="4d3ce-3666">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3666">Driver'Lics</span></span> 
- <span data-ttu-id="4d3ce-3667">Driver'License</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3667">Driver'License</span></span> 
- <span data-ttu-id="4d3ce-3668">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3668">Driver'Licenses</span></span> 
- <span data-ttu-id="4d3ce-3669">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3669">Driver' Lic</span></span> 
- <span data-ttu-id="4d3ce-3670">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3670">Driver' Lics</span></span> 
- <span data-ttu-id="4d3ce-3671">Driver' License</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3671">Driver' License</span></span> 
- <span data-ttu-id="4d3ce-3672">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3672">Driver' Licenses</span></span>
- <span data-ttu-id="4d3ce-3673">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3673">Driver'sLic</span></span> 
- <span data-ttu-id="4d3ce-3674">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3674">Driver'sLics</span></span> 
- <span data-ttu-id="4d3ce-3675">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3675">Driver'sLicense</span></span> 
- <span data-ttu-id="4d3ce-3676">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3676">Driver'sLicenses</span></span> 
- <span data-ttu-id="4d3ce-3677">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3677">Driver's Lic</span></span> 
- <span data-ttu-id="4d3ce-3678">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3678">Driver's Lics</span></span> 
- <span data-ttu-id="4d3ce-3679">Driver's License</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3679">Driver's License</span></span> 
- <span data-ttu-id="4d3ce-3680">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3680">Driver's Licenses</span></span> 
- <span data-ttu-id="4d3ce-3681">identification number</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3681">identification number</span></span> 
- <span data-ttu-id="4d3ce-3682">identification numbers</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3682">identification numbers</span></span> 
- <span data-ttu-id="4d3ce-3683">identification #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3683">identification #</span></span> 
- <span data-ttu-id="4d3ce-3684">id card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3684">id card</span></span> 
- <span data-ttu-id="4d3ce-3685">id cards</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3685">id cards</span></span> 
- <span data-ttu-id="4d3ce-3686">identification card</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3686">identification card</span></span> 
- <span data-ttu-id="4d3ce-3687">identification cards</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3687">identification cards</span></span> 
- <span data-ttu-id="4d3ce-3688">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3688">DriverLic#</span></span> 
- <span data-ttu-id="4d3ce-3689">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3689">DriverLics#</span></span> 
- <span data-ttu-id="4d3ce-3690">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3690">DriverLicense#</span></span> 
- <span data-ttu-id="4d3ce-3691">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3691">DriverLicenses#</span></span> 
- <span data-ttu-id="4d3ce-3692">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3692">Driver Lic#</span></span> 
- <span data-ttu-id="4d3ce-3693">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3693">Driver Lics#</span></span> 
- <span data-ttu-id="4d3ce-3694">Driver License#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3694">Driver License#</span></span> 
- <span data-ttu-id="4d3ce-3695">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3695">Driver Licenses#</span></span> 
- <span data-ttu-id="4d3ce-3696">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3696">DriversLic#</span></span> 
- <span data-ttu-id="4d3ce-3697">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3697">DriversLics#</span></span> 
- <span data-ttu-id="4d3ce-3698">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3698">DriversLicense#</span></span> 
- <span data-ttu-id="4d3ce-3699">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3699">DriversLicenses#</span></span> 
- <span data-ttu-id="4d3ce-3700">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3700">Drivers Lic#</span></span> 
- <span data-ttu-id="4d3ce-3701">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3701">Drivers Lics#</span></span> 
- <span data-ttu-id="4d3ce-3702">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3702">Drivers License#</span></span> 
- <span data-ttu-id="4d3ce-3703">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3703">Drivers Licenses#</span></span> 
- <span data-ttu-id="4d3ce-3704">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3704">Driver'Lic#</span></span> 
- <span data-ttu-id="4d3ce-3705">Driver'Lics #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3705">Driver'Lics#</span></span> 
- <span data-ttu-id="4d3ce-3706">Driver'License #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3706">Driver'License#</span></span> 
- <span data-ttu-id="4d3ce-3707">Driver'Licenses #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3707">Driver'Licenses#</span></span> 
- <span data-ttu-id="4d3ce-3708">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3708">Driver' Lic#</span></span> 
- <span data-ttu-id="4d3ce-3709">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3709">Driver' Lics#</span></span> 
- <span data-ttu-id="4d3ce-3710">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3710">Driver' License#</span></span> 
- <span data-ttu-id="4d3ce-3711">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3711">Driver' Licenses#</span></span> 
- <span data-ttu-id="4d3ce-3712">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3712">Driver'sLic#</span></span> 
- <span data-ttu-id="4d3ce-3713">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3713">Driver'sLics#</span></span> 
- <span data-ttu-id="4d3ce-3714">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3714">Driver'sLicense#</span></span> 
- <span data-ttu-id="4d3ce-3715">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3715">Driver'sLicenses#</span></span> 
- <span data-ttu-id="4d3ce-3716">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3716">Driver's Lic#</span></span> 
- <span data-ttu-id="4d3ce-3717">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3717">Driver's Lics#</span></span> 
- <span data-ttu-id="4d3ce-3718">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3718">Driver's License#</span></span> 
- <span data-ttu-id="4d3ce-3719">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3719">Driver's Licenses#</span></span> 
- <span data-ttu-id="4d3ce-3720">id card#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3720">id card#</span></span> 
- <span data-ttu-id="4d3ce-3721">id cards#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3721">id cards#</span></span> 
- <span data-ttu-id="4d3ce-3722">identification card#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3722">identification card#</span></span> 
- <span data-ttu-id="4d3ce-3723">identification cards#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3723">identification cards#</span></span> 


#### <a name="keyword_state_name_drivers_license_name"></a><span data-ttu-id="4d3ce-3724">Keyword_ [state_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3724">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="4d3ce-3725">Abreviação do estado (por exemplo, "NY")</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3725">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="4d3ce-3726">Nome do estado (por exemplo, "Nova York")</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3726">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="4d3ce-3727">Número de identificação de contribuinte individual (ITIN) dos EUA</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3727">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-3728">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3728">Format</span></span>

<span data-ttu-id="4d3ce-3729">Nove dígitos que começam com "9" e contêm um "7" ou "8" como o quarto dígito, opcionalmente formatado com espaços ou traços</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3729">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-3730">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3730">Pattern</span></span>

<span data-ttu-id="4d3ce-3731">Binário</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3731">Formatted:</span></span>
- <span data-ttu-id="4d3ce-3732">O dígito "9"</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3732">The digit "9"</span></span> 
- <span data-ttu-id="4d3ce-3733">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3733">Two digits</span></span> 
- <span data-ttu-id="4d3ce-3734">Um espaço ou um traço</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3734">A space or dash</span></span> 
- <span data-ttu-id="4d3ce-3735">Um "7" ou "8"</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3735">A "7" or "8"</span></span> 
- <span data-ttu-id="4d3ce-3736">Um dígito</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3736">A digit</span></span> 
- <span data-ttu-id="4d3ce-3737">Um espaço ou um traço</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3737">A space, or dash</span></span> 
- <span data-ttu-id="4d3ce-3738">Quatro dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3738">Four digits</span></span>

<span data-ttu-id="4d3ce-3739">Não formatado</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3739">Unformatted:</span></span>
- <span data-ttu-id="4d3ce-3740">O dígito "9"</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3740">The digit "9"</span></span> 
- <span data-ttu-id="4d3ce-3741">Dois dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3741">Two digits</span></span> 
- <span data-ttu-id="4d3ce-3742">Um "7" ou "8"</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3742">A "7" or "8"</span></span> 
- <span data-ttu-id="4d3ce-3743">Cinco dígitos</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3743">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-3744">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3744">Checksum</span></span>

<span data-ttu-id="4d3ce-3745">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3745">No</span></span>

### <a name="definition"></a><span data-ttu-id="4d3ce-3746">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3746">Definition</span></span>

<span data-ttu-id="4d3ce-3747">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3747">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3748">A função Func_formatted_itin localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3748">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3749">Pelo menos uma das seguintes opções for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3749">At least one of the following is true:</span></span>
    - <span data-ttu-id="4d3ce-3750">Uma palavra-chave de Keyword_itin for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3750">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="4d3ce-3751">A função Func_us_address encontrar um endereço no formato de data à direita.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3751">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="4d3ce-3752">A função Func_us_date encontra uma data no formato de data à direita.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3752">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="4d3ce-3753">Uma palavra-chave de Keyword_itin_collaborative for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3753">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="4d3ce-3754">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3754">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3755">A função Func_unformatted_itin localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3755">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3756">Pelo menos uma das seguintes opções for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3756">At least one of the following is true:</span></span>
    - <span data-ttu-id="4d3ce-3757">Uma palavra-chave de Keyword_itin_collaborative for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3757">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="4d3ce-3758">A função Func_us_address encontrar um endereço no formato de data à direita.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3758">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="4d3ce-3759">A função Func_us_date encontra uma data no formato de data à direita.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3759">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="4d3ce-3760">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3760">Keywords</span></span>

#### <a name="keyword_itin"></a><span data-ttu-id="4d3ce-3761">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3761">Keyword_itin</span></span>

- <span data-ttu-id="4d3ce-3762">contribui</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3762">taxpayer</span></span> 
- <span data-ttu-id="4d3ce-3763">tax id</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3763">tax id</span></span> 
- <span data-ttu-id="4d3ce-3764">tax identification</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3764">tax identification</span></span> 
- <span data-ttu-id="4d3ce-3765">itin</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3765">itin</span></span> 
- <span data-ttu-id="4d3ce-3766">es</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3766">ssn</span></span> 
- <span data-ttu-id="4d3ce-3767">Tin</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3767">tin</span></span> 
- <span data-ttu-id="4d3ce-3768">social security</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3768">social security</span></span> 
- <span data-ttu-id="4d3ce-3769">tax payer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3769">tax payer</span></span> 
- <span data-ttu-id="4d3ce-3770">itins</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3770">itins</span></span> 
- <span data-ttu-id="4d3ce-3771">táxi</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3771">taxid</span></span> 
- <span data-ttu-id="4d3ce-3772">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3772">individual taxpayer</span></span> 

#### <a name="keyword_itin_collaborative"></a><span data-ttu-id="4d3ce-3773">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3773">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="4d3ce-3774">Licença</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3774">License</span></span> 
- <span data-ttu-id="4d3ce-3775">DISTRIBUIÇÃO</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3775">DL</span></span> 
- <span data-ttu-id="4d3ce-3776">DOB</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3776">DOB</span></span> 
- <span data-ttu-id="4d3ce-3777">Data de Nascimento</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3777">Birthdate</span></span> 
- <span data-ttu-id="4d3ce-3778">Aniversário</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3778">Birthday</span></span> 
- <span data-ttu-id="4d3ce-3779">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3779">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="4d3ce-3780">Número de seguridade social dos EUA (SSN)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3780">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="4d3ce-3781">Formatar</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3781">Format</span></span>

<span data-ttu-id="4d3ce-3782">9 dígitos que podem estar em um padrão formatado ou não formatado</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3782">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="4d3ce-3783">Se emitido antes de meados de 2011, um SSN tem uma formatação forte, onde determinadas partes do número devem estar dentro de determinados intervalos para serem válidos (mas não há nenhum checksum).</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3783">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="4d3ce-3784">Padrão</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3784">Pattern</span></span>

<span data-ttu-id="4d3ce-3785">Quatro funções procuram CPFs em quatro padrões diferentes:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3785">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="4d3ce-3786">Func_ssn localiza CPFs com formatação forte de 2011 formatada com traços ou espaços (DDD-DD-dddd ou DDD DD dddd)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3786">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="4d3ce-3787">Func_unformatted_ssn localiza CPFs com uma formatação forte anterior à 2011 que não são formatadas como nove dígitos consecutivos (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3787">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="4d3ce-3788">Func_randomized_formatted_ssn localiza CPFs post-2011 que são formatados com traços ou espaços (DDD-DD-dddd ou DDD DD dddd)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3788">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="4d3ce-3789">Func_randomized_unformatted_ssn localiza CPFs post-2011 que não estão formatados como nove dígitos consecutivos (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3789">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="4d3ce-3790">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3790">Checksum</span></span>

<span data-ttu-id="4d3ce-3791">Não</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3791">No</span></span>


### <a name="definition"></a><span data-ttu-id="4d3ce-3792">Definição</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3792">Definition</span></span>

<span data-ttu-id="4d3ce-3793">Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3794">A função Func_ssn localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3794">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3795">Uma palavra-chave de Keyword_ssn for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3795">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="4d3ce-3796">Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3796">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3797">A função Func_unformatted_ssn localiza o conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3797">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3798">Uma palavra-chave de Keyword_ssn for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3798">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="4d3ce-3799">Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3799">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3800">A função Func_randomized_formatted_ssn localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3800">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3801">Uma palavra-chave de Keyword_ssn for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3801">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="4d3ce-3802">Uma política de DLP tem 55% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3802">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4d3ce-3803">A função Func_randomized_unformatted_ssn localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3803">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="4d3ce-3804">Uma palavra-chave de Keyword_ssn for encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3804">A keyword from Keyword_ssn is found.</span></span>


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

### <a name="keywords"></a><span data-ttu-id="4d3ce-3805">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3805">Keywords</span></span>

#### <a name="keyword_ssn"></a><span data-ttu-id="4d3ce-3806">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3806">Keyword_ssn</span></span>

- <span data-ttu-id="4d3ce-3807">Social Security</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3807">Social Security</span></span> 
- <span data-ttu-id="4d3ce-3808">Social Security#</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3808">Social Security#</span></span> 
- <span data-ttu-id="4d3ce-3809">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3809">Soc Sec</span></span> 
- <span data-ttu-id="4d3ce-3810">ES</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3810">SSN</span></span> 
- <span data-ttu-id="4d3ce-3811">CPFs</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3811">SSNS</span></span> 
- <span data-ttu-id="4d3ce-3812">ES #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3812">SSN#</span></span> 
- <span data-ttu-id="4d3ce-3813">PLANILHA #</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3813">SS#</span></span> 
- <span data-ttu-id="4d3ce-3814">SSID</span><span class="sxs-lookup"><span data-stu-id="4d3ce-3814">SSID</span></span> 
   
