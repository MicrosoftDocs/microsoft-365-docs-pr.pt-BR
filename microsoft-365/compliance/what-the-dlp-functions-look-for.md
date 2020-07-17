---
title: O que as funções DLP procuram
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/18/2016
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Saiba o que as funções de prevenção de perda de dados (DLP) procuram para ajudá-lo a entender como os tipos de informações confidenciais predefinidos funcionam.
ms.openlocfilehash: 838277b2e30696cd00cfc30df49c1d5a29149d92
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819271"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="e8a02-103">O que as funções DLP procuram</span><span class="sxs-lookup"><span data-stu-id="e8a02-103">What the DLP functions look for</span></span>

<span data-ttu-id="e8a02-p101">A política DLP inclui tipos de informação confidencial, como números de cartão de crédito e de cartão de débito da UE (União Europeia), que estão prontos para uso em suas políticas DLP. Esses tipos de informação confidencial procuram por um padrão específico e o confirmam, garantindo a formatação adequada, impondo as somas de verificação e procurando palavras-chave relevantes ou outras informações. Algumas dessas funcionalidades são realizadas por funções internas. Por exemplo, o tipo de informação confidencial de Número de Cartão de Crédito usa uma função para procurar datas formatadas como uma data de expiração, para ajudar a corroborar que um número é um número de cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="e8a02-p101">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies. These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information. Some of this functionality is performed by internal functions. For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="e8a02-108">Este tópico explica o que essas funções procuram, para ajudar você a entender como funcionam os tipos de informações confidenciais predefinidas.</span><span class="sxs-lookup"><span data-stu-id="e8a02-108">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="e8a02-109">Para mais informações, consulte [definições de entidade de tipo de informação confidencial](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="e8a02-109">For more information, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)</span></span>
  
## <a name="func_us_date"></a><span data-ttu-id="e8a02-110">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="e8a02-110">Func_us_date</span></span>

<span data-ttu-id="e8a02-111">Essa função procura uma data no formato comumente usado nos EUA. Isso inclui os formatos "mês/dia/ano", "mês-dia-ano" e "ano dia do mês".</span><span class="sxs-lookup"><span data-stu-id="e8a02-111">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="e8a02-112">Os nomes ou as abreviações de meses não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e8a02-112">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="e8a02-113">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="e8a02-113">Examples:</span></span>
  
- <span data-ttu-id="e8a02-114">2 de dezembro de 2016</span><span class="sxs-lookup"><span data-stu-id="e8a02-114">December 2, 2016</span></span>
    
- <span data-ttu-id="e8a02-115">2 de dezembro de 2016</span><span class="sxs-lookup"><span data-stu-id="e8a02-115">Dec 2, 2016</span></span>
    
- <span data-ttu-id="e8a02-116">Dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="e8a02-116">dec 02 2016</span></span>
    
- <span data-ttu-id="e8a02-117">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="e8a02-117">12/2/2016</span></span>
    
- <span data-ttu-id="e8a02-118">12/02/16</span><span class="sxs-lookup"><span data-stu-id="e8a02-118">12/02/16</span></span>
    
- <span data-ttu-id="e8a02-119">Dec-2-2016</span><span class="sxs-lookup"><span data-stu-id="e8a02-119">Dec-2-2016</span></span>
    
- <span data-ttu-id="e8a02-120">12-2-16</span><span class="sxs-lookup"><span data-stu-id="e8a02-120">12-2-16</span></span>
    
<span data-ttu-id="e8a02-121">Nomes de meses aceitos:</span><span class="sxs-lookup"><span data-stu-id="e8a02-121">Accepted month names:</span></span>
  
- <span data-ttu-id="e8a02-122">English</span><span class="sxs-lookup"><span data-stu-id="e8a02-122">English</span></span>
    
  - <span data-ttu-id="e8a02-123">Janeiro, fevereiro, março, abril, maio, junho de julho, agosto, setembro, outubro, novembro de dezembro</span><span class="sxs-lookup"><span data-stu-id="e8a02-123">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="e8a02-124">Jan. Fev. mar. abr. Maio de 1º de julho de agosto de setembro. Dec.</span><span class="sxs-lookup"><span data-stu-id="e8a02-124">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="func_eu_date"></a><span data-ttu-id="e8a02-125">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="e8a02-125">Func_eu_date</span></span>

