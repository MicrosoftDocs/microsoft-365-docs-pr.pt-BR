---
title: Saiba mais sobre os tipos de informações confidenciais
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: ''
ms.openlocfilehash: 896a529d67faddb45b2672ca077f5a8e3b19827e
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933074"
---
# <a name="learn-about-sensitive-information-types"></a><span data-ttu-id="3fcdf-102">Saiba mais sobre os tipos de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="3fcdf-102">Learn about sensitive information types</span></span>

<span data-ttu-id="3fcdf-103">Identificar e classificar itens confidenciais que estão sob o controle de suas organizações é a primeira etapa na disciplina de Proteção [de Informações.](protect-information.md)</span><span class="sxs-lookup"><span data-stu-id="3fcdf-103">Identifying and classifying sensitive items that are under your organizations control is the first step in the [Information Protection discipline](protect-information.md).</span></span>  <span data-ttu-id="3fcdf-104">O Microsoft 365 fornece três maneiras de identificar itens para que eles possam ser classificados:</span><span class="sxs-lookup"><span data-stu-id="3fcdf-104">Microsoft 365 provides three ways of identifying items so that they can be classified:</span></span>

- <span data-ttu-id="3fcdf-105">manualmente pelos usuários</span><span class="sxs-lookup"><span data-stu-id="3fcdf-105">manually by users</span></span>
- <span data-ttu-id="3fcdf-106">reconhecimento automatizado de padrões, como tipos de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="3fcdf-106">automated pattern recognition, like sensitive information types</span></span>
- [<span data-ttu-id="3fcdf-107">aprendizado de máquina</span><span class="sxs-lookup"><span data-stu-id="3fcdf-107">machine learning</span></span>](classifier-learn-about.md)

<span data-ttu-id="3fcdf-108">Os tipos de informações confidenciais são classificadores baseados em padrões.</span><span class="sxs-lookup"><span data-stu-id="3fcdf-108">Sensitive information types are pattern-based classifiers.</span></span> <span data-ttu-id="3fcdf-109">Eles detectam informações confidenciais, como números de previdência social, cartão de crédito ou contas [bancárias,](sensitive-information-type-entity-definitions.md) para identificar itens confidenciais. Consulte Definições de entidade de tipos de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="3fcdf-109">They detect sensitive information like social security, credit card, or bank account numbers to identify sensitive items, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md)</span></span>

## <a name="sensitive-information-types-are-used-in"></a><span data-ttu-id="3fcdf-110">Os tipos de informações confidenciais são usados em</span><span class="sxs-lookup"><span data-stu-id="3fcdf-110">Sensitive information types are used in</span></span>

