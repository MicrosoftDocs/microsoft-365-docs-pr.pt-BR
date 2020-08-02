---
title: O que as funções de prevenção de perda de dados (DLP) procuram
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
description: Saiba o que as funções de prevenção de perda de dados (DLP) procuram.
ms.openlocfilehash: ef87be7dde83b1e5ba12456e7801e0554bceb6ea
ms.sourcegitcommit: cfb0c50f1366736cdf031a75f0608246b5640d93
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/31/2020
ms.locfileid: "46536306"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="9ee5c-103">O que as funções DLP procuram</span><span class="sxs-lookup"><span data-stu-id="9ee5c-103">What the DLP functions look for</span></span>

<span data-ttu-id="9ee5c-104">A prevenção de perda de dados (DLP) inclui tipos de informações confidenciais, como número de cartão de crédito e número de cartão de débito da UE, que estão prontos para uso nas suas políticas de DLP.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-104">Data loss prevention (DLP) includes sensitive information types, such as credit card Number and EU Debit card number, which are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="9ee5c-105">Esses tipos de informação confidencial procuram por um padrão específico e o confirmam, garantindo a formatação adequada, impondo as somas de verificação e procurando palavras-chave relevantes ou outras informações.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-105">These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information.</span></span> <span data-ttu-id="9ee5c-106">Algumas dessas funcionalidades são realizadas por funções internas.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-106">Some of this functionality is performed by internal functions.</span></span> <span data-ttu-id="9ee5c-107">Por exemplo, o tipo de informação confidencial de Número de Cartão de Crédito usa uma função para procurar datas formatadas como uma data de expiração, para ajudar a corroborar que um número é um número de cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-107">For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="9ee5c-108">Este artigo explica o que essas funções procuram para ajudá-lo a entender como funcionam os tipos de informações confidenciais predefinidos.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-108">This article explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="9ee5c-109">Para mais informações, consulte [definições de entidade de tipo de informação confidencial](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="9ee5c-109">For more information, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)</span></span>
  
## <a name="func_us_date"></a><span data-ttu-id="9ee5c-110">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="9ee5c-110">Func_us_date</span></span>

<span data-ttu-id="9ee5c-111">Essa função procura uma data no formato comumente usado nos EUA. Isso inclui os formatos "mês/dia/ano", "mês-dia-ano" e "ano dia do mês".</span><span class="sxs-lookup"><span data-stu-id="9ee5c-111">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="9ee5c-112">Os nomes ou as abreviações de meses não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-112">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="9ee5c-113">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="9ee5c-113">Examples:</span></span>
  
- <span data-ttu-id="9ee5c-114">2 de dezembro de 2016</span><span class="sxs-lookup"><span data-stu-id="9ee5c-114">December 2, 2016</span></span>
    
- <span data-ttu-id="9ee5c-115">2 de dezembro de 2016</span><span class="sxs-lookup"><span data-stu-id="9ee5c-115">Dec 2, 2016</span></span>
    
- <span data-ttu-id="9ee5c-116">Dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="9ee5c-116">dec 02 2016</span></span>
    
- <span data-ttu-id="9ee5c-117">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="9ee5c-117">12/2/2016</span></span>
    
- <span data-ttu-id="9ee5c-118">12/02/16</span><span class="sxs-lookup"><span data-stu-id="9ee5c-118">12/02/16</span></span>
    
- <span data-ttu-id="9ee5c-119">Dec-2-2016</span><span class="sxs-lookup"><span data-stu-id="9ee5c-119">Dec-2-2016</span></span>
    
- <span data-ttu-id="9ee5c-120">12-2-16</span><span class="sxs-lookup"><span data-stu-id="9ee5c-120">12-2-16</span></span>
    
<span data-ttu-id="9ee5c-121">Nomes de meses aceitos:</span><span class="sxs-lookup"><span data-stu-id="9ee5c-121">Accepted month names:</span></span>
  
- <span data-ttu-id="9ee5c-122">English</span><span class="sxs-lookup"><span data-stu-id="9ee5c-122">English</span></span>
    
  - <span data-ttu-id="9ee5c-123">Janeiro, fevereiro, março, abril, maio, junho de julho, agosto, setembro, outubro, novembro de dezembro</span><span class="sxs-lookup"><span data-stu-id="9ee5c-123">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="9ee5c-124">Jan. Fev. mar. abr. Maio de 1º de julho de agosto de setembro. Dec.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-124">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="func_eu_date"></a><span data-ttu-id="9ee5c-125">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="9ee5c-125">Func_eu_date</span></span>