<span data-ttu-id="e8a02-p104">Essa função procura uma data no formato comumente usado na UE (e na maioria dos lugares fora dos Estados Unidos). Isso inclui os formatos de "dia/mês/ano", "dia-mês-ano" e "dia mês ano". Os nomes ou as abreviações de meses não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e8a02-p104">This function looks for a date in the format commonly used in the E.U. (and most places outside the U.S.). This includes the formats "day/month/year", "day-month-year", and "day month year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="e8a02-130">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="e8a02-130">Examples:</span></span>
  
- <span data-ttu-id="e8a02-131">2 Dec 2016</span><span class="sxs-lookup"><span data-stu-id="e8a02-131">2 Dec 2016</span></span>
    
- <span data-ttu-id="e8a02-132">02 de dezembro de 2016</span><span class="sxs-lookup"><span data-stu-id="e8a02-132">02 dec 2016</span></span>
    
- <span data-ttu-id="e8a02-133">2 de dezembro de 16</span><span class="sxs-lookup"><span data-stu-id="e8a02-133">2 Dec 16</span></span>
    
- <span data-ttu-id="e8a02-134">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="e8a02-134">2/12/2016</span></span>
    
- <span data-ttu-id="e8a02-135">02/12/16</span><span class="sxs-lookup"><span data-stu-id="e8a02-135">02/12/16</span></span>
    
- <span data-ttu-id="e8a02-136">2-dez-2016</span><span class="sxs-lookup"><span data-stu-id="e8a02-136">2-Dec-2016</span></span>
    
- <span data-ttu-id="e8a02-137">2-12-16</span><span class="sxs-lookup"><span data-stu-id="e8a02-137">2-12-16</span></span>
    
<span data-ttu-id="e8a02-138">Nomes de meses aceitos:</span><span class="sxs-lookup"><span data-stu-id="e8a02-138">Accepted month names:</span></span>
  
- <span data-ttu-id="e8a02-139">English</span><span class="sxs-lookup"><span data-stu-id="e8a02-139">English</span></span>
    
  - <span data-ttu-id="e8a02-140">Janeiro, fevereiro, março, abril, maio, junho de julho, agosto, setembro, outubro, novembro de dezembro</span><span class="sxs-lookup"><span data-stu-id="e8a02-140">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="e8a02-141">Jan. Fev. mar. abr. Maio de 1º de julho de agosto de setembro. Dec.</span><span class="sxs-lookup"><span data-stu-id="e8a02-141">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="e8a02-142">Dutch</span><span class="sxs-lookup"><span data-stu-id="e8a02-142">Dutch</span></span>
    
  - <span data-ttu-id="e8a02-143">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="e8a02-143">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="e8a02-144">Jan fevereiro de maart de abril de Mei jun jul setembro de agosto de dezembro de Okt de Nov</span><span class="sxs-lookup"><span data-stu-id="e8a02-144">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="e8a02-145">French</span><span class="sxs-lookup"><span data-stu-id="e8a02-145">French</span></span>
    
  - <span data-ttu-id="e8a02-146">Janvier, Février, Mars, Avril, Mai, Juin Juillet, Août, Septembre, outubro, Novembre, décembre</span><span class="sxs-lookup"><span data-stu-id="e8a02-146">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="e8a02-147">janv.</span><span class="sxs-lookup"><span data-stu-id="e8a02-147">janv.</span></span> <span data-ttu-id="e8a02-148">févr.</span><span class="sxs-lookup"><span data-stu-id="e8a02-148">févr.</span></span> <span data-ttu-id="e8a02-149">Mars Avril Mai Juin Juil.</span><span class="sxs-lookup"><span data-stu-id="e8a02-149">mars avril mai juin juil.</span></span> <span data-ttu-id="e8a02-150">Août set.</span><span class="sxs-lookup"><span data-stu-id="e8a02-150">août sept.</span></span> <span data-ttu-id="e8a02-151">Outubro.</span><span class="sxs-lookup"><span data-stu-id="e8a02-151">oct.</span></span> <span data-ttu-id="e8a02-152">Nov.</span><span class="sxs-lookup"><span data-stu-id="e8a02-152">nov.</span></span> <span data-ttu-id="e8a02-153">déc.</span><span class="sxs-lookup"><span data-stu-id="e8a02-153">déc.</span></span>
    