- [<span data-ttu-id="3fcdf-111">Políticas de prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="3fcdf-111">Data loss prevention policies</span></span>](data-loss-prevention-policies.md) 
- [<span data-ttu-id="3fcdf-112">Rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="3fcdf-112">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="3fcdf-113">Rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="3fcdf-113">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="3fcdf-114">Conformidade em comunicações</span><span class="sxs-lookup"><span data-stu-id="3fcdf-114">Communication compliance</span></span>](communication-compliance.md)
- [<span data-ttu-id="3fcdf-115">Políticas de rotulagem automática</span><span class="sxs-lookup"><span data-stu-id="3fcdf-115">Auto-labelling policies</span></span>](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a><span data-ttu-id="3fcdf-116">Partes fundamentais de um tipo de informação confidenciais</span><span class="sxs-lookup"><span data-stu-id="3fcdf-116">Fundamental parts of a sensitive information type</span></span>

<span data-ttu-id="3fcdf-117">Cada entidade de tipo de informação confidenciais é definida por estes campos:</span><span class="sxs-lookup"><span data-stu-id="3fcdf-117">Every sensitive information type entity is defined by these fields:</span></span>

- <span data-ttu-id="3fcdf-118">name: how the sensitive information type is referred to</span><span class="sxs-lookup"><span data-stu-id="3fcdf-118">name: how the sensitive information type is referred to</span></span>
- <span data-ttu-id="3fcdf-119">description: descreve o que o tipo de informação confidenciais está procurando</span><span class="sxs-lookup"><span data-stu-id="3fcdf-119">description: describes what the sensitive information type is looking for</span></span>
- <span data-ttu-id="3fcdf-120">padrão: um padrão define o que um tipo de informação confidenciais detecta.</span><span class="sxs-lookup"><span data-stu-id="3fcdf-120">pattern: A pattern defines what a sensitive information type detects.</span></span> <span data-ttu-id="3fcdf-121">Ele consiste nos seguintes componentes</span><span class="sxs-lookup"><span data-stu-id="3fcdf-121">It consists of the following components</span></span>
    - <span data-ttu-id="3fcdf-122">Elemento principal – o elemento principal que o tipo de informação sensível está procurando.</span><span class="sxs-lookup"><span data-stu-id="3fcdf-122">Primary element – the main element that the sensitive information type is looking for.</span></span> <span data-ttu-id="3fcdf-123">Pode ser uma expressão **regular com ou sem** uma validação de verificação, uma lista de palavras-chave, um dicionário de palavras-chave ou uma **função.**  </span><span class="sxs-lookup"><span data-stu-id="3fcdf-123">It can be a **regular expression** with or without a checksum validation, a **keyword list**, a **keyword dictionary**, or a **function**.</span></span>
    - <span data-ttu-id="3fcdf-124">Elemento de suporte – elementos que atuam como evidências de suporte que ajudam a aumentar a confiança da partida.</span><span class="sxs-lookup"><span data-stu-id="3fcdf-124">Supporting element – elements that act as supporting evidence that help in increasing the confidence of the match.</span></span> <span data-ttu-id="3fcdf-125">Por exemplo, a palavra-chave "SSN" perto de um número SSN.</span><span class="sxs-lookup"><span data-stu-id="3fcdf-125">For example, keyword “SSN” in proximity of an SSN number.</span></span> <span data-ttu-id="3fcdf-126">Pode ser uma expressão regular com ou sem uma validação de verificação, uma lista de palavras-chave, um dicionário de palavras-chave.</span><span class="sxs-lookup"><span data-stu-id="3fcdf-126">It can be a regular expression with or without a checksum validation, keyword list, keyword dictionary.</span></span>
    - <span data-ttu-id="3fcdf-127">Nível de Confiança - os níveis de confiança (alto, médio, baixo) refletem quanta evidência de suporte foi detectada junto com o elemento principal.</span><span class="sxs-lookup"><span data-stu-id="3fcdf-127">Confidence Level - Confidence levels (high, medium, low) reflect how much supporting evidence was detected along with the primary element.</span></span> <span data-ttu-id="3fcdf-128">Quanto mais evidências de suporte um item contiver, maior será a confiança de que um item com as informações confidenciais que você está procurando.</span><span class="sxs-lookup"><span data-stu-id="3fcdf-128">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span>
    - <span data-ttu-id="3fcdf-129">Proximidade – Número de caracteres entre o elemento principal e o elemento de suporte</span><span class="sxs-lookup"><span data-stu-id="3fcdf-129">Proximity – Number of characters between primary and supporting element</span></span>

![Diagrama da janela de proximidade e evidências comprobatórias](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

<span data-ttu-id="3fcdf-131">Saiba mais sobre os níveis de confiança neste vídeo</span><span class="sxs-lookup"><span data-stu-id="3fcdf-131">Learn more about confidence levels in this video</span></span>


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a><span data-ttu-id="3fcdf-132">Exemplo de tipo de informação sensível</span><span class="sxs-lookup"><span data-stu-id="3fcdf-132">Example sensitive information type</span></span>


## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="3fcdf-133">Número de identidade nacional (DNI) da Argentina</span><span class="sxs-lookup"><span data-stu-id="3fcdf-133">Argentina national identity (DNI) number</span></span>

### <a name="format"></a><span data-ttu-id="3fcdf-134">Formatar</span><span class="sxs-lookup"><span data-stu-id="3fcdf-134">Format</span></span>

<span data-ttu-id="3fcdf-135">Oito dígitos separados por pontos</span><span class="sxs-lookup"><span data-stu-id="3fcdf-135">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="3fcdf-136">Padrão</span><span class="sxs-lookup"><span data-stu-id="3fcdf-136">Pattern</span></span>

<span data-ttu-id="3fcdf-137">Oito dígitos:</span><span class="sxs-lookup"><span data-stu-id="3fcdf-137">Eight digits:</span></span>
- <span data-ttu-id="3fcdf-138">dois dígitos</span><span class="sxs-lookup"><span data-stu-id="3fcdf-138">two digits</span></span>
- <span data-ttu-id="3fcdf-139">um ponto</span><span class="sxs-lookup"><span data-stu-id="3fcdf-139">a period</span></span>
- <span data-ttu-id="3fcdf-140">três dígitos</span><span class="sxs-lookup"><span data-stu-id="3fcdf-140">three digits</span></span>
- <span data-ttu-id="3fcdf-141">um ponto</span><span class="sxs-lookup"><span data-stu-id="3fcdf-141">a period</span></span>
- <span data-ttu-id="3fcdf-142">três dígitos</span><span class="sxs-lookup"><span data-stu-id="3fcdf-142">three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="3fcdf-143">Soma de verificação</span><span class="sxs-lookup"><span data-stu-id="3fcdf-143">Checksum</span></span>

<span data-ttu-id="3fcdf-144">Não</span><span class="sxs-lookup"><span data-stu-id="3fcdf-144">No</span></span>

### <a name="definition"></a><span data-ttu-id="3fcdf-145">Definição</span><span class="sxs-lookup"><span data-stu-id="3fcdf-145">Definition</span></span>

<span data-ttu-id="3fcdf-146">Uma política de DLP tem confiança média de que ela detectou esse tipo de informação sensível se, dentro de uma proximidade de 300 caracteres:</span><span class="sxs-lookup"><span data-stu-id="3fcdf-146">A DLP policy has medium confidence that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="3fcdf-147">A expressão regular Regex_argentina_national_id localiza conteúdo que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="3fcdf-147">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="3fcdf-148">Uma palavra-chave Keyword_argentina_national_id for encontrada.</span><span class="sxs-lookup"><span data-stu-id="3fcdf-148">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3fcdf-149">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="3fcdf-149">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="3fcdf-150">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="3fcdf-150">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="3fcdf-151">Número de Identidade Nacional da Argentina</span><span class="sxs-lookup"><span data-stu-id="3fcdf-151">Argentina National Identity number</span></span> 
- <span data-ttu-id="3fcdf-152">Identidade</span><span class="sxs-lookup"><span data-stu-id="3fcdf-152">Identity</span></span> 
- <span data-ttu-id="3fcdf-153">Cartão de Identidade Nacional de Identificação</span><span class="sxs-lookup"><span data-stu-id="3fcdf-153">Identification National Identity Card</span></span> 
- <span data-ttu-id="3fcdf-154">DNI</span><span class="sxs-lookup"><span data-stu-id="3fcdf-154">DNI</span></span> 
- <span data-ttu-id="3fcdf-155">Registro Nacional NIC de Pessoas</span><span class="sxs-lookup"><span data-stu-id="3fcdf-155">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="3fcdf-156">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="3fcdf-156">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="3fcdf-157">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="3fcdf-157">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="3fcdf-158">Identidad</span><span class="sxs-lookup"><span data-stu-id="3fcdf-158">Identidad</span></span> 
- <span data-ttu-id="3fcdf-159">Identificación</span><span class="sxs-lookup"><span data-stu-id="3fcdf-159">Identificación</span></span> 

### <a name="more-on-confidence-levels"></a><span data-ttu-id="3fcdf-160">Mais sobre níveis de confiança</span><span class="sxs-lookup"><span data-stu-id="3fcdf-160">More on confidence levels</span></span>

<span data-ttu-id="3fcdf-161">Em uma definição de entidade de tipo de informação **confidenciais,** o nível de confiança reflete a quanta evidência de suporte é detectada, além do elemento principal.</span><span class="sxs-lookup"><span data-stu-id="3fcdf-161">In a sensitive information type entity definition, **confidence level** reflects how much supporting evidence is detected in addition to the primary element.</span></span> <span data-ttu-id="3fcdf-162">Quanto mais evidências de suporte um item contiver, maior será a confiança de que um item com as informações confidenciais que você está procurando.</span><span class="sxs-lookup"><span data-stu-id="3fcdf-162">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span> <span data-ttu-id="3fcdf-163">Por exemplo, as combinações com um alto nível de confiança conterão evidências de suporte mais próximas do elemento principal, enquanto as combinações com um nível de confiança baixo conteriam pouca ou nenhuma evidência de suporte próxima.</span><span class="sxs-lookup"><span data-stu-id="3fcdf-163">For example, matches with a high confidence level will contain more supporting evidence in close proximity of the primary element, whereas matches with a low confidence level would contain little to no supporting evidence in close proximity.</span></span> 

<span data-ttu-id="3fcdf-164">Um nível de confiança alto retorna o menor número de falsos positivos, mas pode resultar em mais falsos negativos.</span><span class="sxs-lookup"><span data-stu-id="3fcdf-164">A high confidence level returns the fewest false positives but might result in more false negatives.</span></span> <span data-ttu-id="3fcdf-165">Níveis de confiança baixos ou médios retornam mais falsos positivos, mas poucos a zero falsos negativos.</span><span class="sxs-lookup"><span data-stu-id="3fcdf-165">Low or medium confidence levels returns more false positives but few to zero false negatives.</span></span>

- <span data-ttu-id="3fcdf-166">**baixa confiança**: o valor de 65 itens, os itens que corresponderem conterão o menor falso negativo, mas a maioria dos falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="3fcdf-166">**low confidence**: value of 65, matched items will contain the fewest false negatives but the most false positives.</span></span>  
- <span data-ttu-id="3fcdf-167">**confiança média**: valor de 75, itens de corresponder conterão uma quantidade média de falsos positivos e falsos negativos.</span><span class="sxs-lookup"><span data-stu-id="3fcdf-167">**medium confidence**: value of 75, matched items will contain an average amount of false positives and false negatives.</span></span>  
- <span data-ttu-id="3fcdf-168">**alta confiança**: o valor de 85 itens, os itens que corresponderem conterão o menor número de falsos positivos, mas a maioria dos falsos negativos.</span><span class="sxs-lookup"><span data-stu-id="3fcdf-168">**high confidence**: value of 85, matched items will contain the fewest false positives but the most false negatives.</span></span>  

<span data-ttu-id="3fcdf-169">Você deve usar padrões de nível de alta confiança com contagens baixas, cinco a dez e padrões de baixa confiança com contagens mais altas, digamos 20 ou mais.</span><span class="sxs-lookup"><span data-stu-id="3fcdf-169">You should use high confidence level patterns with low counts, say five to ten, and low confidence patterns with higher counts, say 20 or more.</span></span>

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="3fcdf-170">Criando tipos de informações confidenciais personalizadas</span><span class="sxs-lookup"><span data-stu-id="3fcdf-170">Creating custom sensitive information types</span></span>

<span data-ttu-id="3fcdf-171">Para criar tipos de informações confidenciais personalizadas no Centro de Conformidade e Segurança, você pode escolher entre várias opções:</span><span class="sxs-lookup"><span data-stu-id="3fcdf-171">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="3fcdf-172">**Usar a interface do usuário** Você pode configurar um tipo de informações confidenciais personalizadas usando o a interface do usuário do Centro de Conformidade e Segurança.</span><span class="sxs-lookup"><span data-stu-id="3fcdf-172">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="3fcdf-173">Com esse método, você pode usar expressões comuns, palavras-chave e dicionários de palavras-chave.</span><span class="sxs-lookup"><span data-stu-id="3fcdf-173">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="3fcdf-174">Para saber mais, confira [Criar um tipo de informações confidenciais personalizadas](create-a-custom-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="3fcdf-174">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

- <span data-ttu-id="3fcdf-175">**Use EDM** Você pode configurar tipos de informações confidenciais personalizadas usando a classificação baseada em EDM (Exact Data Match).</span><span class="sxs-lookup"><span data-stu-id="3fcdf-175">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="3fcdf-176">Esse método permite criar um tipo de informações confidenciais dinâmico usando um banco de dados seguro que você pode atualizar periodicamente.</span><span class="sxs-lookup"><span data-stu-id="3fcdf-176">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="3fcdf-177">Confira [Criar um tipo de informações confidenciais personalizadas com classificação baseada em Exact Data Match](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="3fcdf-177">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="3fcdf-178">**Use o PowerShell** Você pode configurar tipos de informações confidenciais personalizadas usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fcdf-178">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="3fcdf-179">Embora esse método seja mais complexo do que usar a interface do usuário, você tem mais opções de configuração.</span><span class="sxs-lookup"><span data-stu-id="3fcdf-179">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="3fcdf-180">Consulte [Criar um tipo de informações confidenciais personalizadas no Centro de Conformidade e Segurança do PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="3fcdf-180">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>



> [!NOTE]
> <span data-ttu-id="3fcdf-181">A Proteção de Informações do Microsoft 365 agora oferece suporte a idiomas de conjunto de caracteres de byte duplo de visualização:</span><span class="sxs-lookup"><span data-stu-id="3fcdf-181">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="3fcdf-182">Chinês (simplificado)</span><span class="sxs-lookup"><span data-stu-id="3fcdf-182">Chinese (simplified)</span></span>
> - <span data-ttu-id="3fcdf-183">Chinês (tradicional)</span><span class="sxs-lookup"><span data-stu-id="3fcdf-183">Chinese (traditional)</span></span>
> - <span data-ttu-id="3fcdf-184">Coreano</span><span class="sxs-lookup"><span data-stu-id="3fcdf-184">Korean</span></span>
> - <span data-ttu-id="3fcdf-185">Japonês</span><span class="sxs-lookup"><span data-stu-id="3fcdf-185">Japanese</span></span>

><span data-ttu-id="3fcdf-186">Este suporte está disponível para tipos de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="3fcdf-186">This support is available for sensitive information types.</span></span> <span data-ttu-id="3fcdf-187">Para obter mais informações, confira [Suporte à proteção de informações para notas de versão de conjuntos de caracteres de byte duplo (visualização)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="3fcdf-187">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="for-further-information"></a><span data-ttu-id="3fcdf-188">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="3fcdf-188">For further information</span></span>
- [<span data-ttu-id="3fcdf-189">Definições da entidade do tipo de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="3fcdf-189">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="3fcdf-190">Criar um tipo de informação confidencial personalizado</span><span class="sxs-lookup"><span data-stu-id="3fcdf-190">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
- [<span data-ttu-id="3fcdf-191">Criar um tipo personalizado de informação confidenciais no PowerShell</span><span class="sxs-lookup"><span data-stu-id="3fcdf-191">Create a custom sensitive information type in PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->