<span data-ttu-id="9ee5c-126">Essa função procura uma data no formato comumente usado na UE</span><span class="sxs-lookup"><span data-stu-id="9ee5c-126">This function looks for a date in the format commonly used in the E.U.</span></span> <span data-ttu-id="9ee5c-127">(e a maioria dos lugares fora dos EUA), como "dia/mês/ano", "dia-mês-ano" e "ano do mês do dia".</span><span class="sxs-lookup"><span data-stu-id="9ee5c-127">(and most places outside the U.S.), such as "day/month/year", "day-month-year", and "day month year".</span></span> <span data-ttu-id="9ee5c-128">Os nomes ou as abreviações de meses não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-128">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="9ee5c-129">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="9ee5c-129">Examples:</span></span>
  
- <span data-ttu-id="9ee5c-130">2 Dec 2016</span><span class="sxs-lookup"><span data-stu-id="9ee5c-130">2 Dec 2016</span></span>
    
- <span data-ttu-id="9ee5c-131">02 de dezembro de 2016</span><span class="sxs-lookup"><span data-stu-id="9ee5c-131">02 dec 2016</span></span>
    
- <span data-ttu-id="9ee5c-132">2 de dezembro de 16</span><span class="sxs-lookup"><span data-stu-id="9ee5c-132">2 Dec 16</span></span>
    
- <span data-ttu-id="9ee5c-133">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="9ee5c-133">2/12/2016</span></span>
    
- <span data-ttu-id="9ee5c-134">02/12/16</span><span class="sxs-lookup"><span data-stu-id="9ee5c-134">02/12/16</span></span>
    
- <span data-ttu-id="9ee5c-135">2-dez-2016</span><span class="sxs-lookup"><span data-stu-id="9ee5c-135">2-Dec-2016</span></span>
    
- <span data-ttu-id="9ee5c-136">2-12-16</span><span class="sxs-lookup"><span data-stu-id="9ee5c-136">2-12-16</span></span>
    
<span data-ttu-id="9ee5c-137">Nomes de meses aceitos:</span><span class="sxs-lookup"><span data-stu-id="9ee5c-137">Accepted month names:</span></span>
  
- <span data-ttu-id="9ee5c-138">English</span><span class="sxs-lookup"><span data-stu-id="9ee5c-138">English</span></span>
    
  - <span data-ttu-id="9ee5c-139">Janeiro, fevereiro, março, abril, maio, junho de julho, agosto, setembro, outubro, novembro de dezembro</span><span class="sxs-lookup"><span data-stu-id="9ee5c-139">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="9ee5c-140">Jan. Fev. mar. abr. Maio de 1º de julho de agosto de setembro. Dec.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-140">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="9ee5c-141">Dutch</span><span class="sxs-lookup"><span data-stu-id="9ee5c-141">Dutch</span></span>
    
  - <span data-ttu-id="9ee5c-142">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="9ee5c-142">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="9ee5c-143">Jan fevereiro de maart de abril de Mei jun jul setembro de agosto de dezembro de Okt de Nov</span><span class="sxs-lookup"><span data-stu-id="9ee5c-143">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="9ee5c-144">French</span><span class="sxs-lookup"><span data-stu-id="9ee5c-144">French</span></span>
    
  - <span data-ttu-id="9ee5c-145">Janvier, Février, Mars, Avril, Mai, Juin Juillet, Août, Septembre, outubro, Novembre, décembre</span><span class="sxs-lookup"><span data-stu-id="9ee5c-145">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="9ee5c-146">janv.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-146">janv.</span></span> <span data-ttu-id="9ee5c-147">févr.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-147">févr.</span></span> <span data-ttu-id="9ee5c-148">Mars Avril Mai Juin Juil.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-148">mars avril mai juin juil.</span></span> <span data-ttu-id="9ee5c-149">Août set.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-149">août sept.</span></span> <span data-ttu-id="9ee5c-150">Outubro.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-150">oct.</span></span> <span data-ttu-id="9ee5c-151">Nov.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-151">nov.</span></span> <span data-ttu-id="9ee5c-152">déc.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-152">déc.</span></span>
    