- <span data-ttu-id="e8a02-154">German</span><span class="sxs-lookup"><span data-stu-id="e8a02-154">German</span></span>
    
  - <span data-ttu-id="e8a02-155">jänuar, februar, März, abril, Mai, Juni Juli, agosto, setembro, Oktober, novembro de Dezember</span><span class="sxs-lookup"><span data-stu-id="e8a02-155">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="e8a02-156">Jan./Jän.</span><span class="sxs-lookup"><span data-stu-id="e8a02-156">Jan./Jän.</span></span> <span data-ttu-id="e8a02-157">Fev. März abr. Mai Juni Juli ago. set. Okt.</span><span class="sxs-lookup"><span data-stu-id="e8a02-157">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="e8a02-158">Nov. dez.</span><span class="sxs-lookup"><span data-stu-id="e8a02-158">Nov. Dez.</span></span>
    
- <span data-ttu-id="e8a02-159">Italian</span><span class="sxs-lookup"><span data-stu-id="e8a02-159">Italian</span></span>
    
  - <span data-ttu-id="e8a02-160">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="e8a02-160">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="e8a02-161">genn.</span><span class="sxs-lookup"><span data-stu-id="e8a02-161">genn.</span></span> <span data-ttu-id="e8a02-162">febbr.</span><span class="sxs-lookup"><span data-stu-id="e8a02-162">febbr.</span></span> <span data-ttu-id="e8a02-163">mar.</span><span class="sxs-lookup"><span data-stu-id="e8a02-163">mar.</span></span> <span data-ttu-id="e8a02-164">abr.</span><span class="sxs-lookup"><span data-stu-id="e8a02-164">apr.</span></span> <span data-ttu-id="e8a02-165">magg.</span><span class="sxs-lookup"><span data-stu-id="e8a02-165">magg.</span></span> <span data-ttu-id="e8a02-166">giugno Luglio AG.</span><span class="sxs-lookup"><span data-stu-id="e8a02-166">giugno luglio ag.</span></span> <span data-ttu-id="e8a02-167">definida.</span><span class="sxs-lookup"><span data-stu-id="e8a02-167">sett.</span></span> <span data-ttu-id="e8a02-168">ott.</span><span class="sxs-lookup"><span data-stu-id="e8a02-168">ott.</span></span> <span data-ttu-id="e8a02-169">Nov.</span><span class="sxs-lookup"><span data-stu-id="e8a02-169">nov.</span></span> <span data-ttu-id="e8a02-170">DIC.</span><span class="sxs-lookup"><span data-stu-id="e8a02-170">dic.</span></span>
    
- <span data-ttu-id="e8a02-171">Português</span><span class="sxs-lookup"><span data-stu-id="e8a02-171">Portuguese</span></span>
    
  - <span data-ttu-id="e8a02-172">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="e8a02-172">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="e8a02-173">Jan fev mar abr mai jun jul atrás Set out nov dez</span><span class="sxs-lookup"><span data-stu-id="e8a02-173">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="e8a02-174">Spanish</span><span class="sxs-lookup"><span data-stu-id="e8a02-174">Spanish</span></span>
    
  - <span data-ttu-id="e8a02-175">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="e8a02-175">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="e8a02-176">Enero Fev.</span><span class="sxs-lookup"><span data-stu-id="e8a02-176">enero feb.</span></span> <span data-ttu-id="e8a02-177">Marzo abr.</span><span class="sxs-lookup"><span data-stu-id="e8a02-177">marzo abr.</span></span> <span data-ttu-id="e8a02-178">Mayo Jun.</span><span class="sxs-lookup"><span data-stu-id="e8a02-178">mayo jun.</span></span> <span data-ttu-id="e8a02-179">Jul.</span><span class="sxs-lookup"><span data-stu-id="e8a02-179">jul.</span></span> <span data-ttu-id="e8a02-180">agosto set./set.</span><span class="sxs-lookup"><span data-stu-id="e8a02-180">agosto sept./set.</span></span> <span data-ttu-id="e8a02-181">Outubro.</span><span class="sxs-lookup"><span data-stu-id="e8a02-181">oct.</span></span> <span data-ttu-id="e8a02-182">Nov.</span><span class="sxs-lookup"><span data-stu-id="e8a02-182">nov.</span></span> <span data-ttu-id="e8a02-183">DIC.</span><span class="sxs-lookup"><span data-stu-id="e8a02-183">dic.</span></span>
    
