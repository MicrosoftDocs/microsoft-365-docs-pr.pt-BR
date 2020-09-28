---
title: Tipos de explicação
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba mais sobre tipos de explicação no Microsoft SharePoint Syntex
ms.openlocfilehash: f4f5dbc24bef57b1801f7df1b7e2fc7ef9b08116
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295708"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="edd8d-103">Introdução aos tipos de explicação</span><span class="sxs-lookup"><span data-stu-id="edd8d-103">Introduction to explanation types</span></span>

<span data-ttu-id="edd8d-104">Use explicações para ajudar a definir as informações que você deseja rotular e extrair no documento os modelos de compreensão para o Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="edd8d-104">Use explanations to help to define the information that you want to label, and extract in your document the understanding models for Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="edd8d-105">Ao criar uma explicação, certifique-se de selecionar um tipo de explicação.</span><span class="sxs-lookup"><span data-stu-id="edd8d-105">When you create an explanation, be sure to select an explanation type.</span></span> 

<span data-ttu-id="edd8d-106">Este artigo ajuda você a compreender os diferentes tipos de explicação e como eles são usados.</span><span class="sxs-lookup"><span data-stu-id="edd8d-106">This article helps you understand the different explanation types and how they are used.</span></span>

   ![Tipos de explicação](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="edd8d-108">Estes tipos de explicação estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="edd8d-108">These explanation types are available:</span></span>

- <span data-ttu-id="edd8d-109">**Lista de frases**: lista de palavras, frases, números ou outros caracteres que você pode usar no documento ou informações que você está extraindo.</span><span class="sxs-lookup"><span data-stu-id="edd8d-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="edd8d-110">Por exemplo, a cadeia de caracteres de texto que **faz referência ao doutor** está em todos os documentos de referência médica que você está identificando.</span><span class="sxs-lookup"><span data-stu-id="edd8d-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="edd8d-111">**Lista padrão**: padrões de lista de números, letras ou outros caracteres que você pode usar para identificar as informações que você está extraindo.</span><span class="sxs-lookup"><span data-stu-id="edd8d-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="edd8d-112">Por exemplo, você pode extrair o **número de telefone** do médico de referência de todos os documentos de referência médica que está identificando.</span><span class="sxs-lookup"><span data-stu-id="edd8d-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="edd8d-113">**Proximidade**: descreve como as explicações de fechamento estão entre si.</span><span class="sxs-lookup"><span data-stu-id="edd8d-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="edd8d-114">Por exemplo, uma lista de padrões de *números de rua* fica correta antes da lista de frases de *nome de rua* , sem tokens entre (você aprenderá tokens mais adiante neste artigo).</span><span class="sxs-lookup"><span data-stu-id="edd8d-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="edd8d-115">Lista de frases</span><span class="sxs-lookup"><span data-stu-id="edd8d-115">Phrase list</span></span>

<span data-ttu-id="edd8d-116">Uma lista de frases o tipo explicação geralmente é usado para identificar e classificar um documento por meio do modelo.</span><span class="sxs-lookup"><span data-stu-id="edd8d-116">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="edd8d-117">Conforme descrito no exemplo de etiqueta de *referência médica* , é uma cadeia de caracteres de palavras, frases, números ou caracteres que é consistentemente nos documentos que você está identificando.</span><span class="sxs-lookup"><span data-stu-id="edd8d-117">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="edd8d-118">Embora não seja um requisito, você pode obter um sucesso melhor com sua explicação se a frase que você está capturando estiver localizada em um local consistente no seu documento.</span><span class="sxs-lookup"><span data-stu-id="edd8d-118">While not a requirement, you can acheive better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="edd8d-119">Por exemplo, a etiqueta de *referência médica* pode ser localizada de forma consistente no primeiro parágrafo do documento.</span><span class="sxs-lookup"><span data-stu-id="edd8d-119">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="edd8d-120">Se a diferenciação de maiúsculas e minúsculas for um requisito para identificar seu rótulo, usar o tipo de lista de frases permite que você o especifique em sua explicação, marcando a caixa de seleção **somente maiúscula exata** .</span><span class="sxs-lookup"><span data-stu-id="edd8d-120">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![Diferenciação de maiúsculas e minúsculas](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="edd8d-122">Listas de padrões</span><span class="sxs-lookup"><span data-stu-id="edd8d-122">Pattern lists</span></span>

<span data-ttu-id="edd8d-123">Um tipo de lista padrão é especialmente útil quando você cria uma explicação que identifica e extrai informações de um documento.</span><span class="sxs-lookup"><span data-stu-id="edd8d-123">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="edd8d-124">Geralmente, ele é apresentado em formatos diferentes, como datas, números de telefone ou números de cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="edd8d-124">It is typically presented in different formats, such as dates, phone numbers, or credit card numbers.</span></span> <span data-ttu-id="edd8d-125">Por exemplo, uma data pode ser exibida em vários formatos diferentes (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1, 2020, etc.).</span><span class="sxs-lookup"><span data-stu-id="edd8d-125">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="edd8d-126">A definição de uma lista de padrões torna sua explicação mais eficiente, capturando quaisquer variações possíveis nos dados que você está tentando identificar e extrair.</span><span class="sxs-lookup"><span data-stu-id="edd8d-126">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="edd8d-127">Para o exemplo de **número de telefone** , extraia o número de telefone de cada referência médica de todos os documentos de referência médica que o modelo identifica.</span><span class="sxs-lookup"><span data-stu-id="edd8d-127">For the **Phone number** sample, extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="edd8d-128">Ao criar a explicação, selecione o tipo de lista padrão para permitir que os diferentes formatos que você espera que sejam retornados.</span><span class="sxs-lookup"><span data-stu-id="edd8d-128">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![Lista de padrões de números de telefone](../media/content-understanding/pattern-list.png)

<span data-ttu-id="edd8d-130">Para este exemplo, selecione a caixa de seleção **qualquer dígito de 0-9** .</span><span class="sxs-lookup"><span data-stu-id="edd8d-130">For this sample, select the **Any digit from 0-9** checkbox.</span></span> <span data-ttu-id="edd8d-131">Selecionar isso reconhece cada valor "0" usado na sua lista de padrões para ser qualquer dígito de 0 a 9.</span><span class="sxs-lookup"><span data-stu-id="edd8d-131">Selecting this recognizes each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![Qualquer dígito de 0-9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="edd8d-133">Da mesma forma, se você criar uma lista de padrões que inclua caracteres de texto, selecione a **letra qualquer da** caixa de seleção-z.</span><span class="sxs-lookup"><span data-stu-id="edd8d-133">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox.</span></span> <span data-ttu-id="edd8d-134">Selecionar isso reconhece cada caractere "a" usado na lista padrão como qualquer caractere de "a" a "z".</span><span class="sxs-lookup"><span data-stu-id="edd8d-134">Selecting this recognizes each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="edd8d-135">Por exemplo, se você criar uma lista de padrões de **datas** e quiser certificar-se de que um formato de data como *1 Jan 2020* seja reconhecido, você precisará:</span><span class="sxs-lookup"><span data-stu-id="edd8d-135">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="edd8d-136">Adicione *AAA 0, 0000* e *AAA 00, 0000* à sua lista padrão.</span><span class="sxs-lookup"><span data-stu-id="edd8d-136">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="edd8d-137">Verifique se **qualquer letra de a-z** também está selecionada.</span><span class="sxs-lookup"><span data-stu-id="edd8d-137">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![Qualquer letra de a a z](../media/content-understanding/any-letter.png)

<span data-ttu-id="edd8d-139">Além disso, se você tiver requisitos de capitalização em sua lista padrão, terá a opção de selecionar somente a caixa de seleção **exata maiúscula** .</span><span class="sxs-lookup"><span data-stu-id="edd8d-139">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="edd8d-140">Para o exemplo de data, se você precisar que a primeira letra do mês seja capitalizada, será necessário:</span><span class="sxs-lookup"><span data-stu-id="edd8d-140">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="edd8d-141">Adicione *AAA 0, 0000* e *AAA 00, 0000* à sua lista padrão.</span><span class="sxs-lookup"><span data-stu-id="edd8d-141">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="edd8d-142">Certifique-se de que **apenas a capitalização exata** também esteja selecionada.</span><span class="sxs-lookup"><span data-stu-id="edd8d-142">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![Apenas maiúscula exata](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="edd8d-144">Em vez de criar a explicação da lista de padrões manualmente, use a [biblioteca explicação]() para usar modelos de lista de padrões predefinidos para lista de padrões comuns, como *Data*, *número de telefone*, *número de cartão de crédito*, etc..</span><span class="sxs-lookup"><span data-stu-id="edd8d-144">Instead of manually creating pattern list explanation, use the [explanation library]() to use pre-made pattern list templates for common pattern list, such as *date*, *phone number*, *credit card number*, etc..</span></span> 

## <a name="proximity"></a><span data-ttu-id="edd8d-145">Proximidade</span><span class="sxs-lookup"><span data-stu-id="edd8d-145">Proximity</span></span> 

<span data-ttu-id="edd8d-146">O tipo de explicação de proximidade ajuda seu modelo a identificar dados por meio da definição de como fechar outros dados.</span><span class="sxs-lookup"><span data-stu-id="edd8d-146">The proximity explanation type helps your model identify data through defining how close another piece of data is to it.</span></span> <span data-ttu-id="edd8d-147">Por exemplo, em seu modelo, você definiu duas explicações que rotulam o *número de endereço* e número de *telefone*do cliente.</span><span class="sxs-lookup"><span data-stu-id="edd8d-147">For example, in your model, you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="edd8d-148">Observe também que os números de telefone do cliente sempre aparecem antes do número de endereço.</span><span class="sxs-lookup"><span data-stu-id="edd8d-148">You also notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="edd8d-149">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="edd8d-149">Alex Wilburn</span></span><br>
<span data-ttu-id="edd8d-150">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="edd8d-150">555-555-5555</span></span><br>
<span data-ttu-id="edd8d-151">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="edd8d-151">One Microsoft Way</span></span><br>
<span data-ttu-id="edd8d-152">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="edd8d-152">Redmond, WA 98034</span></span><br>

<span data-ttu-id="edd8d-153">Use a explicação de proximidade para definir o quanto longe a explicação do número de telefone é para identificar melhor o número de endereço dos seus documentos.</span><span class="sxs-lookup"><span data-stu-id="edd8d-153">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![Explicação de proximidade](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="edd8d-155">O que são tokens?</span><span class="sxs-lookup"><span data-stu-id="edd8d-155">What are tokens?</span></span>

<span data-ttu-id="edd8d-156">Para usar o tipo de explicação de proximidade, entenda o que é um token, como o número de tokens é como a explicação de proximidade mede a distância de uma explicação para outra.</span><span class="sxs-lookup"><span data-stu-id="edd8d-156">In order to use the proximity explanation type, understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span>  

<span data-ttu-id="edd8d-157">Um token é uma extensão contínua (sem espaços ou pontuação) de letras e números.</span><span class="sxs-lookup"><span data-stu-id="edd8d-157">A token is a continuous span (no spaces or punctuation) of letters and numbers.</span></span> <span data-ttu-id="edd8d-158">Um espaço não é um token.</span><span class="sxs-lookup"><span data-stu-id="edd8d-158">A space is NOT a token.</span></span> <span data-ttu-id="edd8d-159">Cada caractere de pontuação é um token.</span><span class="sxs-lookup"><span data-stu-id="edd8d-159">Each punctuation character is a token.</span></span> <span data-ttu-id="edd8d-160">A tabela a seguir mostra alguns exemplos de como determinar o número de tokens em uma frase.</span><span class="sxs-lookup"><span data-stu-id="edd8d-160">The following table shows some examples of how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="edd8d-161">Faça</span><span class="sxs-lookup"><span data-stu-id="edd8d-161">Phrase</span></span>|<span data-ttu-id="edd8d-162">Número de tokens</span><span class="sxs-lookup"><span data-stu-id="edd8d-162">Number of tokens</span></span>|<span data-ttu-id="edd8d-163">Explicação</span><span class="sxs-lookup"><span data-stu-id="edd8d-163">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="edd8d-164">1 </span><span class="sxs-lookup"><span data-stu-id="edd8d-164">1</span></span>|<span data-ttu-id="edd8d-165">Uma única palavra sem pontuação ou espaços.</span><span class="sxs-lookup"><span data-stu-id="edd8d-165">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="edd8d-166">1 </span><span class="sxs-lookup"><span data-stu-id="edd8d-166">1</span></span>|<span data-ttu-id="edd8d-167">Um número de localizador de registro.</span><span class="sxs-lookup"><span data-stu-id="edd8d-167">A record locator number.</span></span> <span data-ttu-id="edd8d-168">Ele pode ter números e letras, mas não tem pontuação.</span><span class="sxs-lookup"><span data-stu-id="edd8d-168">It may have numbers and letters, but does not have any punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="edd8d-169">5 </span><span class="sxs-lookup"><span data-stu-id="edd8d-169">5</span></span>|<span data-ttu-id="edd8d-170">Um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="edd8d-170">A phone number.</span></span> <span data-ttu-id="edd8d-171">Cada marca de pontuação é um único token, portanto,  `425-555-5555` deve ser de 5 tokens:</span><span class="sxs-lookup"><span data-stu-id="edd8d-171">Each punctuation mark is a single token so  `425-555-5555` would be 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="edd8d-172">7 </span><span class="sxs-lookup"><span data-stu-id="edd8d-172">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="edd8d-173">Configurar o tipo de explicação de proximidade</span><span class="sxs-lookup"><span data-stu-id="edd8d-173">Configure the proximity explanation type</span></span>

<span data-ttu-id="edd8d-174">Para o exemplo, configure a configuração de proximidade para que possamos definir o intervalo do número de tokens que o *número de telefone* explicação é da explicação de número de endereço de *rua* .</span><span class="sxs-lookup"><span data-stu-id="edd8d-174">For the sample, configure the proximity setting so that we can define the range of the number of tokens the *Phone number* explanation is from the *Street address number* explanation.</span></span>

<span data-ttu-id="edd8d-175">Você deve ver que o intervalo mínimo é "0", já que não há tokens entre o número de telefone e o número de endereço.</span><span class="sxs-lookup"><span data-stu-id="edd8d-175">You should see that the minimum range is "0" since there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="edd8d-176">No entanto, alguns números de telefone nos documentos de exemplo são acrescentados com *(móvel)*.</span><span class="sxs-lookup"><span data-stu-id="edd8d-176">However, some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="edd8d-177">Marcos Wilke</span><span class="sxs-lookup"><span data-stu-id="edd8d-177">Nestor Wilke</span></span><br>
<span data-ttu-id="edd8d-178">111-111-1111 (celular)</span><span class="sxs-lookup"><span data-stu-id="edd8d-178">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="edd8d-179">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="edd8d-179">One Microsoft Way</span></span><br>
<span data-ttu-id="edd8d-180">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="edd8d-180">Redmond, WA 98034</span></span><br>

<span data-ttu-id="edd8d-181">Há três tokens no *(celular)*:</span><span class="sxs-lookup"><span data-stu-id="edd8d-181">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="edd8d-182">Faça</span><span class="sxs-lookup"><span data-stu-id="edd8d-182">Phrase</span></span>|<span data-ttu-id="edd8d-183">Contagem de tokens</span><span class="sxs-lookup"><span data-stu-id="edd8d-183">Token count</span></span>|
|--|--|
|<span data-ttu-id="edd8d-184">(</span><span class="sxs-lookup"><span data-stu-id="edd8d-184">(</span></span>|<span data-ttu-id="edd8d-185">1 </span><span class="sxs-lookup"><span data-stu-id="edd8d-185">1</span></span>|
|<span data-ttu-id="edd8d-186">processadores</span><span class="sxs-lookup"><span data-stu-id="edd8d-186">mobile</span></span>|<span data-ttu-id="edd8d-187">2 </span><span class="sxs-lookup"><span data-stu-id="edd8d-187">2</span></span>|
|<span data-ttu-id="edd8d-188">)</span><span class="sxs-lookup"><span data-stu-id="edd8d-188">)</span></span>|<span data-ttu-id="edd8d-189">3 </span><span class="sxs-lookup"><span data-stu-id="edd8d-189">3</span></span>|

<span data-ttu-id="edd8d-190">Defina a configuração de proximidade para ter um intervalo de 0 a 3.</span><span class="sxs-lookup"><span data-stu-id="edd8d-190">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![Exemplo de proximidade](../media/content-understanding/proximity-example.png)</br>

## <a name="use-the-explanation-library"></a><span data-ttu-id="edd8d-192">Usar a biblioteca de explicação</span><span class="sxs-lookup"><span data-stu-id="edd8d-192">Use the explanation library</span></span>

<span data-ttu-id="edd8d-193">Embora você possa adicionar manualmente vários valores de lista padrão para sua explicação, é muito mais fácil usar os modelos pré-criados fornecidos na biblioteca de explicação.</span><span class="sxs-lookup"><span data-stu-id="edd8d-193">While you can manually add various pattern list values for your explanation, it's much easier to use the pre-created templates provided to you in the explanation library.</span></span>

<span data-ttu-id="edd8d-194">Por exemplo, em vez de adicionar manualmente todas as variações para *Data*, use o modelo de lista de padrões para *Data*, que já inclua um número de padrões de listas:</span><span class="sxs-lookup"><span data-stu-id="edd8d-194">For example, instead of manually adding all the variations for *Date*, use the pattern list template for *Date*, that already includes a number of pattern lists values:</span></span></br>

   ![Biblioteca de explicação](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="edd8d-196">A biblioteca explicação inclui uma série de explicações de lista de padrões comumente usadas, incluindo:</span><span class="sxs-lookup"><span data-stu-id="edd8d-196">The explanation library includes a number of commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="edd8d-197">Data</span><span class="sxs-lookup"><span data-stu-id="edd8d-197">Date</span></span></br>
- <span data-ttu-id="edd8d-198">Data (numérico)</span><span class="sxs-lookup"><span data-stu-id="edd8d-198">Date (numeric)</span></span></br>
- <span data-ttu-id="edd8d-199">Time</span><span class="sxs-lookup"><span data-stu-id="edd8d-199">Time</span></span></br>
- <span data-ttu-id="edd8d-200">Número</span><span class="sxs-lookup"><span data-stu-id="edd8d-200">Number</span></span></br>
- <span data-ttu-id="edd8d-201">Número de telefone</span><span class="sxs-lookup"><span data-stu-id="edd8d-201">Phone number</span></span></br>
- <span data-ttu-id="edd8d-202">Código Postal</span><span class="sxs-lookup"><span data-stu-id="edd8d-202">Zip code</span></span></br>
- <span data-ttu-id="edd8d-203">Primeira palavra da frase</span><span class="sxs-lookup"><span data-stu-id="edd8d-203">First word of sentence</span></span></br>
- <span data-ttu-id="edd8d-204">Cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="edd8d-204">Credit card</span></span></br>
- <span data-ttu-id="edd8d-205">Número de seguro social</span><span class="sxs-lookup"><span data-stu-id="edd8d-205">Social security number</span></span></br>

<span data-ttu-id="edd8d-206">Observe que a biblioteca de explicação também inclui modelos para explicações de lista de frases, incluindo:</span><span class="sxs-lookup"><span data-stu-id="edd8d-206">Note that the explanation library also includes templates for phrase list explanations as well, including:</span></span>
- <span data-ttu-id="edd8d-207">Fim da frase</span><span class="sxs-lookup"><span data-stu-id="edd8d-207">End of sentence</span></span>
- <span data-ttu-id="edd8d-208">Moeda</span><span class="sxs-lookup"><span data-stu-id="edd8d-208">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="edd8d-209">Para usar um modelo da biblioteca de explicação</span><span class="sxs-lookup"><span data-stu-id="edd8d-209">To use a template from the explanation library</span></span>

1. <span data-ttu-id="edd8d-210">Na seção **explicações** da página de **treinamento** do seu modelo, selecione **novo**e, em seguida, selecione **a partir de um modelo**.</span><span class="sxs-lookup"><span data-stu-id="edd8d-210">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![Criar do modelo](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="edd8d-212">Na página **modelos de explicação** , selecione a explicação que você deseja usar e, em seguida, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="edd8d-212">On the **Explanation templates** page, select the explanation you want to use, and then select **Add**.</span></span></br>

       ![Selecionar um modelo](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="edd8d-214">As informações do modelo selecionado serão exibidas na página **criar uma explicação** .</span><span class="sxs-lookup"><span data-stu-id="edd8d-214">The information for the template you selected will display on the **Create an explanation** page.</span></span> <span data-ttu-id="edd8d-215">Se necessário, edite o nome da explicação e adicione ou remova itens da lista padrão.</span><span class="sxs-lookup"><span data-stu-id="edd8d-215">If needed, edit the explanation name, and add or remove items from the pattern list.</span></span> </br> 

   ![Editar modelo](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="edd8d-217">Quando terminar, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="edd8d-217">When finished, select **Save**.</span></span>