- <span data-ttu-id="9ee5c-153">German</span><span class="sxs-lookup"><span data-stu-id="9ee5c-153">German</span></span>
    
  - <span data-ttu-id="9ee5c-154">jänuar, februar, März, abril, Mai, Juni Juli, agosto, setembro, Oktober, novembro de Dezember</span><span class="sxs-lookup"><span data-stu-id="9ee5c-154">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="9ee5c-155">Jan./Jän.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-155">Jan./Jän.</span></span> <span data-ttu-id="9ee5c-156">Fev. März abr. Mai Juni Juli ago. set. Okt.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-156">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="9ee5c-157">Nov. dez.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-157">Nov. Dez.</span></span>
    
- <span data-ttu-id="9ee5c-158">Italian</span><span class="sxs-lookup"><span data-stu-id="9ee5c-158">Italian</span></span>
    
  - <span data-ttu-id="9ee5c-159">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="9ee5c-159">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="9ee5c-160">genn.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-160">genn.</span></span> <span data-ttu-id="9ee5c-161">febbr.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-161">febbr.</span></span> <span data-ttu-id="9ee5c-162">mar.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-162">mar.</span></span> <span data-ttu-id="9ee5c-163">abr.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-163">apr.</span></span> <span data-ttu-id="9ee5c-164">magg.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-164">magg.</span></span> <span data-ttu-id="9ee5c-165">giugno Luglio AG.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-165">giugno luglio ag.</span></span> <span data-ttu-id="9ee5c-166">definida.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-166">sett.</span></span> <span data-ttu-id="9ee5c-167">ott.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-167">ott.</span></span> <span data-ttu-id="9ee5c-168">Nov.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-168">nov.</span></span> <span data-ttu-id="9ee5c-169">DIC.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-169">dic.</span></span>
    
- <span data-ttu-id="9ee5c-170">Português</span><span class="sxs-lookup"><span data-stu-id="9ee5c-170">Portuguese</span></span>
    
  - <span data-ttu-id="9ee5c-171">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="9ee5c-171">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="9ee5c-172">Jan fev mar abr mai jun jul atrás Set out nov dez</span><span class="sxs-lookup"><span data-stu-id="9ee5c-172">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="9ee5c-173">Spanish</span><span class="sxs-lookup"><span data-stu-id="9ee5c-173">Spanish</span></span>
    
  - <span data-ttu-id="9ee5c-174">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="9ee5c-174">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="9ee5c-175">Enero Fev.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-175">enero feb.</span></span> <span data-ttu-id="9ee5c-176">Marzo abr.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-176">marzo abr.</span></span> <span data-ttu-id="9ee5c-177">Mayo Jun.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-177">mayo jun.</span></span> <span data-ttu-id="9ee5c-178">Jul.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-178">jul.</span></span> <span data-ttu-id="9ee5c-179">agosto set./set.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-179">agosto sept./set.</span></span> <span data-ttu-id="9ee5c-180">Outubro.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-180">oct.</span></span> <span data-ttu-id="9ee5c-181">Nov.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-181">nov.</span></span> <span data-ttu-id="9ee5c-182">DIC.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-182">dic.</span></span>
    
## <a name="func_eu_date1-deprecated"></a><span data-ttu-id="9ee5c-183">Func_eu_date1 (preterido)</span><span class="sxs-lookup"><span data-stu-id="9ee5c-183">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="9ee5c-184">Essa função foi preterida porque dá suporte apenas a nomes de meses em Português, que agora estão incluídos na `Func_eu_date` função acima.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-184">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="9ee5c-185">Essa função procura uma data no formato comumente usado em português.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-185">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="9ee5c-186">O formato dessa função é o mesmo que `Func_eu_date` , diferente somente no idioma usado.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-186">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="9ee5c-187">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="9ee5c-187">Examples:</span></span>
  
- <span data-ttu-id="9ee5c-188">2 dez 2016</span><span class="sxs-lookup"><span data-stu-id="9ee5c-188">2 Dez 2016</span></span>
    