## <a name="func_eu_date1-deprecated"></a><span data-ttu-id="e8a02-184">Func_eu_date1 (preterido)</span><span class="sxs-lookup"><span data-stu-id="e8a02-184">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="e8a02-185">Essa função foi preterida porque dá suporte apenas a nomes de meses em Português, que agora estão incluídos na `Func_eu_date` função acima.</span><span class="sxs-lookup"><span data-stu-id="e8a02-185">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="e8a02-186">Essa função procura uma data no formato comumente usado em português.</span><span class="sxs-lookup"><span data-stu-id="e8a02-186">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="e8a02-187">O formato dessa função é o mesmo que `Func_eu_date` , diferente somente no idioma usado.</span><span class="sxs-lookup"><span data-stu-id="e8a02-187">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="e8a02-188">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="e8a02-188">Examples:</span></span>
  
- <span data-ttu-id="e8a02-189">2 dez 2016</span><span class="sxs-lookup"><span data-stu-id="e8a02-189">2 Dez 2016</span></span>
    
- <span data-ttu-id="e8a02-190">02 dez 2016</span><span class="sxs-lookup"><span data-stu-id="e8a02-190">02 dez 2016</span></span>
    
- <span data-ttu-id="e8a02-191">2 dez 16</span><span class="sxs-lookup"><span data-stu-id="e8a02-191">2 Dez 16</span></span>
    
- <span data-ttu-id="e8a02-192">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="e8a02-192">2/12/2016</span></span>
    
- <span data-ttu-id="e8a02-193">02/12/16</span><span class="sxs-lookup"><span data-stu-id="e8a02-193">02/12/16</span></span>
    
- <span data-ttu-id="e8a02-194">2-dez-2016</span><span class="sxs-lookup"><span data-stu-id="e8a02-194">2-Dez-2016</span></span>
    
- <span data-ttu-id="e8a02-195">2-12-16</span><span class="sxs-lookup"><span data-stu-id="e8a02-195">2-12-16</span></span>
    
<span data-ttu-id="e8a02-196">Nomes de meses aceitos:</span><span class="sxs-lookup"><span data-stu-id="e8a02-196">Accepted month names:</span></span>
  
- <span data-ttu-id="e8a02-197">Português</span><span class="sxs-lookup"><span data-stu-id="e8a02-197">Portuguese</span></span>
    
  - <span data-ttu-id="e8a02-198">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="e8a02-198">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="e8a02-199">Jan fev mar abr mai jun jul atrás Set out nov dez</span><span class="sxs-lookup"><span data-stu-id="e8a02-199">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="func_eu_date2-deprecated"></a><span data-ttu-id="e8a02-200">Func_eu_date2 (preterido)</span><span class="sxs-lookup"><span data-stu-id="e8a02-200">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="e8a02-201">Essa função foi preterida porque dá suporte apenas a nomes de meses em Holandês, que agora estão incluídos na `Func_eu_date` função acima.</span><span class="sxs-lookup"><span data-stu-id="e8a02-201">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="e8a02-202">Essa função procura uma data no formato comumente usado em holandês.</span><span class="sxs-lookup"><span data-stu-id="e8a02-202">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="e8a02-203">O formato dessa função é o mesmo que `Func_eu_date` , diferente somente no idioma usado.</span><span class="sxs-lookup"><span data-stu-id="e8a02-203">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="e8a02-204">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="e8a02-204">Examples:</span></span>
  
- <span data-ttu-id="e8a02-205">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="e8a02-205">2 Mei 2016</span></span>
    
- <span data-ttu-id="e8a02-206">02 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="e8a02-206">02 mei 2016</span></span>
    
- <span data-ttu-id="e8a02-207">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="e8a02-207">2 Mei 16</span></span>
    
- <span data-ttu-id="e8a02-208">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="e8a02-208">2/12/2016</span></span>
    
- <span data-ttu-id="e8a02-209">02/12/16</span><span class="sxs-lookup"><span data-stu-id="e8a02-209">02/12/16</span></span>
    
- <span data-ttu-id="e8a02-210">2-Mei-2016</span><span class="sxs-lookup"><span data-stu-id="e8a02-210">2-Mei-2016</span></span>
    
- <span data-ttu-id="e8a02-211">2-12-16</span><span class="sxs-lookup"><span data-stu-id="e8a02-211">2-12-16</span></span>
    
<span data-ttu-id="e8a02-212">Nomes de meses aceitos:</span><span class="sxs-lookup"><span data-stu-id="e8a02-212">Accepted month names:</span></span>
  
- <span data-ttu-id="e8a02-213">Dutch</span><span class="sxs-lookup"><span data-stu-id="e8a02-213">Dutch</span></span>
    
  - <span data-ttu-id="e8a02-214">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="e8a02-214">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="e8a02-215">Jan fevereiro de maart de abril de Mei jun jul setembro de agosto de dezembro de Okt de Nov</span><span class="sxs-lookup"><span data-stu-id="e8a02-215">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="func_expiration_date"></a><span data-ttu-id="e8a02-216">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="e8a02-216">Func_expiration_date</span></span>

