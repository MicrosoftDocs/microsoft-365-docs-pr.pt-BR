---
title: O que as funções DLP procuram
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
description: Os tipos de informações confidenciais procuram um padrão específico e o corroboratem, garantindo a formatação adequada, aplicando as somas de verificação e procurando palavras-chave relevantes ou outras informações. Algumas dessas funcionalidades são realizadas por funções internas. Este tópico explica o que essas funções procuram, para ajudar você a entender como funcionam os tipos de informações confidenciais predefinidas.
ms.openlocfilehash: c192a17c488e5a7252a3599204d2bdeda4d0637c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073240"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="71b91-105">O que as funções DLP procuram</span><span class="sxs-lookup"><span data-stu-id="71b91-105">What the DLP functions look for</span></span>

<span data-ttu-id="71b91-p102">A política DLP inclui tipos de informação confidencial, como números de cartão de crédito e de cartão de débito da UE (União Europeia), que estão prontos para uso em suas políticas DLP. Esses tipos de informação confidencial procuram por um padrão específico e o confirmam, garantindo a formatação adequada, impondo as somas de verificação e procurando palavras-chave relevantes ou outras informações. Algumas dessas funcionalidades são realizadas por funções internas. Por exemplo, o tipo de informação confidencial de Número de Cartão de Crédito usa uma função para procurar datas formatadas como uma data de expiração, para ajudar a corroborar que um número é um número de cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="71b91-p102">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies. These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information. Some of this functionality is performed by internal functions. For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="71b91-110">Este tópico explica o que essas funções procuram, para ajudar você a entender como funcionam os tipos de informações confidenciais predefinidas.</span><span class="sxs-lookup"><span data-stu-id="71b91-110">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="71b91-111">Para saber mais, consulte [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="71b91-111">For more information, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="func_us_date"></a><span data-ttu-id="71b91-112">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="71b91-112">Func_us_date</span></span>

<span data-ttu-id="71b91-113">Essa função procura uma data no formato comumente usado nos EUA. Isso inclui os formatos "mês/dia/ano", "mês-dia-ano" e "ano dia do mês".</span><span class="sxs-lookup"><span data-stu-id="71b91-113">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="71b91-114">Os nomes ou as abreviações de meses não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="71b91-114">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="71b91-115">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="71b91-115">Examples:</span></span>
  
- <span data-ttu-id="71b91-116">2 de dezembro de 2016</span><span class="sxs-lookup"><span data-stu-id="71b91-116">December 2, 2016</span></span>
    
- <span data-ttu-id="71b91-117">2 de dezembro de 2016</span><span class="sxs-lookup"><span data-stu-id="71b91-117">Dec 2, 2016</span></span>
    
- <span data-ttu-id="71b91-118">Dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="71b91-118">dec 02 2016</span></span>
    
- <span data-ttu-id="71b91-119">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="71b91-119">12/2/2016</span></span>
    
- <span data-ttu-id="71b91-120">12/02/16</span><span class="sxs-lookup"><span data-stu-id="71b91-120">12/02/16</span></span>
    
- <span data-ttu-id="71b91-121">Dec-2-2016</span><span class="sxs-lookup"><span data-stu-id="71b91-121">Dec-2-2016</span></span>
    
- <span data-ttu-id="71b91-122">12-2-16</span><span class="sxs-lookup"><span data-stu-id="71b91-122">12-2-16</span></span>
    
<span data-ttu-id="71b91-123">Nomes de meses aceitos:</span><span class="sxs-lookup"><span data-stu-id="71b91-123">Accepted month names:</span></span>
  
- <span data-ttu-id="71b91-124">Inglês</span><span class="sxs-lookup"><span data-stu-id="71b91-124">English</span></span>
    
  - <span data-ttu-id="71b91-125">Janeiro, fevereiro, março, abril, maio, junho de julho, agosto, setembro, outubro, novembro de dezembro</span><span class="sxs-lookup"><span data-stu-id="71b91-125">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="71b91-126">Jan. Fev. mar. abr. Maio de 1º de julho de agosto de setembro. Dec.</span><span class="sxs-lookup"><span data-stu-id="71b91-126">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="func_eu_date"></a><span data-ttu-id="71b91-127">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="71b91-127">Func_eu_date</span></span>

<span data-ttu-id="71b91-p105">Essa função procura uma data no formato comumente usado na UE (e na maioria dos lugares fora dos Estados Unidos). Isso inclui os formatos de "dia/mês/ano", "dia-mês-ano" e "dia mês ano". Os nomes ou as abreviações de meses não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="71b91-p105">This function looks for a date in the format commonly used in the E.U. (and most places outside the U.S.). This includes the formats "day/month/year", "day-month-year", and "day month year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="71b91-132">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="71b91-132">Examples:</span></span>
  
- <span data-ttu-id="71b91-133">2 Dec 2016</span><span class="sxs-lookup"><span data-stu-id="71b91-133">2 Dec 2016</span></span>
    
- <span data-ttu-id="71b91-134">02 de dezembro de 2016</span><span class="sxs-lookup"><span data-stu-id="71b91-134">02 dec 2016</span></span>
    
- <span data-ttu-id="71b91-135">2 de dezembro de 16</span><span class="sxs-lookup"><span data-stu-id="71b91-135">2 Dec 16</span></span>
    
- <span data-ttu-id="71b91-136">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="71b91-136">2/12/2016</span></span>
    
- <span data-ttu-id="71b91-137">02/12/16</span><span class="sxs-lookup"><span data-stu-id="71b91-137">02/12/16</span></span>
    
- <span data-ttu-id="71b91-138">2-dez-2016</span><span class="sxs-lookup"><span data-stu-id="71b91-138">2-Dec-2016</span></span>
    
- <span data-ttu-id="71b91-139">2-12-16</span><span class="sxs-lookup"><span data-stu-id="71b91-139">2-12-16</span></span>
    
<span data-ttu-id="71b91-140">Nomes de meses aceitos:</span><span class="sxs-lookup"><span data-stu-id="71b91-140">Accepted month names:</span></span>
  
- <span data-ttu-id="71b91-141">Inglês</span><span class="sxs-lookup"><span data-stu-id="71b91-141">English</span></span>
    
  - <span data-ttu-id="71b91-142">Janeiro, fevereiro, março, abril, maio, junho de julho, agosto, setembro, outubro, novembro de dezembro</span><span class="sxs-lookup"><span data-stu-id="71b91-142">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="71b91-143">Jan. Fev. mar. abr. Maio de 1º de julho de agosto de setembro. Dec.</span><span class="sxs-lookup"><span data-stu-id="71b91-143">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="71b91-144">Holandês</span><span class="sxs-lookup"><span data-stu-id="71b91-144">Dutch</span></span>
    
  - <span data-ttu-id="71b91-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="71b91-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="71b91-146">Jan fevereiro de maart de abril de Mei jun jul setembro de agosto de dezembro de Okt de Nov</span><span class="sxs-lookup"><span data-stu-id="71b91-146">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="71b91-147">Francês</span><span class="sxs-lookup"><span data-stu-id="71b91-147">French</span></span>
    
  - <span data-ttu-id="71b91-148">Janvier, Février, Mars, Avril, Mai, Juin Juillet, Août, Septembre, outubro, Novembre, décembre</span><span class="sxs-lookup"><span data-stu-id="71b91-148">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="71b91-149">janv.</span><span class="sxs-lookup"><span data-stu-id="71b91-149">janv.</span></span> <span data-ttu-id="71b91-150">févr.</span><span class="sxs-lookup"><span data-stu-id="71b91-150">févr.</span></span> <span data-ttu-id="71b91-151">Mars Avril Mai Juin Juil.</span><span class="sxs-lookup"><span data-stu-id="71b91-151">mars avril mai juin juil.</span></span> <span data-ttu-id="71b91-152">Août set.</span><span class="sxs-lookup"><span data-stu-id="71b91-152">août sept.</span></span> <span data-ttu-id="71b91-153">Outubro.</span><span class="sxs-lookup"><span data-stu-id="71b91-153">oct.</span></span> <span data-ttu-id="71b91-154">Nov.</span><span class="sxs-lookup"><span data-stu-id="71b91-154">nov.</span></span> <span data-ttu-id="71b91-155">déc.</span><span class="sxs-lookup"><span data-stu-id="71b91-155">déc.</span></span>
    
- <span data-ttu-id="71b91-156">Alemão</span><span class="sxs-lookup"><span data-stu-id="71b91-156">German</span></span>
    
  - <span data-ttu-id="71b91-157">jänuar, februar, März, abril, Mai, Juni Juli, agosto, setembro, Oktober, novembro de Dezember</span><span class="sxs-lookup"><span data-stu-id="71b91-157">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="71b91-158">Jan./Jän.</span><span class="sxs-lookup"><span data-stu-id="71b91-158">Jan./Jän.</span></span> <span data-ttu-id="71b91-159">Fev. März abr. Mai Juni Juli ago. set. Okt.</span><span class="sxs-lookup"><span data-stu-id="71b91-159">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="71b91-160">Nov. dez.</span><span class="sxs-lookup"><span data-stu-id="71b91-160">Nov. Dez.</span></span>
    
- <span data-ttu-id="71b91-161">Italiano</span><span class="sxs-lookup"><span data-stu-id="71b91-161">Italian</span></span>
    
  - <span data-ttu-id="71b91-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="71b91-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="71b91-163">genn.</span><span class="sxs-lookup"><span data-stu-id="71b91-163">genn.</span></span> <span data-ttu-id="71b91-164">febbr.</span><span class="sxs-lookup"><span data-stu-id="71b91-164">febbr.</span></span> <span data-ttu-id="71b91-165">mar.</span><span class="sxs-lookup"><span data-stu-id="71b91-165">mar.</span></span> <span data-ttu-id="71b91-166">abr.</span><span class="sxs-lookup"><span data-stu-id="71b91-166">apr.</span></span> <span data-ttu-id="71b91-167">magg.</span><span class="sxs-lookup"><span data-stu-id="71b91-167">magg.</span></span> <span data-ttu-id="71b91-168">giugno Luglio AG.</span><span class="sxs-lookup"><span data-stu-id="71b91-168">giugno luglio ag.</span></span> <span data-ttu-id="71b91-169">definida.</span><span class="sxs-lookup"><span data-stu-id="71b91-169">sett.</span></span> <span data-ttu-id="71b91-170">ott.</span><span class="sxs-lookup"><span data-stu-id="71b91-170">ott.</span></span> <span data-ttu-id="71b91-171">Nov.</span><span class="sxs-lookup"><span data-stu-id="71b91-171">nov.</span></span> <span data-ttu-id="71b91-172">DIC.</span><span class="sxs-lookup"><span data-stu-id="71b91-172">dic.</span></span>
    
- <span data-ttu-id="71b91-173">Português</span><span class="sxs-lookup"><span data-stu-id="71b91-173">Portuguese</span></span>
    
  - <span data-ttu-id="71b91-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="71b91-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="71b91-175">Jan fev mar abr mai jun jul atrás Set out nov dez</span><span class="sxs-lookup"><span data-stu-id="71b91-175">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="71b91-176">Espanhol</span><span class="sxs-lookup"><span data-stu-id="71b91-176">Spanish</span></span>
    
  - <span data-ttu-id="71b91-177">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="71b91-177">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="71b91-178">Enero Fev.</span><span class="sxs-lookup"><span data-stu-id="71b91-178">enero feb.</span></span> <span data-ttu-id="71b91-179">Marzo abr.</span><span class="sxs-lookup"><span data-stu-id="71b91-179">marzo abr.</span></span> <span data-ttu-id="71b91-180">Mayo Jun.</span><span class="sxs-lookup"><span data-stu-id="71b91-180">mayo jun.</span></span> <span data-ttu-id="71b91-181">Jul.</span><span class="sxs-lookup"><span data-stu-id="71b91-181">jul.</span></span> <span data-ttu-id="71b91-182">agosto set./set.</span><span class="sxs-lookup"><span data-stu-id="71b91-182">agosto sept./set.</span></span> <span data-ttu-id="71b91-183">Outubro.</span><span class="sxs-lookup"><span data-stu-id="71b91-183">oct.</span></span> <span data-ttu-id="71b91-184">Nov.</span><span class="sxs-lookup"><span data-stu-id="71b91-184">nov.</span></span> <span data-ttu-id="71b91-185">DIC.</span><span class="sxs-lookup"><span data-stu-id="71b91-185">dic.</span></span>
    
## <a name="func_eu_date1-deprecated"></a><span data-ttu-id="71b91-186">Func_eu_date1 (preterido)</span><span class="sxs-lookup"><span data-stu-id="71b91-186">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="71b91-187">Essa função foi preterida porque dá suporte apenas a `Func_eu_date` nomes de meses em Português, que agora estão incluídos na função acima.</span><span class="sxs-lookup"><span data-stu-id="71b91-187">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="71b91-188">Essa função procura uma data no formato comumente usado em português.</span><span class="sxs-lookup"><span data-stu-id="71b91-188">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="71b91-189">O formato dessa função é o mesmo que `Func_eu_date`, diferente somente no idioma usado.</span><span class="sxs-lookup"><span data-stu-id="71b91-189">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="71b91-190">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="71b91-190">Examples:</span></span>
  
- <span data-ttu-id="71b91-191">2 dez 2016</span><span class="sxs-lookup"><span data-stu-id="71b91-191">2 Dez 2016</span></span>
    
- <span data-ttu-id="71b91-192">02 dez 2016</span><span class="sxs-lookup"><span data-stu-id="71b91-192">02 dez 2016</span></span>
    
- <span data-ttu-id="71b91-193">2 dez 16</span><span class="sxs-lookup"><span data-stu-id="71b91-193">2 Dez 16</span></span>
    
- <span data-ttu-id="71b91-194">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="71b91-194">2/12/2016</span></span>
    
- <span data-ttu-id="71b91-195">02/12/16</span><span class="sxs-lookup"><span data-stu-id="71b91-195">02/12/16</span></span>
    
- <span data-ttu-id="71b91-196">2-dez-2016</span><span class="sxs-lookup"><span data-stu-id="71b91-196">2-Dez-2016</span></span>
    
- <span data-ttu-id="71b91-197">2-12-16</span><span class="sxs-lookup"><span data-stu-id="71b91-197">2-12-16</span></span>
    
<span data-ttu-id="71b91-198">Nomes de meses aceitos:</span><span class="sxs-lookup"><span data-stu-id="71b91-198">Accepted month names:</span></span>
  
- <span data-ttu-id="71b91-199">Português</span><span class="sxs-lookup"><span data-stu-id="71b91-199">Portuguese</span></span>
    
  - <span data-ttu-id="71b91-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="71b91-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="71b91-201">Jan fev mar abr mai jun jul atrás Set out nov dez</span><span class="sxs-lookup"><span data-stu-id="71b91-201">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="func_eu_date2-deprecated"></a><span data-ttu-id="71b91-202">Func_eu_date2 (preterido)</span><span class="sxs-lookup"><span data-stu-id="71b91-202">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="71b91-203">Essa função foi preterida porque dá suporte apenas a `Func_eu_date` nomes de meses em Holandês, que agora estão incluídos na função acima.</span><span class="sxs-lookup"><span data-stu-id="71b91-203">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="71b91-204">Essa função procura uma data no formato comumente usado em holandês.</span><span class="sxs-lookup"><span data-stu-id="71b91-204">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="71b91-205">O formato dessa função é o mesmo que `Func_eu_date`, diferente somente no idioma usado.</span><span class="sxs-lookup"><span data-stu-id="71b91-205">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="71b91-206">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="71b91-206">Examples:</span></span>
  
- <span data-ttu-id="71b91-207">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="71b91-207">2 Mei 2016</span></span>
    
- <span data-ttu-id="71b91-208">02 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="71b91-208">02 mei 2016</span></span>
    
- <span data-ttu-id="71b91-209">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="71b91-209">2 Mei 16</span></span>
    
- <span data-ttu-id="71b91-210">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="71b91-210">2/12/2016</span></span>
    
- <span data-ttu-id="71b91-211">02/12/16</span><span class="sxs-lookup"><span data-stu-id="71b91-211">02/12/16</span></span>
    
- <span data-ttu-id="71b91-212">2-Mei-2016</span><span class="sxs-lookup"><span data-stu-id="71b91-212">2-Mei-2016</span></span>
    
- <span data-ttu-id="71b91-213">2-12-16</span><span class="sxs-lookup"><span data-stu-id="71b91-213">2-12-16</span></span>
    
<span data-ttu-id="71b91-214">Nomes de meses aceitos:</span><span class="sxs-lookup"><span data-stu-id="71b91-214">Accepted month names:</span></span>
  
- <span data-ttu-id="71b91-215">Holandês</span><span class="sxs-lookup"><span data-stu-id="71b91-215">Dutch</span></span>
    
  - <span data-ttu-id="71b91-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="71b91-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="71b91-217">Jan fevereiro de maart de abril de Mei jun jul setembro de agosto de dezembro de Okt de Nov</span><span class="sxs-lookup"><span data-stu-id="71b91-217">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="func_expiration_date"></a><span data-ttu-id="71b91-218">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="71b91-218">Func_expiration_date</span></span>

<span data-ttu-id="71b91-219">Essa função procura uma data nos formatos usados por cartões de crédito e débito, que exclui os dias e usa os meses.</span><span class="sxs-lookup"><span data-stu-id="71b91-219">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="71b91-220">Essa função coincidirá datas no formato de "mês/ano", "Mês-Year", "[month Name] Year" e "[month abreviation] Year".</span><span class="sxs-lookup"><span data-stu-id="71b91-220">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="71b91-221">Os nomes ou as abreviações de meses não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="71b91-221">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="71b91-222">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="71b91-222">Examples:</span></span>
  
- <span data-ttu-id="71b91-223">MM/AA -- por exemplo, 01/11 ou 1/11</span><span class="sxs-lookup"><span data-stu-id="71b91-223">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="71b91-224">MM/AAAA -- por exemplo, 01/2011 ou 1/2011</span><span class="sxs-lookup"><span data-stu-id="71b91-224">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="71b91-225">MM-AA -- por exemplo, 01-22 ou 1-11</span><span class="sxs-lookup"><span data-stu-id="71b91-225">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="71b91-226">MM-AAAA -- por exemplo, 01-2000 ou 1-2000</span><span class="sxs-lookup"><span data-stu-id="71b91-226">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="71b91-227">Os seguintes formatos dão suporte a AA ou AAAA:</span><span class="sxs-lookup"><span data-stu-id="71b91-227">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="71b91-228">Mês-AAAA – por exemplo, jan-2010 ou janeiro-2010 ou jan-10 ou janeiro-10</span><span class="sxs-lookup"><span data-stu-id="71b91-228">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="71b91-229">Mês AAAA – por exemplo, 'janeiro 2010' ou 'jan 2010' ou 'janeiro 10' ou 'jan 10'</span><span class="sxs-lookup"><span data-stu-id="71b91-229">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="71b91-230">MêsAAAA – por exemplo, 'janeiro2010' ou 'Jan2010' ou 'janeiro10' ou 'Jan10'</span><span class="sxs-lookup"><span data-stu-id="71b91-230">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="71b91-231">Month/aaaa--por exemplo, ' Janeiro/2010 ' ou ' Jan/2010 ' ou ' janeiro/10 ' ou ' Jan/10 '</span><span class="sxs-lookup"><span data-stu-id="71b91-231">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="71b91-232">Nomes de meses aceitos:</span><span class="sxs-lookup"><span data-stu-id="71b91-232">Accepted month names:</span></span>
  
- <span data-ttu-id="71b91-233">Inglês</span><span class="sxs-lookup"><span data-stu-id="71b91-233">English</span></span>
    
  - <span data-ttu-id="71b91-234">Janeiro, fevereiro, março, abril, maio, junho de julho, agosto, setembro, outubro, novembro de dezembro</span><span class="sxs-lookup"><span data-stu-id="71b91-234">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="71b91-235">Jan fev mar de junho de julho de agosto de agosto de abril de dezembro</span><span class="sxs-lookup"><span data-stu-id="71b91-235">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="func_us_address"></a><span data-ttu-id="71b91-236">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="71b91-236">Func_us_address</span></span>

<span data-ttu-id="71b91-p113">Essa função procura por um nome ou sigla de estado dos EUA seguida de um CEP válido, como são usados em endereços postais. O CEP deve ser um dos CEPs corretos associados ao nome ou sigla do estado americano. O nome do estado americano e o CEP não podem ser separados por pontos ou letras.</span><span class="sxs-lookup"><span data-stu-id="71b91-p113">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses. The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation. The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="71b91-240">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="71b91-240">Examples:</span></span>
  
- <span data-ttu-id="71b91-241">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="71b91-241">Washington 98052</span></span>
    
- <span data-ttu-id="71b91-242">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="71b91-242">Washington 98052-9998</span></span>
    
- <span data-ttu-id="71b91-243">WA 98052</span><span class="sxs-lookup"><span data-stu-id="71b91-243">WA 98052</span></span>
    
- <span data-ttu-id="71b91-244">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="71b91-244">WA 98052-9998</span></span>
    

