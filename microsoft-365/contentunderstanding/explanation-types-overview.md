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
ms.openlocfilehash: 2d76fec3ee98f7c096c44a2b19b52da9fb70859d
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988757"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="34ae4-103">Introdução aos tipos de explicação</span><span class="sxs-lookup"><span data-stu-id="34ae4-103">Introduction to explanation types</span></span>

<span data-ttu-id="34ae4-104">As explicações são usadas para ajudar a definir as informações que você deseja rotular e extrai para seus modelos de compreensão de documentos no Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="34ae4-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="34ae4-105">Ao criar uma explicação, você precisa selecionar um tipo de explicação.</span><span class="sxs-lookup"><span data-stu-id="34ae4-105">When creating an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="34ae4-106">Este artigo ajuda você a entender os diferentes tipos de explicação e como eles são usados.</span><span class="sxs-lookup"><span data-stu-id="34ae4-106">This article helps you understand the different explanation types and how they are used.</span></span> 

   ![Tipos de explicação](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="34ae4-108">Esses tipos de explicação estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="34ae4-108">These explanation types are available:</span></span>

- <span data-ttu-id="34ae4-109">**Lista de frases** : lista de palavras, frases, números ou outros caracteres que você pode usar no documento ou informações que você está extraindo.</span><span class="sxs-lookup"><span data-stu-id="34ae4-109">**Phrase list** : List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="34ae4-110">Por exemplo, a cadeia de texto **Médico encaminhador** está em todos os documentos de Encaminhamento Médico que você está identificando.</span><span class="sxs-lookup"><span data-stu-id="34ae4-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="34ae4-111">**Lista de padrões** : lista padrões de números, letras ou outros caracteres que você pode usar para identificar as informações que você está extraindo.</span><span class="sxs-lookup"><span data-stu-id="34ae4-111">**Pattern list** : List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="34ae4-112">Por exemplo, você pode extrair o **Número de telefone** do médico encaminhador de todos os documentos de Encaminhamento Médico que você está identificando.</span><span class="sxs-lookup"><span data-stu-id="34ae4-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="34ae4-113">**Proximidade** : descreve a proximidade das explicações entre si. </span><span class="sxs-lookup"><span data-stu-id="34ae4-113">**Proximity** : Describes how close explanations are to each other.</span></span> <span data-ttu-id="34ae4-114">Por exemplo, uma lista de padrões de *número da rua* fica antes da lista de frases de *nome da rua* , sem tokens entre elas (você aprenderá sobre tokens mais adiante neste artigo).</span><span class="sxs-lookup"><span data-stu-id="34ae4-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="34ae4-115">Usar o tipo de proximidade exige que você tenha pelo menos duas explicações em seu modelo, ou a opção será desabilitada.</span><span class="sxs-lookup"><span data-stu-id="34ae4-115">Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="34ae4-116">Lista de frases</span><span class="sxs-lookup"><span data-stu-id="34ae4-116">Phrase list</span></span>

<span data-ttu-id="34ae4-117">Um tipo de explicação de lista de frases geralmente é usado para identificar e classificar um documento por meio do seu modelo.</span><span class="sxs-lookup"><span data-stu-id="34ae4-117">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="34ae4-118">Conforme descrito no exemplo de rótulo *Médico encaminhador* , é uma cadeia de cadeia de palavras, frases, números ou caracteres que está de maneira consistente nos documentos que você está identificando.</span><span class="sxs-lookup"><span data-stu-id="34ae4-118">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="34ae4-119">Embora não seja um requisito, você pode obter um sucesso melhor com a sua explicação se a frase que está capturando estiver localizada em um local consistente no documento.</span><span class="sxs-lookup"><span data-stu-id="34ae4-119">While not a requirement, you can achieve better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="34ae4-120">Por exemplo, o rótulo *Médico encaminhador* pode estar localizado, de maneira consistente, no primeiro parágrafo do documento.</span><span class="sxs-lookup"><span data-stu-id="34ae4-120">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="34ae4-121">Se a diferenciação de maiúsculas e minúsculas for um requisito para a identificação do seu rótulo, usar o tipo de lista de frases permite que você o especifique na sua explicação selecionando a caixa de seleção **Somente maiúsculas**.</span><span class="sxs-lookup"><span data-stu-id="34ae4-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![Diferenciação de maiúsculas e minúsculas](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="34ae4-123">Listas de padrões</span><span class="sxs-lookup"><span data-stu-id="34ae4-123">Pattern lists</span></span>

<span data-ttu-id="34ae4-124">Um tipo de lista de padrões é especialmente útil quando você cria uma explicação que identifica e extrai informações de um documento.</span><span class="sxs-lookup"><span data-stu-id="34ae4-124">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="34ae4-125">Geralmente, é apresentado em formatos diferentes, como datas, números de telefone e de cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="34ae4-125">It is typically presented in different formats, such as dates, phone numbers, and credit card numbers.</span></span> <span data-ttu-id="34ae4-126">Por exemplo, um data pode ser exibida em diversos formatos (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1º de janeiro de 2020, etc.).</span><span class="sxs-lookup"><span data-stu-id="34ae4-126">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="34ae4-127">A definição de uma lista de padrões torna suas explicações mais eficientes, capturando todas as variações possíveis nos dados que você está tentando identificar e extrair.</span><span class="sxs-lookup"><span data-stu-id="34ae4-127">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="34ae4-128">Para obter o exemplo de **Número de telefone** , extraia o número de telefone de cada médico encaminhador de todos os documentos de Encaminhamento Médico identificados pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="34ae4-128">For the **Phone number** example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="34ae4-129">Ao criar a explicação, selecione o tipo de lista Padrão para permitir que os diferentes formados esperados sejam retornados.</span><span class="sxs-lookup"><span data-stu-id="34ae4-129">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![Lista de padrões de número de telefone](../media/content-understanding/pattern-list.png)

<span data-ttu-id="34ae4-131">Para este exemplo, selecione a caixa de seleção **Qualquer dígito de 0-9** para reconhecer cada valor "0" usado em sua lista de padrões como qualquer dígito de 0 a 9.</span><span class="sxs-lookup"><span data-stu-id="34ae4-131">For this example, select the **Any digit from 0-9** checkbox to recognize each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![Qualquer dígito de 0-9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="34ae4-133">Da mesma forma, se você criar uma lista de padrões que inclui caracteres de texto, selecione a caixa de seleção **Qualquer letra de a-z** para reconhecer cada caractere "a" usado na lista de padrões como qualquer caractere de "a" a "z".</span><span class="sxs-lookup"><span data-stu-id="34ae4-133">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="34ae4-134">Por exemplo, se você criar uma lista de padrões **Data** e desejar verificar se um formato de data como *1º de janeiro de 2020* é reconhecido, será necessário:</span><span class="sxs-lookup"><span data-stu-id="34ae4-134">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="34ae4-135">Adicionar *aaa 0, 0000* e *aaa 00, 0000* à sua lista de padrões.</span><span class="sxs-lookup"><span data-stu-id="34ae4-135">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="34ae4-136">Verificar se **Qualquer letra de a-z** também está selecionada.</span><span class="sxs-lookup"><span data-stu-id="34ae4-136">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![Qualquer letra de a-z](../media/content-understanding/any-letter.png)

<span data-ttu-id="34ae4-138">Além disso, se você tiver requisitos de uso de maiúsculas na sua lista de padrões, você tem a opção de selecionar a caixa de seleção **Somente maiúsculas**.</span><span class="sxs-lookup"><span data-stu-id="34ae4-138">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="34ae4-139">Para o exemplo de Data, se for necessário que a primeira letra do mês seja maiúscula, você precisará:</span><span class="sxs-lookup"><span data-stu-id="34ae4-139">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="34ae4-140">Adicionar *Aaa 0, 0000* e *Aaa 00, 0000* à sua lista de padrões.</span><span class="sxs-lookup"><span data-stu-id="34ae4-140">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="34ae4-141">Verificar se **Somente maiúsculas** também está selecionada.</span><span class="sxs-lookup"><span data-stu-id="34ae4-141">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![Somente maiúsculas](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="34ae4-143">Em vez de criar uma explicação da lista de padrões manualmente, use a [biblioteca de explicações](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) para usar modelos de lista de padrões de uma lista de padrões comuns, como *data* , *número de telefone* , *número de cartão de crédito* , etc.</span><span class="sxs-lookup"><span data-stu-id="34ae4-143">Instead of manually creating a pattern list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use pattern list templates for a common pattern list, such as *date* , *phone number* , *credit card number* , etc.</span></span>

## <a name="proximity"></a><span data-ttu-id="34ae4-144">Proximidade</span><span class="sxs-lookup"><span data-stu-id="34ae4-144">Proximity</span></span> 

<span data-ttu-id="34ae4-145">O tipo de explicação da proximidade ajuda seu modelo a identificar dados definindo a proximidade dos dados entre si.</span><span class="sxs-lookup"><span data-stu-id="34ae4-145">The proximity explanation type helps your model identify data by defining how close another piece of data is to it.</span></span> <span data-ttu-id="34ae4-146">Por exemplo, em seu modelo, você definiu duas explicações que rotulam o *Número da rua* e *Número de telefone* do cliente.</span><span class="sxs-lookup"><span data-stu-id="34ae4-146">For example, in your model say you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="34ae4-147">Observe que os números de telefone do cliente sempre aparecem antes do número da rua.</span><span class="sxs-lookup"><span data-stu-id="34ae4-147">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="34ae4-148">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="34ae4-148">Alex Wilburn</span></span><br>
<span data-ttu-id="34ae4-149">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="34ae4-149">555-555-5555</span></span><br>
<span data-ttu-id="34ae4-150">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="34ae4-150">One Microsoft Way</span></span><br>
<span data-ttu-id="34ae4-151">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="34ae4-151">Redmond, WA 98034</span></span><br>

<span data-ttu-id="34ae4-152">Use a explicação de proximidade para definir a distância da explicação do número de telefone para identificar melhor o número da rua em seus documentos.</span><span class="sxs-lookup"><span data-stu-id="34ae4-152">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![Explicação de proximidade](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="34ae4-154">O que são tokens?</span><span class="sxs-lookup"><span data-stu-id="34ae4-154">What are tokens?</span></span>

<span data-ttu-id="34ae4-155">Para usar o tipo de explicação de proximidade, você precisa entender o que é um token, uma vez que o número de tokens é como a explicação de proximidade mede a distância de uma explicação para a outra.</span><span class="sxs-lookup"><span data-stu-id="34ae4-155">In order to use the proximity explanation type, you need to understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span> <span data-ttu-id="34ae4-156">Um token é um intervalo contínuo (sem incluir espaços ou pontuação) de letras e números.</span><span class="sxs-lookup"><span data-stu-id="34ae4-156">A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="34ae4-157">A tabela a seguir mostra exemplos de como determinar o número de tokens em uma frase.</span><span class="sxs-lookup"><span data-stu-id="34ae4-157">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="34ae4-158">Frase</span><span class="sxs-lookup"><span data-stu-id="34ae4-158">Phrase</span></span>|<span data-ttu-id="34ae4-159">Número de tokens</span><span class="sxs-lookup"><span data-stu-id="34ae4-159">Number of tokens</span></span>|<span data-ttu-id="34ae4-160">Explicação</span><span class="sxs-lookup"><span data-stu-id="34ae4-160">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="34ae4-161">1</span><span class="sxs-lookup"><span data-stu-id="34ae4-161">1</span></span>|<span data-ttu-id="34ae4-162">Uma única palavra sem pontuação ou espaços.</span><span class="sxs-lookup"><span data-stu-id="34ae4-162">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="34ae4-163">1</span><span class="sxs-lookup"><span data-stu-id="34ae4-163">1</span></span>|<span data-ttu-id="34ae4-164">Um número de localizador de registro.</span><span class="sxs-lookup"><span data-stu-id="34ae4-164">A record locator number.</span></span> <span data-ttu-id="34ae4-165">Pode incluir números e letras, mas não tem pontuação.</span><span class="sxs-lookup"><span data-stu-id="34ae4-165">It may include numbers and letters, but does not have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="34ae4-166">5</span><span class="sxs-lookup"><span data-stu-id="34ae4-166">5</span></span>|<span data-ttu-id="34ae4-167">Um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="34ae4-167">A phone number.</span></span> <span data-ttu-id="34ae4-168">Cada sinal de pontuação é um único token, assim `425-555-5555` equivale a 5 tokens:</span><span class="sxs-lookup"><span data-stu-id="34ae4-168">Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="34ae4-169">7</span><span class="sxs-lookup"><span data-stu-id="34ae4-169">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="34ae4-170">Configurar o tipo de explicação de proximidade</span><span class="sxs-lookup"><span data-stu-id="34ae4-170">Configure the proximity explanation type</span></span>

<span data-ttu-id="34ae4-171">Para o exemplo, defina a configuração de proximidade para definir o intervalo do número de tokens na explicação do *Número de telefone* da explicação do *Número da rua*.</span><span class="sxs-lookup"><span data-stu-id="34ae4-171">For the example, configure the proximity setting to define the range of the number of tokens in the *Phone number* explanation from the *Street address number* explanation.</span></span> <span data-ttu-id="34ae4-172">Observe que o intervalo mínimo é “0”, pois não há nenhum token entre o número de telefone e o número da rua.</span><span class="sxs-lookup"><span data-stu-id="34ae4-172">Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="34ae4-173">No entanto, alguns números de telefone nos documentos de exemplo são acrescentados no *(telefone)*.</span><span class="sxs-lookup"><span data-stu-id="34ae4-173">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="34ae4-174">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="34ae4-174">Nestor Wilke</span></span><br>
<span data-ttu-id="34ae4-175">111-111-1111 (móvel)</span><span class="sxs-lookup"><span data-stu-id="34ae4-175">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="34ae4-176">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="34ae4-176">One Microsoft Way</span></span><br>
<span data-ttu-id="34ae4-177">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="34ae4-177">Redmond, WA 98034</span></span><br>

<span data-ttu-id="34ae4-178">Há três tokens em *(móvel)* :</span><span class="sxs-lookup"><span data-stu-id="34ae4-178">There are three tokens in *(mobile)* :</span></span>

|<span data-ttu-id="34ae4-179">Frase</span><span class="sxs-lookup"><span data-stu-id="34ae4-179">Phrase</span></span>|<span data-ttu-id="34ae4-180">Contagem de tokens</span><span class="sxs-lookup"><span data-stu-id="34ae4-180">Token count</span></span>|
|--|--|
|<span data-ttu-id="34ae4-181">(</span><span class="sxs-lookup"><span data-stu-id="34ae4-181">(</span></span>|<span data-ttu-id="34ae4-182">1</span><span class="sxs-lookup"><span data-stu-id="34ae4-182">1</span></span>|
|<span data-ttu-id="34ae4-183">móvel</span><span class="sxs-lookup"><span data-stu-id="34ae4-183">mobile</span></span>|<span data-ttu-id="34ae4-184">2</span><span class="sxs-lookup"><span data-stu-id="34ae4-184">2</span></span>|
|<span data-ttu-id="34ae4-185">)</span><span class="sxs-lookup"><span data-stu-id="34ae4-185">)</span></span>|<span data-ttu-id="34ae4-186">3</span><span class="sxs-lookup"><span data-stu-id="34ae4-186">3</span></span>|

<span data-ttu-id="34ae4-187">Definir a configuração de proximidade para ter um intervalo de 0 a 3.</span><span class="sxs-lookup"><span data-stu-id="34ae4-187">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![Exemplo de proximidade](../media/content-understanding/proximity-example.png)</br>

## <a name="use-explanation-templates"></a><span data-ttu-id="34ae4-189">Usar modelos de explicação</span><span class="sxs-lookup"><span data-stu-id="34ae4-189">Use explanation templates</span></span>

<span data-ttu-id="34ae4-190">Embora seja possível adicionar vários valores da lista de padrões à sua explicação, pode ser mais fácil usar os modelos fornecidos na biblioteca de explicações.</span><span class="sxs-lookup"><span data-stu-id="34ae4-190">While you can manually add various pattern list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="34ae4-191">Por exemplo, em vez de adicionar manualmente todas as variações para *Data* , você pode usar o modelo de lista de padrões para *Data* , pois já inclui diversos valores de listas de padrões:</span><span class="sxs-lookup"><span data-stu-id="34ae4-191">For example, instead of manually adding all the variations for *Date* , you can use the pattern list template for *Date* as it already includes a number of pattern lists values:</span></span></br>

   ![Biblioteca de explicações](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="34ae4-193">A biblioteca de explicações inclui explicações de lista de padrões usadas com frequência, incluindo:</span><span class="sxs-lookup"><span data-stu-id="34ae4-193">The explanation library includes commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="34ae4-194">Data</span><span class="sxs-lookup"><span data-stu-id="34ae4-194">Date</span></span></br>
- <span data-ttu-id="34ae4-195">Data (numérico)</span><span class="sxs-lookup"><span data-stu-id="34ae4-195">Date (numeric)</span></span></br>
- <span data-ttu-id="34ae4-196">Hora</span><span class="sxs-lookup"><span data-stu-id="34ae4-196">Time</span></span></br>
- <span data-ttu-id="34ae4-197">Número</span><span class="sxs-lookup"><span data-stu-id="34ae4-197">Number</span></span></br>
- <span data-ttu-id="34ae4-198">Número de telefone</span><span class="sxs-lookup"><span data-stu-id="34ae4-198">Phone number</span></span></br>
- <span data-ttu-id="34ae4-199">Código postal</span><span class="sxs-lookup"><span data-stu-id="34ae4-199">Zip code</span></span></br>
- <span data-ttu-id="34ae4-200">Primeira palavra da frase</span><span class="sxs-lookup"><span data-stu-id="34ae4-200">First word of sentence</span></span></br>
- <span data-ttu-id="34ae4-201">Cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="34ae4-201">Credit card</span></span></br>
- <span data-ttu-id="34ae4-202">Número do seguro social</span><span class="sxs-lookup"><span data-stu-id="34ae4-202">Social security number</span></span></br>

<span data-ttu-id="34ae4-203">Observe que a biblioteca de explicações também inclui modelos de explicações de lista de frases:</span><span class="sxs-lookup"><span data-stu-id="34ae4-203">Note that the explanation library also includes templates for phrase list explanations:</span></span>
- <span data-ttu-id="34ae4-204">Fim da frase</span><span class="sxs-lookup"><span data-stu-id="34ae4-204">End of sentence</span></span>
- <span data-ttu-id="34ae4-205">Moeda</span><span class="sxs-lookup"><span data-stu-id="34ae4-205">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="34ae4-206">Para usar um modelo da biblioteca de explicações</span><span class="sxs-lookup"><span data-stu-id="34ae4-206">To use a template from the explanation library</span></span>

1. <span data-ttu-id="34ae4-207">Na seção **Explicações** da página de **Treinamento** do seu modelo, selecione **Novo** e, em seguida, selecione **De um modelo**.</span><span class="sxs-lookup"><span data-stu-id="34ae4-207">From the **Explanations** section of your model's **Train** page, select **New** , then select **From a template**.</span></span></br>

   ![Criar do modelo](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="34ae4-209">Na página **Modelos de explicação** , selecione a explicação que você deseja usar e, em seguida, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="34ae4-209">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span></br>

       ![Selecionar um modelo](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="34ae4-211">As informações do modelo que você selecionou são exibidas na página **Criar uma explicação**.</span><span class="sxs-lookup"><span data-stu-id="34ae4-211">The information for the template you selected displays on the **Create an explanation** page.</span></span> <span data-ttu-id="34ae4-212">Se necessário, edite o nome da explicação e adicione ou remova itens da lista de padrões.</span><span class="sxs-lookup"><span data-stu-id="34ae4-212">If needed, edit the explanation name and add or remove items from the pattern list.</span></span> </br> 

   ![Editar modelo](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="34ae4-214">Quando concluir, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="34ae4-214">When finished, select **Save**.</span></span>