- <span data-ttu-id="9ee5c-189">02 dez 2016</span><span class="sxs-lookup"><span data-stu-id="9ee5c-189">02 dez 2016</span></span>
    
- <span data-ttu-id="9ee5c-190">2 dez 16</span><span class="sxs-lookup"><span data-stu-id="9ee5c-190">2 Dez 16</span></span>
    
- <span data-ttu-id="9ee5c-191">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="9ee5c-191">2/12/2016</span></span>
    
- <span data-ttu-id="9ee5c-192">02/12/16</span><span class="sxs-lookup"><span data-stu-id="9ee5c-192">02/12/16</span></span>
    
- <span data-ttu-id="9ee5c-193">2-dez-2016</span><span class="sxs-lookup"><span data-stu-id="9ee5c-193">2-Dez-2016</span></span>
    
- <span data-ttu-id="9ee5c-194">2-12-16</span><span class="sxs-lookup"><span data-stu-id="9ee5c-194">2-12-16</span></span>
    
<span data-ttu-id="9ee5c-195">Nomes de meses aceitos:</span><span class="sxs-lookup"><span data-stu-id="9ee5c-195">Accepted month names:</span></span>
  
- <span data-ttu-id="9ee5c-196">Português</span><span class="sxs-lookup"><span data-stu-id="9ee5c-196">Portuguese</span></span>
    
  - <span data-ttu-id="9ee5c-197">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="9ee5c-197">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="9ee5c-198">Jan fev mar abr mai jun jul atrás Set out nov dez</span><span class="sxs-lookup"><span data-stu-id="9ee5c-198">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="func_eu_date2-deprecated"></a><span data-ttu-id="9ee5c-199">Func_eu_date2 (preterido)</span><span class="sxs-lookup"><span data-stu-id="9ee5c-199">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="9ee5c-200">Essa função foi preterida porque dá suporte apenas a nomes de meses em Holandês, que agora estão incluídos na `Func_eu_date` função acima.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-200">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="9ee5c-201">Essa função procura uma data no formato comumente usado em holandês.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-201">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="9ee5c-202">O formato dessa função é o mesmo que `Func_eu_date` , diferente somente no idioma usado.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-202">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="9ee5c-203">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="9ee5c-203">Examples:</span></span>
  
- <span data-ttu-id="9ee5c-204">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="9ee5c-204">2 Mei 2016</span></span>
    
- <span data-ttu-id="9ee5c-205">02 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="9ee5c-205">02 mei 2016</span></span>
    
- <span data-ttu-id="9ee5c-206">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="9ee5c-206">2 Mei 16</span></span>
    
- <span data-ttu-id="9ee5c-207">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="9ee5c-207">2/12/2016</span></span>
    
- <span data-ttu-id="9ee5c-208">02/12/16</span><span class="sxs-lookup"><span data-stu-id="9ee5c-208">02/12/16</span></span>
    
- <span data-ttu-id="9ee5c-209">2-Mei-2016</span><span class="sxs-lookup"><span data-stu-id="9ee5c-209">2-Mei-2016</span></span>
    
- <span data-ttu-id="9ee5c-210">2-12-16</span><span class="sxs-lookup"><span data-stu-id="9ee5c-210">2-12-16</span></span>
    
<span data-ttu-id="9ee5c-211">Nomes de meses aceitos:</span><span class="sxs-lookup"><span data-stu-id="9ee5c-211">Accepted month names:</span></span>
  
- <span data-ttu-id="9ee5c-212">Dutch</span><span class="sxs-lookup"><span data-stu-id="9ee5c-212">Dutch</span></span>
    
  - <span data-ttu-id="9ee5c-213">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="9ee5c-213">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="9ee5c-214">Jan Fev maart Apr Mei jun jul ago set out Okt Nov</span><span class="sxs-lookup"><span data-stu-id="9ee5c-214">jan feb maart apr mei jun jul aug sep sept out okt nov dec</span></span>
    
## <a name="func_expiration_date"></a><span data-ttu-id="9ee5c-215">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="9ee5c-215">Func_expiration_date</span></span>

