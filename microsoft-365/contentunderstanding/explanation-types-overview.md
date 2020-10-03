---
title: Tipos de explicação
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Saiba mais sobre tipos de explicação no Microsoft SharePoint Syntex
ms.openlocfilehash: 4fe13a35757807e08638f68259ccd24a59a97460
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338656"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="24c8c-103">Introdução aos tipos de explicação</span><span class="sxs-lookup"><span data-stu-id="24c8c-103">Introduction to explanation types</span></span>

<span data-ttu-id="24c8c-104">As explicações são usadas para ajudar a definir as informações que você deseja rotular e extrai para seus modelos de compreensão de documentos no Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="24c8c-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="24c8c-105">Ao criar uma explicação, você precisa selecionar um tipo de explicação.</span><span class="sxs-lookup"><span data-stu-id="24c8c-105">When creating an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="24c8c-106">Este artigo vai ajudá-lo a entender melhor os diferentes tipos de explicação e como eles são usados.</span><span class="sxs-lookup"><span data-stu-id="24c8c-106">This article will help you learn more to better understand the different explanation types and how they are used.</span></span> 

   ![Tipos de explicação](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="24c8c-108">Esses tipos de explicação estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="24c8c-108">These explanation types are available:</span></span>

- <span data-ttu-id="24c8c-109">**Lista de frases**: lista de palavras, frases, números ou outros caracteres que você pode usar no documento ou informações que você está extraindo.</span><span class="sxs-lookup"><span data-stu-id="24c8c-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="24c8c-110">Por exemplo, a cadeia de texto **Médico encaminhador** está em todos os documentos de Encaminhamento Médico que você está identificando.</span><span class="sxs-lookup"><span data-stu-id="24c8c-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="24c8c-111">**Lista de padrões**: lista padrões de números, letras ou outros caracteres que você pode usar para identificar as informações que você está extraindo.</span><span class="sxs-lookup"><span data-stu-id="24c8c-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="24c8c-112">Por exemplo, você pode extrair o **Número de telefone** do médico encaminhador de todos os documentos de Encaminhamento Médico que você está identificando.</span><span class="sxs-lookup"><span data-stu-id="24c8c-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="24c8c-113">**Proximidade**: descreve a proximidade das explicações entre si. </span><span class="sxs-lookup"><span data-stu-id="24c8c-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="24c8c-114">Por exemplo, uma lista de padrões de *número da rua* fica antes da lista de frases de *nome da rua*, sem tokens entre elas (você aprenderá sobre tokens mais adiante neste artigo).</span><span class="sxs-lookup"><span data-stu-id="24c8c-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="24c8c-115">Usar o tipo de proximidade exige que você tenha pelo menos duas explicações em seu modelo, ou a opção será desabilitada.</span><span class="sxs-lookup"><span data-stu-id="24c8c-115">Using the proximity type requires you to have at least two explanations in your model, or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="24c8c-116">Lista de frases</span><span class="sxs-lookup"><span data-stu-id="24c8c-116">Phrase list</span></span>

<span data-ttu-id="24c8c-117">Um tipo de explicação de lista de frases geralmente é usado para identificar e classificar um documento por meio do seu modelo.</span><span class="sxs-lookup"><span data-stu-id="24c8c-117">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="24c8c-118">Conforme descrito no exemplo de rótulo *Médico encaminhador*, é uma cadeia de cadeia de palavras, frases, números ou caracteres que está de maneira consistente nos documentos que você está identificando.</span><span class="sxs-lookup"><span data-stu-id="24c8c-118">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="24c8c-119">Embora não seja um requisito, você pode obter um sucesso melhor com a sua explicação se a frase que está capturando estiver localizada em um local consistente no documento.</span><span class="sxs-lookup"><span data-stu-id="24c8c-119">While not a requirement, you can achieve better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="24c8c-120">Por exemplo, o rótulo *Médico encaminhador* pode estar localizado, de maneira consistente, no primeiro parágrafo do documento.</span><span class="sxs-lookup"><span data-stu-id="24c8c-120">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="24c8c-121">Se a diferenciação de maiúsculas e minúsculas for um requisito para a identificação do seu rótulo, usar o tipo de lista de frases permite que você o especifique na sua explicação selecionando a caixa de seleção **Somente maiúsculas**.</span><span class="sxs-lookup"><span data-stu-id="24c8c-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![Diferenciação de maiúsculas e minúsculas](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="24c8c-123">Listas de padrões</span><span class="sxs-lookup"><span data-stu-id="24c8c-123">Pattern lists</span></span>

<span data-ttu-id="24c8c-124">Um tipo de lista de padrões é especialmente útil quando você cria uma explicação que identifica e extrai informações de um documento.</span><span class="sxs-lookup"><span data-stu-id="24c8c-124">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="24c8c-125">Geralmente, é apresentado em formatos diferentes, como datas, números de telefone ou de cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="24c8c-125">It is typically presented in different formats, such as dates, phone numbers, or credit card numbers.</span></span> <span data-ttu-id="24c8c-126">Por exemplo, um data pode ser exibida em diversos formatos (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1º de janeiro de 2020, etc.).</span><span class="sxs-lookup"><span data-stu-id="24c8c-126">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="24c8c-127">A definição de uma lista de padrões torna suas explicações mais eficientes, capturando todas as variações possíveis nos dados que você está tentando identificar e extrair.</span><span class="sxs-lookup"><span data-stu-id="24c8c-127">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="24c8c-128">Para obter o exemplo de **Número de telefone**, extraia o número de telefone de cada médico encaminhador de todos os documentos de Encaminhamento Médico identificados pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="24c8c-128">For the **Phone number** sample, extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="24c8c-129">Ao criar a explicação, selecione o tipo de lista de padrões para permitir que os diferentes formados esperados sejam retornados.</span><span class="sxs-lookup"><span data-stu-id="24c8c-129">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![Lista de padrões de número de telefone](../media/content-understanding/pattern-list.png)

<span data-ttu-id="24c8c-131">Para este exemplo, selecione a caixa de seleção **Qualquer dígito de 0-9**.</span><span class="sxs-lookup"><span data-stu-id="24c8c-131">For this sample, select the **Any digit from 0-9** checkbox.</span></span> <span data-ttu-id="24c8c-132">Selecionar isso reconhece todos os valores “0” usado na sua lista de padrões como qualquer dígito de 0 a 9.</span><span class="sxs-lookup"><span data-stu-id="24c8c-132">Selecting this recognizes each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![Qualquer dígito de 0-9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="24c8c-134">Da mesma forma, se você criar uma lista de padrões que inclui caracteres de texto, selecione a caixa de seleção **Qualquer letra de a-z**.</span><span class="sxs-lookup"><span data-stu-id="24c8c-134">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox.</span></span> <span data-ttu-id="24c8c-135">Selecionar isso reconhecer todos os caracteres “a” usados na lista de padrões como qualquer caractere de “a” a “z”.</span><span class="sxs-lookup"><span data-stu-id="24c8c-135">Selecting this recognizes each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="24c8c-136">Por exemplo, se você criar uma lista de padrões **Data** e desejar verificar se um formato de data como \* 1º de janeiro de 2020\* é reconhecido, será necessário:</span><span class="sxs-lookup"><span data-stu-id="24c8c-136">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="24c8c-137">Adicionar *aaa 0, 0000* e *aaa 00, 0000* à sua lista de padrões.</span><span class="sxs-lookup"><span data-stu-id="24c8c-137">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="24c8c-138">Verificar se **Qualquer letra de a-z** também está selecionada.</span><span class="sxs-lookup"><span data-stu-id="24c8c-138">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![Qualquer letra de a-z](../media/content-understanding/any-letter.png)

<span data-ttu-id="24c8c-140">Além disso, se você tiver requisitos de uso de maiúsculas na sua lista de padrões, você tem a opção de selecionar a caixa de seleção **Somente maiúsculas**.</span><span class="sxs-lookup"><span data-stu-id="24c8c-140">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="24c8c-141">Para o exemplo de Data, se for necessário que a primeira letra do mês seja maiúscula, você precisará:</span><span class="sxs-lookup"><span data-stu-id="24c8c-141">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="24c8c-142">Adicionar *Aaa 0, 0000* e *Aaa 00, 0000* à sua lista de padrões.</span><span class="sxs-lookup"><span data-stu-id="24c8c-142">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="24c8c-143">Verificar se **Somente maiúsculas** também está selecionada.</span><span class="sxs-lookup"><span data-stu-id="24c8c-143">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![Somente maiúsculas](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="24c8c-145">Em vez de criar a explicação da lista de padrões manualmente, use a [biblioteca de explicações](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) para usar modelos de lista de padrões predefinidos para lista de padrões comuns, como *data*, *número de telefone*, *número de cartão de crédito*, etc...</span><span class="sxs-lookup"><span data-stu-id="24c8c-145">Instead of manually creating pattern list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use pre-made pattern list templates for common pattern list, such as *date*, *phone number*, *credit card number*, etc..</span></span> 

## <a name="proximity"></a><span data-ttu-id="24c8c-146">Proximidade</span><span class="sxs-lookup"><span data-stu-id="24c8c-146">Proximity</span></span> 

<span data-ttu-id="24c8c-147">O tipo de explicação da proximidade ajuda seu modelo a identificar dados definindo a proximidade dos dados entre si.</span><span class="sxs-lookup"><span data-stu-id="24c8c-147">The proximity explanation type helps your model identify data through defining how close another piece of data is to it.</span></span> <span data-ttu-id="24c8c-148">Por exemplo, em seu modelo, você definiu duas explicações que rotulam o *Número da rua* e *Número de telefone*.</span><span class="sxs-lookup"><span data-stu-id="24c8c-148">For example, in your model, you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="24c8c-149">Você também percebe que os números de telefone do cliente sempre aparecem antes do número da rua.</span><span class="sxs-lookup"><span data-stu-id="24c8c-149">You also notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="24c8c-150">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="24c8c-150">Alex Wilburn</span></span><br>
<span data-ttu-id="24c8c-151">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="24c8c-151">555-555-5555</span></span><br>
<span data-ttu-id="24c8c-152">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="24c8c-152">One Microsoft Way</span></span><br>
<span data-ttu-id="24c8c-153">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="24c8c-153">Redmond, WA 98034</span></span><br>

<span data-ttu-id="24c8c-154">Use a explicação de proximidade para definir a distância da explicação do número de telefone para identificar melhor o número da rua em seus documentos.</span><span class="sxs-lookup"><span data-stu-id="24c8c-154">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![Explicação de proximidade](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="24c8c-156">O que são tokens?</span><span class="sxs-lookup"><span data-stu-id="24c8c-156">What are tokens?</span></span>

<span data-ttu-id="24c8c-157">Para usar o tipo de explicação de proximidade, entenda o que é um token, uma vez que o número de tokens é como a explicação de proximidade mede a distância de uma explicação para a outra.</span><span class="sxs-lookup"><span data-stu-id="24c8c-157">In order to use the proximity explanation type, understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span>  

<span data-ttu-id="24c8c-158">Um token é um intervalo contínuo (sem espaços ou pontuação) de letras e números.</span><span class="sxs-lookup"><span data-stu-id="24c8c-158">A token is a continuous span (no spaces or punctuation) of letters and numbers.</span></span> <span data-ttu-id="24c8c-159">Um espaço NÃO é um token.</span><span class="sxs-lookup"><span data-stu-id="24c8c-159">A space is NOT a token.</span></span> <span data-ttu-id="24c8c-160">Cada caractere de pontuação é um token.</span><span class="sxs-lookup"><span data-stu-id="24c8c-160">Each punctuation character is a token.</span></span> <span data-ttu-id="24c8c-161">A tabela a segui mostra alguns exemplos de como determinar o número de tokens em uma frase.</span><span class="sxs-lookup"><span data-stu-id="24c8c-161">The following table shows some examples of how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="24c8c-162">Frase</span><span class="sxs-lookup"><span data-stu-id="24c8c-162">Phrase</span></span>|<span data-ttu-id="24c8c-163">Número de tokens</span><span class="sxs-lookup"><span data-stu-id="24c8c-163">Number of tokens</span></span>|<span data-ttu-id="24c8c-164">Explicação</span><span class="sxs-lookup"><span data-stu-id="24c8c-164">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="24c8c-165">1</span><span class="sxs-lookup"><span data-stu-id="24c8c-165">1</span></span>|<span data-ttu-id="24c8c-166">Uma única palavra sem pontuação ou espaços.</span><span class="sxs-lookup"><span data-stu-id="24c8c-166">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="24c8c-167">1</span><span class="sxs-lookup"><span data-stu-id="24c8c-167">1</span></span>|<span data-ttu-id="24c8c-168">Um número de localizador de registro.</span><span class="sxs-lookup"><span data-stu-id="24c8c-168">A record locator number.</span></span> <span data-ttu-id="24c8c-169">Pode ter números e letras, mas não tem nenhuma pontuação.</span><span class="sxs-lookup"><span data-stu-id="24c8c-169">It may have numbers and letters, but does not have any punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="24c8c-170">5</span><span class="sxs-lookup"><span data-stu-id="24c8c-170">5</span></span>|<span data-ttu-id="24c8c-171">Um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="24c8c-171">A phone number.</span></span> <span data-ttu-id="24c8c-172">Todos os sinais de pontuação são um único token, então  `425-555-5555` seria 5 tokens:</span><span class="sxs-lookup"><span data-stu-id="24c8c-172">Each punctuation mark is a single token so  `425-555-5555` would be 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="24c8c-173">7</span><span class="sxs-lookup"><span data-stu-id="24c8c-173">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="24c8c-174">Configurar o tipo de explicação de proximidade</span><span class="sxs-lookup"><span data-stu-id="24c8c-174">Configure the proximity explanation type</span></span>

<span data-ttu-id="24c8c-175">Para o exemplo, defina a configuração de proximidade para que possamos definir o intervalo do número de tokens que a explicação do *Número de telefone* entre a explicação do *Número da rua*.</span><span class="sxs-lookup"><span data-stu-id="24c8c-175">For the sample, configure the proximity setting so that we can define the range of the number of tokens the *Phone number* explanation is from the *Street address number* explanation.</span></span>

<span data-ttu-id="24c8c-176">Você deve ver que o intervalo mínimo é “0”, uma vez que não há nenhum token entre o número de telefone e o número da rua.</span><span class="sxs-lookup"><span data-stu-id="24c8c-176">You should see that the minimum range is "0" since there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="24c8c-177">No entanto, alguns números de telefone nos documentos de exemplo são anexados com *(móvel)*.</span><span class="sxs-lookup"><span data-stu-id="24c8c-177">However, some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="24c8c-178">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="24c8c-178">Nestor Wilke</span></span><br>
<span data-ttu-id="24c8c-179">111-111-1111 (móvel)</span><span class="sxs-lookup"><span data-stu-id="24c8c-179">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="24c8c-180">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="24c8c-180">One Microsoft Way</span></span><br>
<span data-ttu-id="24c8c-181">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="24c8c-181">Redmond, WA 98034</span></span><br>

<span data-ttu-id="24c8c-182">Há três tokens em *(móvel)*:</span><span class="sxs-lookup"><span data-stu-id="24c8c-182">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="24c8c-183">Frase</span><span class="sxs-lookup"><span data-stu-id="24c8c-183">Phrase</span></span>|<span data-ttu-id="24c8c-184">Contagem de tokens</span><span class="sxs-lookup"><span data-stu-id="24c8c-184">Token count</span></span>|
|--|--|
|<span data-ttu-id="24c8c-185">(</span><span class="sxs-lookup"><span data-stu-id="24c8c-185">(</span></span>|<span data-ttu-id="24c8c-186">1</span><span class="sxs-lookup"><span data-stu-id="24c8c-186">1</span></span>|
|<span data-ttu-id="24c8c-187">móvel</span><span class="sxs-lookup"><span data-stu-id="24c8c-187">mobile</span></span>|<span data-ttu-id="24c8c-188">2</span><span class="sxs-lookup"><span data-stu-id="24c8c-188">2</span></span>|
|<span data-ttu-id="24c8c-189">)</span><span class="sxs-lookup"><span data-stu-id="24c8c-189">)</span></span>|<span data-ttu-id="24c8c-190">3</span><span class="sxs-lookup"><span data-stu-id="24c8c-190">3</span></span>|

<span data-ttu-id="24c8c-191">Definir a configuração de proximidade para ter um intervalo de 0 a 3.</span><span class="sxs-lookup"><span data-stu-id="24c8c-191">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![Exemplo de proximidade](../media/content-understanding/proximity-example.png)</br>

## <a name="use-explanation-templates"></a><span data-ttu-id="24c8c-193">Usar modelos de explicação</span><span class="sxs-lookup"><span data-stu-id="24c8c-193">Use explanation templates</span></span>

<span data-ttu-id="24c8c-194">Embora seja possível adicionar vários valores da lista de padrões para a explicação, é muito mais fácil usar os modelos predefinidos fornecidos na biblioteca de explicações.</span><span class="sxs-lookup"><span data-stu-id="24c8c-194">While you can manually add various pattern list values for your explanation, it can be much easier to use the pre-created templates provided to you in the explanation library.</span></span>

<span data-ttu-id="24c8c-195">Por exemplo, em vez de adicionar manualmente todas as variações para *Data*, você pode usar o modelo de lista de padrões para *Data*, que já inclui diversos valores de listas de padrões:</span><span class="sxs-lookup"><span data-stu-id="24c8c-195">For example, instead of manually adding all the variations for *Date*, you can use the pattern list template for *Date*, that already includes a number of pattern lists values:</span></span></br>

   ![Biblioteca de explicações](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="24c8c-197">A biblioteca de explicações inclui diversas explicações de lista de padrões usadas com frequência, incluindo:</span><span class="sxs-lookup"><span data-stu-id="24c8c-197">The explanation library includes a number of commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="24c8c-198">Data</span><span class="sxs-lookup"><span data-stu-id="24c8c-198">Date</span></span></br>
- <span data-ttu-id="24c8c-199">Data (numérico)</span><span class="sxs-lookup"><span data-stu-id="24c8c-199">Date (numeric)</span></span></br>
- <span data-ttu-id="24c8c-200">Hora</span><span class="sxs-lookup"><span data-stu-id="24c8c-200">Time</span></span></br>
- <span data-ttu-id="24c8c-201">Número</span><span class="sxs-lookup"><span data-stu-id="24c8c-201">Number</span></span></br>
- <span data-ttu-id="24c8c-202">Número de telefone</span><span class="sxs-lookup"><span data-stu-id="24c8c-202">Phone number</span></span></br>
- <span data-ttu-id="24c8c-203">Código postal</span><span class="sxs-lookup"><span data-stu-id="24c8c-203">Zip code</span></span></br>
- <span data-ttu-id="24c8c-204">Primeira palavra da frase</span><span class="sxs-lookup"><span data-stu-id="24c8c-204">First word of sentence</span></span></br>
- <span data-ttu-id="24c8c-205">Cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="24c8c-205">Credit card</span></span></br>
- <span data-ttu-id="24c8c-206">Cadastro de pessoas físicas</span><span class="sxs-lookup"><span data-stu-id="24c8c-206">Social security number</span></span></br>

<span data-ttu-id="24c8c-207">Observe que a biblioteca de explicações também inclui modelos para explicações de lista de frases, incluindo:</span><span class="sxs-lookup"><span data-stu-id="24c8c-207">Note that the explanation library also includes templates for phrase list explanations as well, including:</span></span>
- <span data-ttu-id="24c8c-208">Fim da frase</span><span class="sxs-lookup"><span data-stu-id="24c8c-208">End of sentence</span></span>
- <span data-ttu-id="24c8c-209">Moeda</span><span class="sxs-lookup"><span data-stu-id="24c8c-209">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="24c8c-210">Para usar um modelo da biblioteca de explicações</span><span class="sxs-lookup"><span data-stu-id="24c8c-210">To use a template from the explanation library</span></span>

1. <span data-ttu-id="24c8c-211">Na seção **Explicações** da página de **Treinamento** do seu modelo, selecione **Novo** e, em seguida, selecione **De um modelo**.</span><span class="sxs-lookup"><span data-stu-id="24c8c-211">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![Criar do modelo](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="24c8c-213">Na página **Modelos de explicação**, selecione a explicação que você deseja usar e, em seguida, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="24c8c-213">On the **Explanation templates** page, select the explanation you want to use, and then select **Add**.</span></span></br>

       ![Selecionar um modelo](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="24c8c-215">As informações do modelo que você selecionou serão exibidas na página **Criar uma explicação**.</span><span class="sxs-lookup"><span data-stu-id="24c8c-215">The information for the template you selected will display on the **Create an explanation** page.</span></span> <span data-ttu-id="24c8c-216">Se necessário, edite o nome da explicação e adicione ou remova itens da lista de padrões.</span><span class="sxs-lookup"><span data-stu-id="24c8c-216">If needed, edit the explanation name, and add or remove items from the pattern list.</span></span> </br> 

   ![Editar modelo](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="24c8c-218">Quando concluir, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="24c8c-218">When finished, select **Save**.</span></span>