<span data-ttu-id="e8a02-217">Essa função procura uma data nos formatos usados por cartões de crédito e débito, que exclui os dias e usa os meses.</span><span class="sxs-lookup"><span data-stu-id="e8a02-217">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="e8a02-218">Essa função coincidirá datas no formato de "mês/ano", "Mês-Year", "[month Name] Year" e "[month abreviation] Year".</span><span class="sxs-lookup"><span data-stu-id="e8a02-218">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="e8a02-219">Os nomes ou as abreviações de meses não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e8a02-219">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="e8a02-220">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="e8a02-220">Examples:</span></span>
  
- <span data-ttu-id="e8a02-221">MM/AA -- por exemplo, 01/11 ou 1/11</span><span class="sxs-lookup"><span data-stu-id="e8a02-221">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="e8a02-222">MM/AAAA -- por exemplo, 01/2011 ou 1/2011</span><span class="sxs-lookup"><span data-stu-id="e8a02-222">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="e8a02-223">MM-AA -- por exemplo, 01-22 ou 1-11</span><span class="sxs-lookup"><span data-stu-id="e8a02-223">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="e8a02-224">MM-AAAA -- por exemplo, 01-2000 ou 1-2000</span><span class="sxs-lookup"><span data-stu-id="e8a02-224">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="e8a02-225">Os seguintes formatos dão suporte a AA ou AAAA:</span><span class="sxs-lookup"><span data-stu-id="e8a02-225">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="e8a02-226">Mês-AAAA – por exemplo, jan-2010 ou janeiro-2010 ou jan-10 ou janeiro-10</span><span class="sxs-lookup"><span data-stu-id="e8a02-226">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="e8a02-227">Mês AAAA – por exemplo, 'janeiro 2010' ou 'jan 2010' ou 'janeiro 10' ou 'jan 10'</span><span class="sxs-lookup"><span data-stu-id="e8a02-227">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="e8a02-228">MêsAAAA – por exemplo, 'janeiro2010' ou 'Jan2010' ou 'janeiro10' ou 'Jan10'</span><span class="sxs-lookup"><span data-stu-id="e8a02-228">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="e8a02-229">Month/aaaa--por exemplo, ' Janeiro/2010 ' ou ' Jan/2010 ' ou ' janeiro/10 ' ou ' Jan/10 '</span><span class="sxs-lookup"><span data-stu-id="e8a02-229">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="e8a02-230">Nomes de meses aceitos:</span><span class="sxs-lookup"><span data-stu-id="e8a02-230">Accepted month names:</span></span>
  
- <span data-ttu-id="e8a02-231">English</span><span class="sxs-lookup"><span data-stu-id="e8a02-231">English</span></span>
    
  - <span data-ttu-id="e8a02-232">Janeiro, fevereiro, março, abril, maio, junho de julho, agosto, setembro, outubro, novembro de dezembro</span><span class="sxs-lookup"><span data-stu-id="e8a02-232">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="e8a02-233">Jan fev mar de junho de julho de agosto de agosto de abril de dezembro</span><span class="sxs-lookup"><span data-stu-id="e8a02-233">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="func_us_address"></a><span data-ttu-id="e8a02-234">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="e8a02-234">Func_us_address</span></span>

<span data-ttu-id="e8a02-p112">Essa função procura por um nome ou sigla de estado dos EUA seguida de um CEP válido, como são usados em endereços postais. O CEP deve ser um dos CEPs corretos associados ao nome ou sigla do estado americano. O nome do estado americano e o CEP não podem ser separados por pontos ou letras.</span><span class="sxs-lookup"><span data-stu-id="e8a02-p112">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses. The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation. The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="e8a02-238">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="e8a02-238">Examples:</span></span>
  
- <span data-ttu-id="e8a02-239">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="e8a02-239">Washington 98052</span></span>
    
- <span data-ttu-id="e8a02-240">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="e8a02-240">Washington 98052-9998</span></span>
    
- <span data-ttu-id="e8a02-241">WA 98052</span><span class="sxs-lookup"><span data-stu-id="e8a02-241">WA 98052</span></span>
    
- <span data-ttu-id="e8a02-242">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="e8a02-242">WA 98052-9998</span></span>
    