<span data-ttu-id="9ee5c-216">Essa função procura uma data nos formatos usados por cartões de crédito e débito, que exclui os dias e usa os meses.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-216">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="9ee5c-217">Essa função coincidirá datas no formato de "mês/ano", "Mês-Year", "[month Name] Year" e "[month abreviation] Year".</span><span class="sxs-lookup"><span data-stu-id="9ee5c-217">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="9ee5c-218">Os nomes ou as abreviações de meses não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-218">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="9ee5c-219">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="9ee5c-219">Examples:</span></span>
  
- <span data-ttu-id="9ee5c-220">MM/AA -- por exemplo, 01/11 ou 1/11</span><span class="sxs-lookup"><span data-stu-id="9ee5c-220">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="9ee5c-221">MM/AAAA -- por exemplo, 01/2011 ou 1/2011</span><span class="sxs-lookup"><span data-stu-id="9ee5c-221">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="9ee5c-222">MM-AA -- por exemplo, 01-22 ou 1-11</span><span class="sxs-lookup"><span data-stu-id="9ee5c-222">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="9ee5c-223">MM-AAAA -- por exemplo, 01-2000 ou 1-2000</span><span class="sxs-lookup"><span data-stu-id="9ee5c-223">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="9ee5c-224">Os seguintes formatos dão suporte a AA ou AAAA:</span><span class="sxs-lookup"><span data-stu-id="9ee5c-224">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="9ee5c-225">Month-aaaa--por exemplo Jan-2010 ou Janeiro-2010 ou Jan-10 ou janeiro-10</span><span class="sxs-lookup"><span data-stu-id="9ee5c-225">Month-YYYY -- for example Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="9ee5c-226">Mês AAAA – por exemplo, 'janeiro 2010' ou 'jan 2010' ou 'janeiro 10' ou 'jan 10'</span><span class="sxs-lookup"><span data-stu-id="9ee5c-226">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="9ee5c-227">MêsAAAA – por exemplo, 'janeiro2010' ou 'Jan2010' ou 'janeiro10' ou 'Jan10'</span><span class="sxs-lookup"><span data-stu-id="9ee5c-227">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="9ee5c-228">Month/aaaa--por exemplo, ' Janeiro/2010 ' ou ' Jan/2010 ' ou ' janeiro/10 ' ou ' Jan/10 '</span><span class="sxs-lookup"><span data-stu-id="9ee5c-228">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="9ee5c-229">Nomes de meses aceitos:</span><span class="sxs-lookup"><span data-stu-id="9ee5c-229">Accepted month names:</span></span>
  
- <span data-ttu-id="9ee5c-230">English</span><span class="sxs-lookup"><span data-stu-id="9ee5c-230">English</span></span>
    
  - <span data-ttu-id="9ee5c-231">Janeiro, fevereiro, março, abril, maio, junho de julho, agosto, setembro, outubro, novembro de dezembro</span><span class="sxs-lookup"><span data-stu-id="9ee5c-231">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="9ee5c-232">Jan fev mar de junho de julho de agosto de agosto de abril de dezembro</span><span class="sxs-lookup"><span data-stu-id="9ee5c-232">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="func_us_address"></a><span data-ttu-id="9ee5c-233">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="9ee5c-233">Func_us_address</span></span>

<span data-ttu-id="9ee5c-234">Essa função procura um nome de estado americano ou abreviatura de postal seguida de um código postal válido, exatamente como eles são usados em endereços postais.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-234">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they're used in postal addresses.</span></span> <span data-ttu-id="9ee5c-235">O CEP deve ser um dos CEPs corretos associados ao nome ou sigla do estado americano.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-235">The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation.</span></span> <span data-ttu-id="9ee5c-236">O nome do estado americano e o CEP não podem ser separados por pontos ou letras.</span><span class="sxs-lookup"><span data-stu-id="9ee5c-236">The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="9ee5c-237">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="9ee5c-237">Examples:</span></span>
  
- <span data-ttu-id="9ee5c-238">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="9ee5c-238">Washington 98052</span></span>
    
- <span data-ttu-id="9ee5c-239">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="9ee5c-239">Washington 98052-9998</span></span>
    
- <span data-ttu-id="9ee5c-240">WA 98052</span><span class="sxs-lookup"><span data-stu-id="9ee5c-240">WA 98052</span></span>
    
- <span data-ttu-id="9ee5c-241">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="9ee5c-241">WA 98052-9998</span></span>
    

