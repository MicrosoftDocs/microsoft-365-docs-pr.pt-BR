---
title: Tipos de explicação
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Saiba mais sobre tipos de explicação no Microsoft SharePoint Syntex
ms.openlocfilehash: a5404230a59d1740a2b855527229a7aca92195a8
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604400"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="013d2-103">Introdução aos tipos de explicação</span><span class="sxs-lookup"><span data-stu-id="013d2-103">Introduction to explanation types</span></span>

<span data-ttu-id="013d2-104">As explicações são usadas para ajudar a definir as informações que você deseja rotular e extrai para seus modelos de compreensão de documentos no Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="013d2-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="013d2-105">Ao criar uma explicação, você precisa selecionar um tipo de explicação.</span><span class="sxs-lookup"><span data-stu-id="013d2-105">When creating an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="013d2-106">Este artigo ajuda você a entender os diferentes tipos de explicação e como eles são usados.</span><span class="sxs-lookup"><span data-stu-id="013d2-106">This article helps you understand the different explanation types and how they are used.</span></span> 

![Tipos de explicação](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="013d2-108">Esses tipos de explicação estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="013d2-108">These explanation types are available:</span></span>

- <span data-ttu-id="013d2-109">**Lista de frases**: lista de palavras, frases, números ou outros caracteres que você pode usar no documento ou informações que você está extraindo.</span><span class="sxs-lookup"><span data-stu-id="013d2-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="013d2-110">Por exemplo, a cadeia de texto **Médico encaminhador** está em todos os documentos de Encaminhamento Médico que você está identificando.</span><span class="sxs-lookup"><span data-stu-id="013d2-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span> <span data-ttu-id="013d2-111">Ou o **Número de telefone** do médico de referência de todos os documentos de referência médica que você está identificando.</span><span class="sxs-lookup"><span data-stu-id="013d2-111">Or the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span>

- <span data-ttu-id="013d2-112">**Proximidade**: Descreve como as explicações são próximas umas das outras.</span><span class="sxs-lookup"><span data-stu-id="013d2-112">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="013d2-113">Por exemplo, um *número da rua* lista de frases vai logo antes do *nome da rua* lista de frases, sem tokens entre eles (você aprenderá sobre tokens posteriormente neste artigo).</span><span class="sxs-lookup"><span data-stu-id="013d2-113">For example, a *street number* phrase list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="013d2-114">Usar o tipo de proximidade exige que você tenha pelo menos duas explicações em seu modelo, ou a opção será desabilitada.</span><span class="sxs-lookup"><span data-stu-id="013d2-114">Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="013d2-115">Lista de frases</span><span class="sxs-lookup"><span data-stu-id="013d2-115">Phrase list</span></span>

<span data-ttu-id="013d2-116">Um tipo de explicação de lista de frases geralmente é usado para identificar e classificar um documento por meio do seu modelo.</span><span class="sxs-lookup"><span data-stu-id="013d2-116">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="013d2-117">Conforme descrito no exemplo de rótulo *Médico encaminhador*, é uma cadeia de cadeia de palavras, frases, números ou caracteres que está de maneira consistente nos documentos que você está identificando.</span><span class="sxs-lookup"><span data-stu-id="013d2-117">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="013d2-118">Embora não seja um requisito, você pode obter um sucesso melhor com a sua explicação se a frase que está capturando estiver localizada em um local consistente no documento.</span><span class="sxs-lookup"><span data-stu-id="013d2-118">While not a requirement, you can achieve better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="013d2-119">Por exemplo, o rótulo *Médico encaminhador* pode estar localizado, de maneira consistente, no primeiro parágrafo do documento.</span><span class="sxs-lookup"><span data-stu-id="013d2-119">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span> <span data-ttu-id="013d2-120">Você também pode usar o **[Configurar onde as frases ocorrem no documento](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** configuração avançada para selecionar áreas específicas onde a frase está localizada, especialmente se houver uma chance de que a frase possa ocorrer em vários locais em seu documento.</span><span class="sxs-lookup"><span data-stu-id="013d2-120">You can also use the **[Configure where phrases occur in the document](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** advanced setting to select specific areas where the phrase is located, especially if there is a chance that the phrase might occur in multiple locations in your document.</span></span>

<span data-ttu-id="013d2-121">Se a diferenciação de maiúsculas e minúsculas for um requisito para a identificação do seu rótulo, usar o tipo de lista de frases permite que você o especifique na sua explicação selecionando a caixa de seleção **Somente maiúsculas**.</span><span class="sxs-lookup"><span data-stu-id="013d2-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

![Diferenciação de maiúsculas e minúsculas](../media/content-understanding/case-sensitivity.png) 

<span data-ttu-id="013d2-123">Um tipo de frase é especialmente útil quando você cria uma explicação que identifica e extrai informações em diferentes formatos, como datas, números de telefone e números de cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="013d2-123">A phrase type is especially useful when you create an explanation that identifies and extracts information in different formats, such as dates, phone numbers, and credit card numbers.</span></span> <span data-ttu-id="013d2-124">Por exemplo, uma data pode ser exibida em vários formatos diferentes (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span><span class="sxs-lookup"><span data-stu-id="013d2-124">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="013d2-125">Definir uma lista de frases torna sua explicação mais eficiente, capturando quaisquer variações possíveis nos dados que você está tentando identificar e extrair.</span><span class="sxs-lookup"><span data-stu-id="013d2-125">Defining a phrase list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="013d2-126">Para o **Número de telefone** Por exemplo, você extrai o número de telefone de cada médico de referência de todos os documentos de referência médica que o modelo identifica.</span><span class="sxs-lookup"><span data-stu-id="013d2-126">For the **Phone number** example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="013d2-127">Ao criar a explicação, digite os diferentes formatos que um número de telefone pode exibir em seu documento para que você possa capturar possíveis variações.</span><span class="sxs-lookup"><span data-stu-id="013d2-127">When you create the explanation, type the different formats a phone number might display in your document so that you are able to capture possible variations.</span></span> 

![Padrões de frase de número de telefone](../media/content-understanding/pattern-list.png)

<span data-ttu-id="013d2-129">Para este exemplo, em **Configurações avançadas** selecione os **Qualquer dígito de 0-9** caixa de seleção para reconhecer cada valor "0" usado em sua lista de frases como qualquer dígito de 0 a 9.</span><span class="sxs-lookup"><span data-stu-id="013d2-129">For this example, in **Advanced Settings** select the **Any digit from 0-9** checkbox to recognize each "0" value used in your phrase list to be any digit from 0 through 9.</span></span>

![Qualquer dígito de 0-9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="013d2-131">Da mesma forma, se você criar uma lista de frases que inclua caracteres de texto, selecione o **Qualquer letra de a-z** caixa de seleção para reconhecer cada caractere "a" usado na lista de frases como qualquer caractere de "a" a "z".</span><span class="sxs-lookup"><span data-stu-id="013d2-131">Similarly, if you create a phrase list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the phrase list to be any character from "a" to "z".</span></span>

<span data-ttu-id="013d2-132">Por exemplo, se você criar um **Data** lista de frases e você deseja ter certeza de que um formato de data como *Jan 1, 2020* é reconhecido, você precisa:</span><span class="sxs-lookup"><span data-stu-id="013d2-132">For example, if you create a **Date** phrase list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="013d2-133">Adicionar *aaa 0, 0000* e *aaa 00, 0000* para sua lista de frases.</span><span class="sxs-lookup"><span data-stu-id="013d2-133">Add *aaa 0, 0000* and *aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="013d2-134">Verificar se **Qualquer letra de a-z** também está selecionada.</span><span class="sxs-lookup"><span data-stu-id="013d2-134">Make sure that **Any letter from a-z** is also selected.</span></span>

![Qualquer letra de a-z](../media/content-understanding/any-letter.png)

<span data-ttu-id="013d2-136">Além disso, se houver requisitos de letras maiúsculas em sua lista de frases, você terá a opção de selecionar o **Apenas letras maiúsculas exatas** caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="013d2-136">Additionally, if you have capitalization requirements in your phrase list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="013d2-137">Para o exemplo de data, se você quiser que a primeira letra do mês seja maiúscula, você precisa:</span><span class="sxs-lookup"><span data-stu-id="013d2-137">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="013d2-138">Adicionar *Aaa 0, 0000* and *Aaa 00, 0000* para sua lista de frases.</span><span class="sxs-lookup"><span data-stu-id="013d2-138">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="013d2-139">Verificar se **Somente maiúsculas** também está selecionada.</span><span class="sxs-lookup"><span data-stu-id="013d2-139">Make sure that **Only exact capitalization** is also selected.</span></span>

![Somente maiúsculas](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="013d2-141">Em vez de criar manualmente uma explicação de lista de frases, use o [biblioteca de explicação](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) para usar modelos de lista de frases para uma lista de frases comum, como *data*, *número de telefone*, *número do cartão de crédito*, etc.</span><span class="sxs-lookup"><span data-stu-id="013d2-141">Instead of manually creating a phrase list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use phrase list templates for a common phrase list, such as *date*, *phone number*, *credit card number*, etc.</span></span>

## <a name="proximity"></a><span data-ttu-id="013d2-142">Proximidade</span><span class="sxs-lookup"><span data-stu-id="013d2-142">Proximity</span></span> 

<span data-ttu-id="013d2-143">O tipo de explicação da proximidade ajuda seu modelo a identificar dados definindo a proximidade dos dados entre si.</span><span class="sxs-lookup"><span data-stu-id="013d2-143">The proximity explanation type helps your model identify data by defining how close another piece of data is to it.</span></span> <span data-ttu-id="013d2-144">Por exemplo, em seu modelo, você definiu duas explicações que rotulam o *Número da rua* e *Número de telefone* do cliente.</span><span class="sxs-lookup"><span data-stu-id="013d2-144">For example, in your model say you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="013d2-145">Observe que os números de telefone do cliente sempre aparecem antes do número da rua.</span><span class="sxs-lookup"><span data-stu-id="013d2-145">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="013d2-146">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="013d2-146">Alex Wilburn</span></span><br>
<span data-ttu-id="013d2-147">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="013d2-147">555-555-5555</span></span><br>
<span data-ttu-id="013d2-148">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="013d2-148">One Microsoft Way</span></span><br>
<span data-ttu-id="013d2-149">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="013d2-149">Redmond, WA 98034</span></span><br>

<span data-ttu-id="013d2-150">Use a explicação de proximidade para definir a distância da explicação do número de telefone para identificar melhor o número da rua em seus documentos.</span><span class="sxs-lookup"><span data-stu-id="013d2-150">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

![Explicação de proximidade](../media/content-understanding/proximity.png)

#### <a name="what-are-tokens"></a><span data-ttu-id="013d2-152">O que são tokens?</span><span class="sxs-lookup"><span data-stu-id="013d2-152">What are tokens?</span></span>

<span data-ttu-id="013d2-153">Para usar o tipo de explicação de proximidade, você precisa entender o que é um token, uma vez que o número de tokens é como a explicação de proximidade mede a distância de uma explicação para a outra.</span><span class="sxs-lookup"><span data-stu-id="013d2-153">In order to use the proximity explanation type, you need to understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span> <span data-ttu-id="013d2-154">Um token é um intervalo contínuo (sem incluir espaços ou pontuação) de letras e números.</span><span class="sxs-lookup"><span data-stu-id="013d2-154">A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="013d2-155">A tabela a seguir mostra exemplos de como determinar o número de tokens em uma frase.</span><span class="sxs-lookup"><span data-stu-id="013d2-155">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="013d2-156">Frase</span><span class="sxs-lookup"><span data-stu-id="013d2-156">Phrase</span></span>|<span data-ttu-id="013d2-157">Número de tokens</span><span class="sxs-lookup"><span data-stu-id="013d2-157">Number of tokens</span></span>|<span data-ttu-id="013d2-158">Explicação</span><span class="sxs-lookup"><span data-stu-id="013d2-158">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="013d2-159">1</span><span class="sxs-lookup"><span data-stu-id="013d2-159">1</span></span>|<span data-ttu-id="013d2-160">Uma única palavra sem pontuação ou espaços.</span><span class="sxs-lookup"><span data-stu-id="013d2-160">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="013d2-161">1</span><span class="sxs-lookup"><span data-stu-id="013d2-161">1</span></span>|<span data-ttu-id="013d2-162">Um número de localizador de registro.</span><span class="sxs-lookup"><span data-stu-id="013d2-162">A record locator number.</span></span> <span data-ttu-id="013d2-163">Pode incluir números e letras, mas não tem pontuação.</span><span class="sxs-lookup"><span data-stu-id="013d2-163">It may include numbers and letters, but does not have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="013d2-164">5</span><span class="sxs-lookup"><span data-stu-id="013d2-164">5</span></span>|<span data-ttu-id="013d2-165">Um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="013d2-165">A phone number.</span></span> <span data-ttu-id="013d2-166">Cada sinal de pontuação é um único token, assim `425-555-5555` equivale a 5 tokens:</span><span class="sxs-lookup"><span data-stu-id="013d2-166">Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="013d2-167">7</span><span class="sxs-lookup"><span data-stu-id="013d2-167">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="013d2-168">Configurar o tipo de explicação de proximidade</span><span class="sxs-lookup"><span data-stu-id="013d2-168">Configure the proximity explanation type</span></span>

<span data-ttu-id="013d2-169">Para o exemplo, defina a configuração de proximidade para definir o intervalo do número de tokens na explicação do *Número de telefone* da explicação do *Número da rua*.</span><span class="sxs-lookup"><span data-stu-id="013d2-169">For the example, configure the proximity setting to define the range of the number of tokens in the *Phone number* explanation from the *Street address number* explanation.</span></span> <span data-ttu-id="013d2-170">Observe que o intervalo mínimo é “0”, pois não há nenhum token entre o número de telefone e o número da rua.</span><span class="sxs-lookup"><span data-stu-id="013d2-170">Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="013d2-171">No entanto, alguns números de telefone nos documentos de exemplo são acrescentados no *(telefone)*.</span><span class="sxs-lookup"><span data-stu-id="013d2-171">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="013d2-172">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="013d2-172">Nestor Wilke</span></span><br>
<span data-ttu-id="013d2-173">111-111-1111 (móvel)</span><span class="sxs-lookup"><span data-stu-id="013d2-173">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="013d2-174">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="013d2-174">One Microsoft Way</span></span><br>
<span data-ttu-id="013d2-175">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="013d2-175">Redmond, WA 98034</span></span><br>

<span data-ttu-id="013d2-176">Há três tokens em *(móvel)*:</span><span class="sxs-lookup"><span data-stu-id="013d2-176">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="013d2-177">Frase</span><span class="sxs-lookup"><span data-stu-id="013d2-177">Phrase</span></span>|<span data-ttu-id="013d2-178">Contagem de tokens</span><span class="sxs-lookup"><span data-stu-id="013d2-178">Token count</span></span>|
|--|--|
|<span data-ttu-id="013d2-179">(</span><span class="sxs-lookup"><span data-stu-id="013d2-179">(</span></span>|<span data-ttu-id="013d2-180">1</span><span class="sxs-lookup"><span data-stu-id="013d2-180">1</span></span>|
|<span data-ttu-id="013d2-181">móvel</span><span class="sxs-lookup"><span data-stu-id="013d2-181">mobile</span></span>|<span data-ttu-id="013d2-182">2</span><span class="sxs-lookup"><span data-stu-id="013d2-182">2</span></span>|
|<span data-ttu-id="013d2-183">)</span><span class="sxs-lookup"><span data-stu-id="013d2-183">)</span></span>|<span data-ttu-id="013d2-184">3</span><span class="sxs-lookup"><span data-stu-id="013d2-184">3</span></span>|

<span data-ttu-id="013d2-185">Definir a configuração de proximidade para ter um intervalo de 0 a 3.</span><span class="sxs-lookup"><span data-stu-id="013d2-185">Configure the proximity setting to have a range of 0 through 3.</span></span>

![Exemplo de proximidade](../media/content-understanding/proximity-example.png)


## <a name="configure-where-phrases-occur-in-the-document"></a><span data-ttu-id="013d2-187">Configurar onde as frases ocorrem no documento</span><span class="sxs-lookup"><span data-stu-id="013d2-187">Configure where phrases occur in the document</span></span>

<span data-ttu-id="013d2-188">Quando você cria uma explicação, por padrão, todo o documento é pesquisado pela frase que você está tentando extrair.</span><span class="sxs-lookup"><span data-stu-id="013d2-188">When you create an explanation, by default the entire document is searched for the phrase you are trying to extract.</span></span> <span data-ttu-id="013d2-189">No entanto, você pode usar a configuração avançada **Onde essas frases ocorrem** para ajudar a isolar um local específico do documento em que ocorre uma frase.</span><span class="sxs-lookup"><span data-stu-id="013d2-189">However, you can use the **Where these phrases occur** advanced setting to help in isolating a specific location in the document that a phrase occurs.</span></span> <span data-ttu-id="013d2-190">Isso é útil em situações em que instâncias semelhantes de uma frase podem aparecer em outro lugar no documento e você deseja ter certeza de que a correta está selecionada.</span><span class="sxs-lookup"><span data-stu-id="013d2-190">This is useful in situations where similar instances of a phrase might appear somewhere else in the document, and you want to make sure that the correct one is selected.</span></span> <span data-ttu-id="013d2-191">Ao se referir ao nosso exemplo de documento de Referência Médica, o **Médico Encaminhador** sempre é mencionado no primeiro parágrafo do documento.</span><span class="sxs-lookup"><span data-stu-id="013d2-191">Referring to our Medical Referral document example, the **Referring Doctor** is always mentioned in the first paragraph of the document.</span></span> <span data-ttu-id="013d2-192">Com a configuração \*\* Onde essas frases ocorrem, neste exemplo, você pode configurar sua explicação para pesquisar esse rótulo apenas na seção inicial do documento ou em qualquer outro local em que possa ocorrer.</span><span class="sxs-lookup"><span data-stu-id="013d2-192">With the \*\*Where these phrases occur setting, in this example you can configure your explanation to search for this label only in the beginning section of the document, or any other location in which it might occur.</span></span>

![Configuração de onde essas frases ocorrem](../media/content-understanding/phrase-location.png)

<span data-ttu-id="013d2-194">Você pode escolher uma das três opções para esta configuração:</span><span class="sxs-lookup"><span data-stu-id="013d2-194">You can choose the following options for this setting:</span></span>

- <span data-ttu-id="013d2-195">Em qualquer lugar no arquivo: o documento inteiro é pesquisado pela frase.</span><span class="sxs-lookup"><span data-stu-id="013d2-195">Anywhere in the file: The entire document is searched for the phrase.</span></span>

- <span data-ttu-id="013d2-196">Início do arquivo: o documento é pesquisado do início até o local da frase.</span><span class="sxs-lookup"><span data-stu-id="013d2-196">Beginning of the file:  The document is searched from the beginning to the phrase location.</span></span>

   ![Início do arquivo](../media/content-understanding/beginning-of-file.png)

    <span data-ttu-id="013d2-198">No visualizador, você pode ajustar manualmente a caixa de seleção para incluir o local onde a fase ocorre.</span><span class="sxs-lookup"><span data-stu-id="013d2-198">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="013d2-199">O valor **Posição final** será atualizado para mostrar o número de tokens que sua área selecionada inclui.</span><span class="sxs-lookup"><span data-stu-id="013d2-199">The **End position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="013d2-200">Observe que você também pode atualizar o valor da Posição final para ajustar a área selecionada.</span><span class="sxs-lookup"><span data-stu-id="013d2-200">Note that you can update the End position value as well to adjust the selected area.</span></span>

   ![Início da caixa de posição do arquivo](../media/content-understanding/beginning-box.png)

- <span data-ttu-id="013d2-202">Fim do arquivo: O documento é pesquisado desde o final até a localização da frase.</span><span class="sxs-lookup"><span data-stu-id="013d2-202">End of the file:  The document is searched from the end to the phrase location.</span></span>

   ![Fim do arquivo](../media/content-understanding/end-of-file.png)

    <span data-ttu-id="013d2-204">No visualizador, você pode ajustar manualmente a caixa de seleção para incluir o local onde a fase ocorre.</span><span class="sxs-lookup"><span data-stu-id="013d2-204">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="013d2-205">O valor **Posição incial** será atualizado para mostrar o número de tokens que sua área selecionada inclui.</span><span class="sxs-lookup"><span data-stu-id="013d2-205">The **Starting position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="013d2-206">Observe que você também pode atualizar o valor da Posição inicial para ajustar a área selecionada.</span><span class="sxs-lookup"><span data-stu-id="013d2-206">Note that you can update the Starting position value as well to adjust the selected area.</span></span>

   ![Fim da caixa de fim do arquivo](../media/content-understanding/end-box.png)

- <span data-ttu-id="013d2-208">Intervalo personalizado: O documento é pesquisado em um intervalo especificado dentro dele para a localização da frase.</span><span class="sxs-lookup"><span data-stu-id="013d2-208">Custom range:  The document is searched in a specified range within the it for the phrase location.</span></span>

   ![Intervalo personalizado](../media/content-understanding/custom-file.png)

    <span data-ttu-id="013d2-210">No visualizador, você pode ajustar manualmente a caixa de seleção para incluir o local onde a fase ocorre.</span><span class="sxs-lookup"><span data-stu-id="013d2-210">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="013d2-211">Para essa configuração, você precisa selecionar uma posição **Inicial** e uma **Final**.</span><span class="sxs-lookup"><span data-stu-id="013d2-211">For this setting, you need to select a **Start** and an **End** position.</span></span> <span data-ttu-id="013d2-212">Esses valores representam o número de tokens do início do documento.</span><span class="sxs-lookup"><span data-stu-id="013d2-212">These values represent the number of tokens from the begging of the document.</span></span> <span data-ttu-id="013d2-213">Embora seja possível inserir manualmente esses valores, é mais fácil ajustar manualmente a caixa de seleção no visualizador.</span><span class="sxs-lookup"><span data-stu-id="013d2-213">While you can manually enter in these values, it is easier to manually adjust the select box in the viewer.</span></span> 
   
## <a name="use-explanation-templates"></a><span data-ttu-id="013d2-214">Usar modelos de explicação</span><span class="sxs-lookup"><span data-stu-id="013d2-214">Use explanation templates</span></span>

<span data-ttu-id="013d2-215">Embora você possa adicionar manualmente vários valores da lista de frases para sua explicação, pode ser mais fácil usar os modelos fornecidos a você na biblioteca de explicação.</span><span class="sxs-lookup"><span data-stu-id="013d2-215">While you can manually add various phrase list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="013d2-216">Por exemplo, em vez de adicionar manualmente todas as variações de *Data*, você pode usar o modelo de lista de frases para *Data*, pois já inclui vários valores da listas de frases:</span><span class="sxs-lookup"><span data-stu-id="013d2-216">For example, instead of manually adding all the variations for *Date*, you can use the phrase list template for *Date* as it already includes a number of phrase lists values:</span></span>

![Biblioteca de explicações](../media/content-understanding/explanation-template.png)
 
<span data-ttu-id="013d2-218">A biblioteca de explicação inclui explicações da lista de frases comumente usadas, incluindo:</span><span class="sxs-lookup"><span data-stu-id="013d2-218">The explanation library includes commonly used phrase list explanations, including:</span></span>

- <span data-ttu-id="013d2-219">Data: datas do Calendário do Outlook, todos os formatos.</span><span class="sxs-lookup"><span data-stu-id="013d2-219">Date: Calendar dates, all formats.</span></span> <span data-ttu-id="013d2-220">Inclui texto e números (por exemplo, "9 de dezembro de 2020").</span><span class="sxs-lookup"><span data-stu-id="013d2-220">Includes text and numbers (for example, "Dec 9, 2020").</span></span>
- <span data-ttu-id="013d2-221">Data (numérico): datas do Calendário do Outlook, todos os formatos.</span><span class="sxs-lookup"><span data-stu-id="013d2-221">Date (numeric): Calendar dates, all formats.</span></span> <span data-ttu-id="013d2-222">Inclui números (por exemplo, 1-11-2020).</span><span class="sxs-lookup"><span data-stu-id="013d2-222">Includes numbers (for example 1-11-2020).</span></span>
- <span data-ttu-id="013d2-223">Relógio: formatos de 12 e 24 horas.</span><span class="sxs-lookup"><span data-stu-id="013d2-223">Time: 12 and 24 hour formats.</span></span>
- <span data-ttu-id="013d2-224">Número: números positivos e negativos até 2 decimais.</span><span class="sxs-lookup"><span data-stu-id="013d2-224">Number: Positive and negative numbers up to 2 decimals.</span></span> 
- <span data-ttu-id="013d2-225">Porcentagem: uma lista de padrões que representam uma porcentagem.</span><span class="sxs-lookup"><span data-stu-id="013d2-225">Percentage: A list of patterns representing a percentage.</span></span> <span data-ttu-id="013d2-226">Por exemplo, 1%, 11%, 100%, 11,11%, etc.</span><span class="sxs-lookup"><span data-stu-id="013d2-226">For example, 1%, 11%, 100%, 11.11%, etc.</span></span>
- <span data-ttu-id="013d2-227">Número de telefone: formatos comuns nos EUA e internacionais.</span><span class="sxs-lookup"><span data-stu-id="013d2-227">Phone number: Common US and International formats.</span></span> <span data-ttu-id="013d2-228">Por exemplo, 000 000 0000, 000-000-0000, (000) 000-0000, (000) 000-0000, etc.</span><span class="sxs-lookup"><span data-stu-id="013d2-228">For example, 000 000 0000, 000-000-0000, (000)000-0000, (000) 000-0000, etc.</span></span>
- <span data-ttu-id="013d2-229">Código postal: formatos de código postal dos EUA.</span><span class="sxs-lookup"><span data-stu-id="013d2-229">Zip code: US Zip code formats.</span></span> <span data-ttu-id="013d2-230">Por exemplo, 11111, 11111-1111.</span><span class="sxs-lookup"><span data-stu-id="013d2-230">For example, 11111, 11111-1111.</span></span>
- <span data-ttu-id="013d2-231">Primeira palavra da frase: padrões comuns para palavras de até 9 caracteres.</span><span class="sxs-lookup"><span data-stu-id="013d2-231">First word of sentence: Common patterns for words up to 9 characters.</span></span> 
- <span data-ttu-id="013d2-232">Fim da frase: pontuação comum para o final de uma frase</span><span class="sxs-lookup"><span data-stu-id="013d2-232">End of sentence: Common punctuation for end of a sentence</span></span>
- <span data-ttu-id="013d2-233">Cartão de crédito: formatos comuns de número de cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="013d2-233">Credit card: Common credit card number formats.</span></span> <span data-ttu-id="013d2-234">Por exemplo, 1111-1111-1111-1111.</span><span class="sxs-lookup"><span data-stu-id="013d2-234">For example, 1111-1111-1111-1111.</span></span> 
- <span data-ttu-id="013d2-235">Número da previdência social: formato do número da previdência social dos EUA.</span><span class="sxs-lookup"><span data-stu-id="013d2-235">Social security number: US Social Security Number format.</span></span> <span data-ttu-id="013d2-236">Por exemplo, 111-11-1111.</span><span class="sxs-lookup"><span data-stu-id="013d2-236">For example, 111-11-1111.</span></span> 
- <span data-ttu-id="013d2-237">Caixa de seleção: uma lista de frases que representa variações de uma caixa de seleção preenchida.</span><span class="sxs-lookup"><span data-stu-id="013d2-237">Checkbox: A phrase list representing variations on a filled in checkbox.</span></span> <span data-ttu-id="013d2-238">Por exemplo, _X_, _ _X_, etc.</span><span class="sxs-lookup"><span data-stu-id="013d2-238">For example, _X_, _ _X_, etc.</span></span>
- <span data-ttu-id="013d2-239">Moeda: principais símbolos internacionais.</span><span class="sxs-lookup"><span data-stu-id="013d2-239">Currency: Major international symbols.</span></span> <span data-ttu-id="013d2-240">Por exemplo, $.</span><span class="sxs-lookup"><span data-stu-id="013d2-240">For example, $.</span></span> 
- <span data-ttu-id="013d2-241">CC de email: uma lista de frases com o termo 'CC:', geralmente encontrada perto dos nomes ou endereços de email de outras pessoas ou grupos para os quais a mensagem foi enviada.</span><span class="sxs-lookup"><span data-stu-id="013d2-241">Email CC: A phrase list with the term 'CC:', often found near the names or email addresses of additional people or groups the message was sent to.</span></span>
- <span data-ttu-id="013d2-242">Data do email: uma lista de frases com o termo 'Enviado em:', geralmente encontrada próximo à data em que o email foi enviado.</span><span class="sxs-lookup"><span data-stu-id="013d2-242">Email date: A phrase list with the term 'Sent on:', often found near the date the email was sent.</span></span>
- <span data-ttu-id="013d2-243">Saudação por email: linhas de abertura comuns para emails.</span><span class="sxs-lookup"><span data-stu-id="013d2-243">Email greeting: Common opening lines for emails.</span></span>
- <span data-ttu-id="013d2-244">Destinatário do email: uma lista de frases com o termo 'Para:', geralmente encontrada próximo aos nomes ou endereços de email de pessoas ou grupos para os quais a mensagem foi enviada.</span><span class="sxs-lookup"><span data-stu-id="013d2-244">Email recipient: A phrase list with the term 'To:', often found near the names or email addresses of people or groups the message was sent to.</span></span> 
- <span data-ttu-id="013d2-245">Remetente do email: uma lista de frases com o termo 'De:', geralmente encontrada próximo ao nome ou endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="013d2-245">Email sender: A phrase list with the term 'From:', often found near the sender's name or email address.</span></span> 
- <span data-ttu-id="013d2-246">Assunto do email: uma lista de frases com o termo 'Assunto:', geralmente encontrada próximo ao assunto do email.</span><span class="sxs-lookup"><span data-stu-id="013d2-246">Email subject: A phrase list with the term 'Subject:', often found near the email's subject.</span></span> 

<span data-ttu-id="013d2-247">A biblioteca de explicação também inclui três tipos de modelos automáticos que funcionam com os dados que você rotulou em seus arquivos de exemplo:</span><span class="sxs-lookup"><span data-stu-id="013d2-247">The explanation library also includes three automatic template types that work with the data you've labeled in your example files:</span></span>

- <span data-ttu-id="013d2-248">Depois do rótulo: As palavras ou caracteres que ocorrem após os rótulos nos arquivos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="013d2-248">After label: The words or characters that occur after the labels in the example files.</span></span>
- <span data-ttu-id="013d2-249">Antes do rótulo: As palavras ou caracteres que ocorrem antes dos rótulos nos arquivos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="013d2-249">Before label: The words or characters that occur before the labels in the example files.</span></span>
- <span data-ttu-id="013d2-250">Rótulos: Até os primeiros 10 rótulos dos arquivos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="013d2-250">Labels: Up to the first 10 labels from the example files.</span></span>

<span data-ttu-id="013d2-251">Para lhe dar um exemplo de como os modelos automáticos funcionam, no arquivo de exemplo a seguir, usaremos o modelo de explicação Antes do rótulo para ajudar a fornecer ao modelo mais informações para obter uma correspondência mais precisa.</span><span class="sxs-lookup"><span data-stu-id="013d2-251">To give you an example of how automatic templates work, in the following example file, we will use the Before Label explanation template to help give the model more information to get a more accurate match.</span></span>

![Arquivo de exemplo](../media/content-understanding/before-label.png)

<span data-ttu-id="013d2-253">Quando você seleciona o modelo de explicação Antes do Rótulo, ele procura o primeiro conjunto de palavras que aparece antes do rótulo em seus arquivos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="013d2-253">When you select the Before Label explanation template, it will look for the first set of words that appear before the label in your example files.</span></span> <span data-ttu-id="013d2-254">No exemplo, as palavras identificadas no primeiro arquivo de exemplo são "A partir de".</span><span class="sxs-lookup"><span data-stu-id="013d2-254">In the example, the words that are identified in the first example file is "As of".</span></span>

![Antes do Modelo do Rótulo](../media/content-understanding/before-label-explanation.png)

<span data-ttu-id="013d2-256">Você pode selecionar **Adicionar** para criar uma explicação a partir do modelo.</span><span class="sxs-lookup"><span data-stu-id="013d2-256">You can select **Add** to create an explanation from the template.</span></span>  <span data-ttu-id="013d2-257">Conforme você adiciona mais arquivos de exemplo, palavras adicionais serão identificadas e adicionadas à lista de frases.</span><span class="sxs-lookup"><span data-stu-id="013d2-257">As you add more example files, additional words will be identified and added to the phrase list.</span></span>

![Adicionar o rótulo](../media/content-understanding/before-label-add.png)
 
#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="013d2-259">Para usar um modelo da biblioteca de explicações</span><span class="sxs-lookup"><span data-stu-id="013d2-259">To use a template from the explanation library</span></span>

1. <span data-ttu-id="013d2-260">Na seção **Explicações** da página de **Treinamento** do seu modelo, selecione **Novo** e, em seguida, selecione **De um modelo**.</span><span class="sxs-lookup"><span data-stu-id="013d2-260">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span>

   ![Adicionar Antes do Rótulo](../media/content-understanding/from-template.png)

2.  <span data-ttu-id="013d2-262">Na página **Modelos de explicação**, selecione a explicação que você deseja usar e, em seguida, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="013d2-262">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span>

    ![Selecionar um modelo](../media/content-understanding/phone-template.png)

3. <span data-ttu-id="013d2-264">As informações do modelo que você selecionou são exibidas na página **Criar uma explicação**.</span><span class="sxs-lookup"><span data-stu-id="013d2-264">The information for the template you selected displays on the **Create an explanation** page.</span></span> <span data-ttu-id="013d2-265">Se necessário, edite o nome da explicação e adicione ou remova itens da lista de frases.</span><span class="sxs-lookup"><span data-stu-id="013d2-265">If needed, edit the explanation name and add or remove items from the phrase list.</span></span>  

    ![Editar modelo](../media/content-understanding/phone-template-live.png)

4. <span data-ttu-id="013d2-267">Quando concluir, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="013d2-267">When finished, select **Save**.</span></span>