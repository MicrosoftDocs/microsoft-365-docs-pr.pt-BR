---
title: Tipos de explicação no Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Saiba mais sobre tipos de explicação no Microsoft SharePoint Syntex.
ms.openlocfilehash: 515fd8af289ec7c64e14eb6d54b236ba3a8aa9f6
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706543"
---
# <a name="explanation-types-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="cd38a-103">Tipos de explicação no Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="cd38a-103">Explanation types in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="cd38a-104">As explicações são usadas para ajudar a definir as informações que você deseja rotular e extrai para seus modelos de compreensão de documentos no Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="cd38a-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="cd38a-105">Ao criar uma explicação, você precisa selecionar um tipo de explicação.</span><span class="sxs-lookup"><span data-stu-id="cd38a-105">When you create an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="cd38a-106">Este artigo ajuda você a entender os diferentes tipos de explicação e como eles são usados.</span><span class="sxs-lookup"><span data-stu-id="cd38a-106">This article helps you understand the different explanation types and how they're used.</span></span>

![Captura de tela do painel Criar uma explicação mostrando os três tipos de explicação.](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="cd38a-108">Esses tipos de explicação estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="cd38a-108">These explanation types are available:</span></span>

- <span data-ttu-id="cd38a-109">[**Lista de frases**](#phrase-list): Lista de palavras, frases, números ou outros caracteres que você pode usar no documento ou nas informações que você está extraindo.</span><span class="sxs-lookup"><span data-stu-id="cd38a-109">[**Phrase list**](#phrase-list): List of words, phrases, numbers, or other characters you can use in the document or information that you're extracting.</span></span> <span data-ttu-id="cd38a-110">Por exemplo, a cadeia de caracteres *médico encaminhador* está em todos os documentos de Referência Médica que você está identificando.</span><span class="sxs-lookup"><span data-stu-id="cd38a-110">For example, the text string *referring doctor* is in all Medical Referral documents you're identifying.</span></span> <span data-ttu-id="cd38a-111">Ou o *número de telefone* do médico encaminhador de todos os documentos de Referência Médica que você está identificando.</span><span class="sxs-lookup"><span data-stu-id="cd38a-111">Or the *phone number* of the referring doctor from all Medical Referral documents that you're identifying.</span></span>

- <span data-ttu-id="cd38a-112">[**Expressão regular**](#regular-expression): Usa uma notação de correspondência de padrão para encontrar padrões de caracteres específicos.</span><span class="sxs-lookup"><span data-stu-id="cd38a-112">[**Regular expression**](#regular-expression): Uses a pattern-matching notation to find specific character patterns.</span></span> <span data-ttu-id="cd38a-113">Por exemplo, você pode usar uma expressão regular para encontrar todas as instâncias de um padrão de *endereço de email* em um conjunto de documentos.</span><span class="sxs-lookup"><span data-stu-id="cd38a-113">For example, you can use a regular expression to find all instances of an *email address* pattern in a set of documents.</span></span>

- <span data-ttu-id="cd38a-114">[**Proximidade**](#proximity): Descreve o quão próximas as explicações são umas das outras.</span><span class="sxs-lookup"><span data-stu-id="cd38a-114">[**Proximity**](#proximity): Describes how close explanations are to each other.</span></span> <span data-ttu-id="cd38a-115">Por exemplo, uma lista de frases de *número da rua* vai logo antes da lista de frases de *nome da rua*, sem tokens entre eles (você aprenderá sobre tokens posteriormente neste artigo).</span><span class="sxs-lookup"><span data-stu-id="cd38a-115">For example, a *street number* phrase list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="cd38a-116">Usar o tipo de proximidade exige que você tenha pelo menos duas explicações em seu modelo, ou a opção será desabilitada.</span><span class="sxs-lookup"><span data-stu-id="cd38a-116">Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 

## <a name="phrase-list"></a><span data-ttu-id="cd38a-117">Lista de frases</span><span class="sxs-lookup"><span data-stu-id="cd38a-117">Phrase list</span></span>

<span data-ttu-id="cd38a-118">Um tipo de explicação de lista de frases geralmente é usado para identificar e classificar um documento por meio do seu modelo.</span><span class="sxs-lookup"><span data-stu-id="cd38a-118">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="cd38a-119">Conforme descrito no exemplo de rótulo *médico encaminhador*, é uma cadeia de palavras, frases, números ou caracteres que está consistentemente nos documentos que você está identificando.</span><span class="sxs-lookup"><span data-stu-id="cd38a-119">As described in the *referring doctor* label example, it's a string of words, phrases, numbers, or characters that is consistently in the documents that you're identifying.</span></span>

<span data-ttu-id="cd38a-120">Embora não seja um requisito, você pode obter um sucesso melhor com a sua explicação se a frase que está capturando estiver localizada em um local consistente no documento.</span><span class="sxs-lookup"><span data-stu-id="cd38a-120">While not a requirement, you can achieve better success with your explanation if the phrase you're capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="cd38a-121">Por exemplo, o rótulo *médico encaminhador* poderia estar localizado consistentemente no primeiro parágrafo do documento.</span><span class="sxs-lookup"><span data-stu-id="cd38a-121">For example, the *referring doctor* label might be consistently located in the first paragraph of the document.</span></span> <span data-ttu-id="cd38a-122">Você também pode usar a configuração avançada **[Configurar onde as frases ocorrem no documento](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** para selecionar áreas específicas onde a frase se encontra, especialmente se houver uma chance de a frase ocorrer em vários locais no documento.</span><span class="sxs-lookup"><span data-stu-id="cd38a-122">You can also use the **[Configure where phrases occur in the document](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** advanced setting to select specific areas where the phrase is located, especially if there's a chance that the phrase might occur in multiple locations in your document.</span></span>

<span data-ttu-id="cd38a-123">Se a diferenciação de maiúsculas e minúsculas for um requisito para a identificação do seu rótulo, usar o tipo de lista de frases permite que você o especifique na sua explicação selecionando a caixa de seleção **Somente maiúsculas**.</span><span class="sxs-lookup"><span data-stu-id="cd38a-123">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

![Diferenciação de maiúsculas e minúsculas](../media/content-understanding/case-sensitivity.png) 

<span data-ttu-id="cd38a-125">Um tipo de frase é especialmente útil quando você cria uma explicação que identifica e extrai informações em diferentes formatos, como datas, números de telefone e números de cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="cd38a-125">A phrase type is especially useful when you create an explanation that identifies and extracts information in different formats, such as dates, phone numbers, and credit card numbers.</span></span> <span data-ttu-id="cd38a-126">Por exemplo, uma data pode ser exibida em vários formatos diferentes (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020 ou 1º de janeiro de 2020).</span><span class="sxs-lookup"><span data-stu-id="cd38a-126">For example, a date can be displayed in many different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, or Jan 1,2020).</span></span> <span data-ttu-id="cd38a-127">Definir uma lista de frases torna sua explicação mais eficiente, capturando quaisquer variações possíveis nos dados que você está tentando identificar e extrair.</span><span class="sxs-lookup"><span data-stu-id="cd38a-127">Defining a phrase list makes your explanation more efficient by capturing any possible variations in the data that you're trying to identify and extract.</span></span> 

<span data-ttu-id="cd38a-128">Para o exemplo de *Número de telefone*, você extrai o número de telefone de cada médico encaminhador de todos os documentos de Referência Médica que o modelo identifica.</span><span class="sxs-lookup"><span data-stu-id="cd38a-128">For the *phone number* example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="cd38a-129">Ao criar a explicação, digite os diferentes formatos que um número de telefone pode exibir em seu documento para que você possa capturar possíveis variações.</span><span class="sxs-lookup"><span data-stu-id="cd38a-129">When you create the explanation, type the different formats a phone number might display in your document so that you're able to capture possible variations.</span></span> 

![Padrões de frase de número de telefone](../media/content-understanding/pattern-list.png)

<span data-ttu-id="cd38a-131">Para este exemplo, em **Configurações Avançadas**, marque a caixa de seleção **Qualquer dígito de 0-9** para reconhecer cada valor "0" usado em sua lista de frases como qualquer dígito de 0 a 9.</span><span class="sxs-lookup"><span data-stu-id="cd38a-131">For this example, in **Advanced Settings** select the **Any digit from 0-9** checkbox to recognize each "0" value used in your phrase list to be any digit from 0 through 9.</span></span>

![Qualquer dígito de 0-9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="cd38a-133">Da mesma forma, se você criar uma lista de frases que inclua caracteres de texto, marque a caixa de seleção **Qualquer letra de a-z** para reconhecer cada caractere "a" usado na lista de frases como qualquer caractere de "a" a "z".</span><span class="sxs-lookup"><span data-stu-id="cd38a-133">Similarly, if you create a phrase list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the phrase list to be any character from "a" to "z".</span></span>

<span data-ttu-id="cd38a-134">Por exemplo, se você criar uma lista de frases de **Data** e desejar ter certeza de que um formato de data como *Jan 1, 2020* será reconhecido, você precisará:</span><span class="sxs-lookup"><span data-stu-id="cd38a-134">For example, if you create a **Date** phrase list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>

- <span data-ttu-id="cd38a-135">Adicionar *aaa 0, 0000* e *aaa 00, 0000* à sua lista de frases.</span><span class="sxs-lookup"><span data-stu-id="cd38a-135">Add *aaa 0, 0000* and *aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="cd38a-136">Verificar se **Qualquer letra de a-z** também está selecionada.</span><span class="sxs-lookup"><span data-stu-id="cd38a-136">Make sure that **Any letter from a-z** is also selected.</span></span>

![Qualquer letra de a-z](../media/content-understanding/any-letter.png)

<span data-ttu-id="cd38a-138">Se você tiver requisitos de uso de maiúsculas ou minúsculas na sua lista de frases, poderá marcar a caixa de seleção **Apenas capitalização exata**.</span><span class="sxs-lookup"><span data-stu-id="cd38a-138">If you have capitalization requirements in your phrase list, you can select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="cd38a-139">Para o exemplo de data, se você exige que a primeira letra do mês seja maiúscula, você precisa:</span><span class="sxs-lookup"><span data-stu-id="cd38a-139">For the date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="cd38a-140">Adicionar *Aaa 0, 0000* e *Aaa 00, 0000* à sua lista de frases.</span><span class="sxs-lookup"><span data-stu-id="cd38a-140">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="cd38a-141">Verificar se **Somente maiúsculas** também está selecionada.</span><span class="sxs-lookup"><span data-stu-id="cd38a-141">Make sure that **Only exact capitalization** is also selected.</span></span>

![Somente maiúsculas](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="cd38a-143">Em vez de criar manualmente uma explicação de lista de frases, use a [biblioteca de explicações](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) para usar modelos de lista de frases para uma lista de frases comuns, como *data*, *número de telefone* ou *número de cartão de crédito*.</span><span class="sxs-lookup"><span data-stu-id="cd38a-143">Instead of manually creating a phrase list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use phrase list templates for a common phrase list, such as *date*, *phone number*, or *credit card number*.</span></span>

## <a name="regular-expression"></a><span data-ttu-id="cd38a-144">Expressão regular</span><span class="sxs-lookup"><span data-stu-id="cd38a-144">Regular expression</span></span>

<span data-ttu-id="cd38a-145">Um tipo de explicação de expressão regular permite criar padrões que ajudam a encontrar e identificar determinadas cadeias de texto em documentos.</span><span class="sxs-lookup"><span data-stu-id="cd38a-145">A regular expression explanation type allows you to create patterns that help find and identify certain text strings in documents.</span></span> <span data-ttu-id="cd38a-146">Você pode usar expressões regulares para analisar rapidamente grandes quantidades de texto para:</span><span class="sxs-lookup"><span data-stu-id="cd38a-146">You can use regular expressions to quickly parse large amounts of text to:</span></span>

- <span data-ttu-id="cd38a-147">Encontrar padrões de caracteres específicos.</span><span class="sxs-lookup"><span data-stu-id="cd38a-147">Find specific character patterns.</span></span>
- <span data-ttu-id="cd38a-148">Validar o texto para garantir que ele corresponde a um padrão predefinido (como um endereço de email).</span><span class="sxs-lookup"><span data-stu-id="cd38a-148">Validate text to ensure that it matches a predefined pattern (such as an email address).</span></span>
- <span data-ttu-id="cd38a-149">Extrair, editar, substituir ou excluir subseções de texto.</span><span class="sxs-lookup"><span data-stu-id="cd38a-149">Extract, edit, replace, or delete text substrings.</span></span>

<span data-ttu-id="cd38a-150">Um tipo de expressão regular é especialmente útil quando você cria uma explicação que identifica e extrai informações em formatos semelhantes, como endereços de email, números de conta bancária ou URLs.</span><span class="sxs-lookup"><span data-stu-id="cd38a-150">A regular expression type is especially useful when you create an explanation that identifies and extracts information in similar formats, such as email addresses, bank account numbers, or URLs.</span></span> <span data-ttu-id="cd38a-151">Por exemplo, um endereço de email, como megan@contoso.com, é exibido em um determinado padrão ("megan" é a primeira parte, e "com" é a última parte).</span><span class="sxs-lookup"><span data-stu-id="cd38a-151">For example, an email address, such as megan@contoso.com, is displayed in a certain pattern ("megan" is the first part, and "com" is the last part).</span></span> 

<span data-ttu-id="cd38a-152">A expressão regular para um endereço de email é: **[A-Za-z0-9._%-]+@[A-Za-z0-9.-]+.[A-Za-z]{2,6}**.</span><span class="sxs-lookup"><span data-stu-id="cd38a-152">The regular expression for an email address is: **[A-Za-z0-9._%-]+@[A-Za-z0-9.-]+.[A-Za-z]{2,6}**.</span></span>

<span data-ttu-id="cd38a-153">Essa expressão consiste em cinco partes, nesta ordem:</span><span class="sxs-lookup"><span data-stu-id="cd38a-153">This expression consists of five parts, in this order:</span></span>

1. <span data-ttu-id="cd38a-154">Qualquer quantidade dos seguintes caracteres:</span><span class="sxs-lookup"><span data-stu-id="cd38a-154">Any amount of the following characters:</span></span>

   <span data-ttu-id="cd38a-p112">a. Letras de A a Z</span><span class="sxs-lookup"><span data-stu-id="cd38a-p112">a. Letters from a to z</span></span>

   <span data-ttu-id="cd38a-p113">b. Números de 0 a 9</span><span class="sxs-lookup"><span data-stu-id="cd38a-p113">b. Numbers from 0-9</span></span>

   <span data-ttu-id="cd38a-p114">c. Ponto, sublinhado, porcentagem ou traço</span><span class="sxs-lookup"><span data-stu-id="cd38a-p114">c. Period, underscore, percent, or dash</span></span>

2. <span data-ttu-id="cd38a-161">O símbolo @</span><span class="sxs-lookup"><span data-stu-id="cd38a-161">The @ symbol</span></span>

3. <span data-ttu-id="cd38a-162">Qualquer quantidade de caracteres iguais à primeira parte do endereço de email</span><span class="sxs-lookup"><span data-stu-id="cd38a-162">Any amount of the same characters as the first part of the email address</span></span>

4. <span data-ttu-id="cd38a-163">Um ponto</span><span class="sxs-lookup"><span data-stu-id="cd38a-163">A period</span></span>

5. <span data-ttu-id="cd38a-164">De duas a seis letras</span><span class="sxs-lookup"><span data-stu-id="cd38a-164">Two to six letters</span></span>

<span data-ttu-id="cd38a-165">Para adicionar um tipo de explicação de expressão regular:</span><span class="sxs-lookup"><span data-stu-id="cd38a-165">To add a regular expression explanation type:</span></span>

1. <span data-ttu-id="cd38a-166">No painel **Criar uma explicação**, em **Tipo de explicação**, selecione **Expressão regular**.</span><span class="sxs-lookup"><span data-stu-id="cd38a-166">From the **Create an explanation** panel, under **Explanation type**, select **Regular expression**.</span></span>

   ![Captura de tela mostrando o painel Criar um explicação com a opção Expressão Regular selecionada.](../media/content-understanding/create-regular-expression.png)

2. <span data-ttu-id="cd38a-168">Você pode digitar uma expressão na caixa de texto **Expressão regular** ou selecionar **Adicionar uma expressão regular a partir de um modelo**.</span><span class="sxs-lookup"><span data-stu-id="cd38a-168">You can either type an expression in the **Regular expression** text box or select **Add a regular expression from a template**.</span></span>

   <span data-ttu-id="cd38a-169">Quando você adiciona uma expressão regular usando um modelo, ele adiciona automaticamente o nome e a expressão regular à caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="cd38a-169">When you add a regular expression by using a template, it automatically adds the name and the regular expression to the text box.</span></span> <span data-ttu-id="cd38a-170">Por exemplo, se você escolher o modelo **Endereço de email**, o painel **Criar uma explicação** será preenchido.</span><span class="sxs-lookup"><span data-stu-id="cd38a-170">For example, if you choose the **Email address** template, the **Create an explanation** panel will be populated.</span></span>

   ![Captura de tela mostrando o painel Criar uma explicação com o modelo de Endereço de email aplicado.](../media/content-understanding/create-regular-expression-email.png)

## <a name="proximity"></a><span data-ttu-id="cd38a-172">Proximidade</span><span class="sxs-lookup"><span data-stu-id="cd38a-172">Proximity</span></span> 

<span data-ttu-id="cd38a-173">O tipo de explicação da proximidade ajuda seu modelo a identificar dados definindo a proximidade dos dados entre si.</span><span class="sxs-lookup"><span data-stu-id="cd38a-173">The proximity explanation type helps your model identify data by defining how close another piece of data is to it.</span></span> <span data-ttu-id="cd38a-174">Por exemplo, em seu modelo, você definiu duas explicações que rotulam o *Número da rua* e *Número de telefone* do cliente.</span><span class="sxs-lookup"><span data-stu-id="cd38a-174">For example, in your model say you have defined two explanations that label both the customer *street address number* and *phone number*.</span></span> 

<span data-ttu-id="cd38a-175">Observe que os números de telefone do cliente sempre aparecem antes do número da rua.</span><span class="sxs-lookup"><span data-stu-id="cd38a-175">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="cd38a-176">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="cd38a-176">Alex Wilburn</span></span><br>
<span data-ttu-id="cd38a-177">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="cd38a-177">555-555-5555</span></span><br>
<span data-ttu-id="cd38a-178">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="cd38a-178">One Microsoft Way</span></span><br>
<span data-ttu-id="cd38a-179">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="cd38a-179">Redmond, WA 98034</span></span><br>

<span data-ttu-id="cd38a-180">Use a explicação de proximidade para definir a distância da explicação do número de telefone para identificar melhor o número da rua em seus documentos.</span><span class="sxs-lookup"><span data-stu-id="cd38a-180">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

![Explicação de proximidade](../media/content-understanding/proximity.png)

#### <a name="what-are-tokens"></a><span data-ttu-id="cd38a-182">O que são tokens?</span><span class="sxs-lookup"><span data-stu-id="cd38a-182">What are tokens?</span></span>

<span data-ttu-id="cd38a-183">Para usar o tipo de explicação de proximidade, você precisa entender o que é um token.</span><span class="sxs-lookup"><span data-stu-id="cd38a-183">To use the proximity explanation type, you need to understand what a token is.</span></span> <span data-ttu-id="cd38a-184">O número de tokens é como a explicação de proximidade mede a distância de uma explicação para outra.</span><span class="sxs-lookup"><span data-stu-id="cd38a-184">The number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span> <span data-ttu-id="cd38a-185">Um token é um intervalo contínuo (sem incluir espaços ou pontuação) de letras e números.</span><span class="sxs-lookup"><span data-stu-id="cd38a-185">A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="cd38a-186">A tabela a seguir mostra exemplos de como determinar o número de tokens em uma frase.</span><span class="sxs-lookup"><span data-stu-id="cd38a-186">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="cd38a-187">Frase</span><span class="sxs-lookup"><span data-stu-id="cd38a-187">Phrase</span></span>|<span data-ttu-id="cd38a-188">Número de tokens</span><span class="sxs-lookup"><span data-stu-id="cd38a-188">Number of tokens</span></span>|<span data-ttu-id="cd38a-189">Explicação</span><span class="sxs-lookup"><span data-stu-id="cd38a-189">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="cd38a-190">1</span><span class="sxs-lookup"><span data-stu-id="cd38a-190">1</span></span>|<span data-ttu-id="cd38a-191">Uma única palavra sem pontuação ou espaços.</span><span class="sxs-lookup"><span data-stu-id="cd38a-191">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="cd38a-192">1</span><span class="sxs-lookup"><span data-stu-id="cd38a-192">1</span></span>|<span data-ttu-id="cd38a-193">Um número de localizador de registro.</span><span class="sxs-lookup"><span data-stu-id="cd38a-193">A record locator number.</span></span> <span data-ttu-id="cd38a-194">Pode incluir números e letras, mas não tem pontuação.</span><span class="sxs-lookup"><span data-stu-id="cd38a-194">It might include numbers and letters, but doesn't have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="cd38a-195">5</span><span class="sxs-lookup"><span data-stu-id="cd38a-195">5</span></span>|<span data-ttu-id="cd38a-196">Um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="cd38a-196">A phone number.</span></span> <span data-ttu-id="cd38a-197">Cada sinal de pontuação é um único token, assim `425-555-5555` equivale a 5 tokens:</span><span class="sxs-lookup"><span data-stu-id="cd38a-197">Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="cd38a-198">7</span><span class="sxs-lookup"><span data-stu-id="cd38a-198">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="cd38a-199">Configurar o tipo de explicação de proximidade</span><span class="sxs-lookup"><span data-stu-id="cd38a-199">Configure the proximity explanation type</span></span>

<span data-ttu-id="cd38a-200">Para o exemplo, defina a configuração de proximidade para definir o intervalo do número de tokens na explicação do *número de telefone* da explicação do *número da rua*.</span><span class="sxs-lookup"><span data-stu-id="cd38a-200">For the example, configure the proximity setting to define the range of the number of tokens in the *phone number* explanation from the *street address number* explanation.</span></span> <span data-ttu-id="cd38a-201">Observe que o intervalo mínimo é “0”, pois não há nenhum token entre o número de telefone e o número da rua.</span><span class="sxs-lookup"><span data-stu-id="cd38a-201">Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="cd38a-202">No entanto, alguns números de telefone nos documentos de exemplo são acrescentados no *(telefone)*.</span><span class="sxs-lookup"><span data-stu-id="cd38a-202">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="cd38a-203">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="cd38a-203">Nestor Wilke</span></span><br>
<span data-ttu-id="cd38a-204">111-111-1111 (móvel)</span><span class="sxs-lookup"><span data-stu-id="cd38a-204">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="cd38a-205">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="cd38a-205">One Microsoft Way</span></span><br>
<span data-ttu-id="cd38a-206">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="cd38a-206">Redmond, WA 98034</span></span><br>

<span data-ttu-id="cd38a-207">Há três tokens em *(móvel)*:</span><span class="sxs-lookup"><span data-stu-id="cd38a-207">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="cd38a-208">Frase</span><span class="sxs-lookup"><span data-stu-id="cd38a-208">Phrase</span></span>|<span data-ttu-id="cd38a-209">Contagem de tokens</span><span class="sxs-lookup"><span data-stu-id="cd38a-209">Token count</span></span>|
|--|--|
|<span data-ttu-id="cd38a-210">(</span><span class="sxs-lookup"><span data-stu-id="cd38a-210">(</span></span>|<span data-ttu-id="cd38a-211">1</span><span class="sxs-lookup"><span data-stu-id="cd38a-211">1</span></span>|
|<span data-ttu-id="cd38a-212">móvel</span><span class="sxs-lookup"><span data-stu-id="cd38a-212">mobile</span></span>|<span data-ttu-id="cd38a-213">2</span><span class="sxs-lookup"><span data-stu-id="cd38a-213">2</span></span>|
|<span data-ttu-id="cd38a-214">)</span><span class="sxs-lookup"><span data-stu-id="cd38a-214">)</span></span>|<span data-ttu-id="cd38a-215">3</span><span class="sxs-lookup"><span data-stu-id="cd38a-215">3</span></span>|

<span data-ttu-id="cd38a-216">Definir a configuração de proximidade para ter um intervalo de 0 a 3.</span><span class="sxs-lookup"><span data-stu-id="cd38a-216">Configure the proximity setting to have a range of 0 through 3.</span></span>

![Exemplo de proximidade](../media/content-understanding/proximity-example.png)

## <a name="configure-where-phrases-occur-in-the-document"></a><span data-ttu-id="cd38a-218">Configurar onde as frases ocorrem no documento</span><span class="sxs-lookup"><span data-stu-id="cd38a-218">Configure where phrases occur in the document</span></span>

<span data-ttu-id="cd38a-219">Quando você cria uma explicação, por padrão, todo o documento é pesquisado pela frase que você está tentando extrair.</span><span class="sxs-lookup"><span data-stu-id="cd38a-219">When you create an explanation, by default the entire document is searched for the phrase you're trying to extract.</span></span> <span data-ttu-id="cd38a-220">No entanto, você pode usar a configuração avançada **Onde essas frases ocorrem** para ajudar a isolar um local específico do documento em que ocorre uma frase.</span><span class="sxs-lookup"><span data-stu-id="cd38a-220">However, you can use the **Where these phrases occur** advanced setting to help in isolating a specific location in the document that a phrase occurs.</span></span> <span data-ttu-id="cd38a-221">Essa configuração é útil em situações em que instâncias semelhantes de uma frase podem aparecer em outro lugar no documento e você deseja ter certeza de que a correta está selecionada.</span><span class="sxs-lookup"><span data-stu-id="cd38a-221">This setting is useful in situations where similar instances of a phrase might appear somewhere else in the document, and you want to make sure that the correct one is selected.</span></span>

<span data-ttu-id="cd38a-222">Ao se referir ao nosso exemplo de documento de Referência Médica, o *médico encaminhador* sempre é mencionado no primeiro parágrafo do documento.</span><span class="sxs-lookup"><span data-stu-id="cd38a-222">Referring to our Medical Referral document example, the *referring doctor* is always mentioned in the first paragraph of the document.</span></span> <span data-ttu-id="cd38a-223">Com a configuração **Onde essas frases ocorrem**, neste exemplo, você pode configurar a explicação para pesquisar por esse rótulo somente na seção inicial do documento ou em qualquer outro local em que ela possa ocorrer.</span><span class="sxs-lookup"><span data-stu-id="cd38a-223">With the **Where these phrases occur** setting, in this example you can configure your explanation to search for this label only in the beginning section of the document, or any other location in which it might occur.</span></span>

![Configuração de onde essas frases ocorrem](../media/content-understanding/phrase-location.png)

<span data-ttu-id="cd38a-225">Você pode escolher uma das três opções para esta configuração:</span><span class="sxs-lookup"><span data-stu-id="cd38a-225">You can choose the following options for this setting:</span></span>

- <span data-ttu-id="cd38a-226">Em qualquer lugar no arquivo: o documento inteiro é pesquisado pela frase.</span><span class="sxs-lookup"><span data-stu-id="cd38a-226">Anywhere in the file: The entire document is searched for the phrase.</span></span>

- <span data-ttu-id="cd38a-227">Início do arquivo: o documento é pesquisado do início até o local da frase.</span><span class="sxs-lookup"><span data-stu-id="cd38a-227">Beginning of the file:  The document is searched from the beginning to the phrase location.</span></span>

   ![Início do arquivo](../media/content-understanding/beginning-of-file.png)

    <span data-ttu-id="cd38a-229">No visualizador, você pode ajustar manualmente a caixa de seleção para incluir o local onde a fase ocorre.</span><span class="sxs-lookup"><span data-stu-id="cd38a-229">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="cd38a-230">O valor **Posição final** será atualizado para mostrar o número de tokens que sua área selecionada inclui.</span><span class="sxs-lookup"><span data-stu-id="cd38a-230">The **End position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="cd38a-231">Você pode atualizar o valor da **Posição final** para ajustar a área selecionada.</span><span class="sxs-lookup"><span data-stu-id="cd38a-231">You can update the **End position** value as well to adjust the selected area.</span></span>

   ![Início da caixa de posição do arquivo](../media/content-understanding/beginning-box.png)

- <span data-ttu-id="cd38a-233">Fim do arquivo: O documento é pesquisado desde o final até a localização da frase.</span><span class="sxs-lookup"><span data-stu-id="cd38a-233">End of the file: The document is searched from the end to the phrase location.</span></span>

   ![Fim do arquivo](../media/content-understanding/end-of-file.png)

    <span data-ttu-id="cd38a-235">No visualizador, você pode ajustar manualmente a caixa de seleção para incluir o local onde a fase ocorre.</span><span class="sxs-lookup"><span data-stu-id="cd38a-235">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="cd38a-236">O valor **Posição incial** será atualizado para mostrar o número de tokens que sua área selecionada inclui.</span><span class="sxs-lookup"><span data-stu-id="cd38a-236">The **Starting position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="cd38a-237">Você também pode atualizar o valor da Posição inicial para ajustar a área selecionada.</span><span class="sxs-lookup"><span data-stu-id="cd38a-237">You can update the Starting position value as well to adjust the selected area.</span></span>

   ![Fim da caixa de fim do arquivo](../media/content-understanding/end-box.png)

- <span data-ttu-id="cd38a-239">Intervalo personalizado: O documento é pesquisado dentro de um intervalo especificado para o local da frase.</span><span class="sxs-lookup"><span data-stu-id="cd38a-239">Custom range: The document is searched within a specified range for the phrase location.</span></span>

   ![Intervalo personalizado](../media/content-understanding/custom-file.png)

    <span data-ttu-id="cd38a-241">No visualizador, você pode ajustar manualmente a caixa de seleção para incluir o local onde a fase ocorre.</span><span class="sxs-lookup"><span data-stu-id="cd38a-241">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="cd38a-242">Para essa configuração, você precisa selecionar uma posição **Inicial** e uma **Final**.</span><span class="sxs-lookup"><span data-stu-id="cd38a-242">For this setting, you need to select a **Start** and an **End** position.</span></span> <span data-ttu-id="cd38a-243">Esses valores representam o número de tokens desde o início do documento.</span><span class="sxs-lookup"><span data-stu-id="cd38a-243">These values represent the number of tokens from the beginning of the document.</span></span> <span data-ttu-id="cd38a-244">Embora seja possível inserir manualmente esses valores, é mais fácil ajustar manualmente a caixa de seleção no visualizador.</span><span class="sxs-lookup"><span data-stu-id="cd38a-244">While you can manually enter in these values, it's easier to manually adjust the select box in the viewer.</span></span> 
   
## <a name="use-explanation-templates"></a><span data-ttu-id="cd38a-245">Usar modelos de explicação</span><span class="sxs-lookup"><span data-stu-id="cd38a-245">Use explanation templates</span></span>

<span data-ttu-id="cd38a-246">Embora você possa adicionar manualmente vários valores da lista de frases para sua explicação, pode ser mais fácil usar os modelos fornecidos a você na biblioteca de explicação.</span><span class="sxs-lookup"><span data-stu-id="cd38a-246">While you can manually add various phrase list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="cd38a-247">Por exemplo, em vez de adicionar manualmente todas as variações de *data*, você pode usar o modelo de lista de frases para *data* porque ele já inclui muitos valores de listas de frases:</span><span class="sxs-lookup"><span data-stu-id="cd38a-247">For example, instead of manually adding all the variations for *date*, you can use the phrase list template for *date* because it already includes many phrase lists values:</span></span>

![Biblioteca de explicações](../media/content-understanding/explanation-template.png)
 
<span data-ttu-id="cd38a-249&quot;>A biblioteca de explicações inclui explicações de *lista de frases* frequentemente usadas, incluindo:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;cd38a-249&quot;>The explanation library includes commonly used *phrase list* explanations, including:</span></span>

- <span data-ttu-id=&quot;cd38a-250&quot;>Data: datas do Calendário do Outlook, todos os formatos.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;cd38a-250&quot;>Date: Calendar dates, all formats.</span></span> <span data-ttu-id=&quot;cd38a-251&quot;>Inclui texto e números (por exemplo, &quot;9 de dezembro de 2020").</span><span class="sxs-lookup"><span data-stu-id="cd38a-251">Includes text and numbers (for example, "Dec 9, 2020").</span></span>
- <span data-ttu-id="cd38a-252">Data (numérico): datas do Calendário do Outlook, todos os formatos.</span><span class="sxs-lookup"><span data-stu-id="cd38a-252">Date (numeric): Calendar dates, all formats.</span></span> <span data-ttu-id="cd38a-253">Inclui números (por exemplo, 1-11-2020).</span><span class="sxs-lookup"><span data-stu-id="cd38a-253">Includes numbers (for example, 1-11-2020).</span></span>
- <span data-ttu-id="cd38a-254">Relógio: formatos de 12 e 24 horas.</span><span class="sxs-lookup"><span data-stu-id="cd38a-254">Time: 12 and 24 hour formats.</span></span>
- <span data-ttu-id="cd38a-255">Número: números positivos e negativos até dois decimais.</span><span class="sxs-lookup"><span data-stu-id="cd38a-255">Number: Positive and negative numbers up to two decimals.</span></span> 
- <span data-ttu-id="cd38a-256">Porcentagem: uma lista de padrões que representam uma porcentagem.</span><span class="sxs-lookup"><span data-stu-id="cd38a-256">Percentage: A list of patterns representing a percentage.</span></span> <span data-ttu-id="cd38a-257">Por exemplo, 1%, 11%, 100% ou 11,11%.</span><span class="sxs-lookup"><span data-stu-id="cd38a-257">For example, 1%, 11%, 100%, or 11.11%.</span></span>
- <span data-ttu-id="cd38a-258">Número de telefone: Formatos comuns nos EUA e internacionais.</span><span class="sxs-lookup"><span data-stu-id="cd38a-258">Phone number: Common US and International formats.</span></span> <span data-ttu-id="cd38a-259">Por exemplo, 000 000 0000, 000-000-0000, (000)000-0000 ou (000) 000-0000.</span><span class="sxs-lookup"><span data-stu-id="cd38a-259">For example, 000 000 0000, 000-000-0000, (000)000-0000, or (000) 000-0000.</span></span>
- <span data-ttu-id="cd38a-260">Código postal: formatos de código postal dos EUA.</span><span class="sxs-lookup"><span data-stu-id="cd38a-260">Zip code: US Zip code formats.</span></span> <span data-ttu-id="cd38a-261">Por exemplo, 11111, 11111-1111.</span><span class="sxs-lookup"><span data-stu-id="cd38a-261">For example, 11111, 11111-1111.</span></span>
- <span data-ttu-id="cd38a-262">Primeira palavra da frase: Padrões comuns para palavras de até nove caracteres.</span><span class="sxs-lookup"><span data-stu-id="cd38a-262">First word of sentence: Common patterns for words up to nine characters.</span></span> 
- <span data-ttu-id="cd38a-263">Fim da frase: pontuação comum para o final de uma frase.</span><span class="sxs-lookup"><span data-stu-id="cd38a-263">End of sentence: Common punctuation for end of a sentence.</span></span>
- <span data-ttu-id="cd38a-264">Cartão de crédito: formatos comuns de número de cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="cd38a-264">Credit card: Common credit card number formats.</span></span> <span data-ttu-id="cd38a-265">Por exemplo, 1111-1111-1111-1111.</span><span class="sxs-lookup"><span data-stu-id="cd38a-265">For example, 1111-1111-1111-1111.</span></span> 
- <span data-ttu-id="cd38a-p132">Número da previdência social: Formato do número da previdência social dos EUA. Por exemplo, 111-11-1111.</span><span class="sxs-lookup"><span data-stu-id="cd38a-p132">Social security number: US Social Security Number format. For example, 111-11-1111.</span></span> 
- <span data-ttu-id="cd38a-268">Caixa de seleção: Uma lista de frases que representa variações de uma caixa de seleção preenchida.</span><span class="sxs-lookup"><span data-stu-id="cd38a-268">Checkbox: A phrase list representing variations on a filled in checkbox.</span></span> <span data-ttu-id="cd38a-269">Por exemplo, _X_, _ _X_.</span><span class="sxs-lookup"><span data-stu-id="cd38a-269">For example, _X_, _ _X_.</span></span>
- <span data-ttu-id="cd38a-270">Moeda: principais símbolos internacionais.</span><span class="sxs-lookup"><span data-stu-id="cd38a-270">Currency: Major international symbols.</span></span> <span data-ttu-id="cd38a-271">Por exemplo, $.</span><span class="sxs-lookup"><span data-stu-id="cd38a-271">For example, $.</span></span> 
- <span data-ttu-id="cd38a-272">CC de Email: uma lista de frases com o termo "CC:", muitas vezes encontrado perto dos nomes ou endereços de email de outras pessoas ou grupos para onde a mensagem foi enviada.</span><span class="sxs-lookup"><span data-stu-id="cd38a-272">Email CC: A phrase list with the term 'CC:', often found near the names or email addresses of other people or groups the message was sent to.</span></span>
- <span data-ttu-id="cd38a-273">Data do email: uma lista de frases com o termo 'Enviado em:', geralmente encontrada próximo à data em que o email foi enviado.</span><span class="sxs-lookup"><span data-stu-id="cd38a-273">Email date: A phrase list with the term 'Sent on:', often found near the date the email was sent.</span></span>
- <span data-ttu-id="cd38a-274">Saudação por email: linhas de abertura comuns para emails.</span><span class="sxs-lookup"><span data-stu-id="cd38a-274">Email greeting: Common opening lines for emails.</span></span>
- <span data-ttu-id="cd38a-275">Destinatário do email: uma lista de frases com o termo 'Para:', geralmente encontrada próximo aos nomes ou endereços de email de pessoas ou grupos para os quais a mensagem foi enviada.</span><span class="sxs-lookup"><span data-stu-id="cd38a-275">Email recipient: A phrase list with the term 'To:', often found near the names or email addresses of people or groups the message was sent to.</span></span> 
- <span data-ttu-id="cd38a-276">Remetente do email: uma lista de frases com o termo 'De:', geralmente encontrada próximo ao nome ou endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="cd38a-276">Email sender: A phrase list with the term 'From:', often found near the sender's name or email address.</span></span> 
- <span data-ttu-id="cd38a-277">Assunto do email: uma lista de frases com o termo 'Assunto:', geralmente encontrada próximo ao assunto do email.</span><span class="sxs-lookup"><span data-stu-id="cd38a-277">Email subject: A phrase list with the term 'Subject:', often found near the email's subject.</span></span>

<span data-ttu-id="cd38a-278">A biblioteca de explicações também inclui explicações de *expressões regulares* frequentemente usadas, incluindo:</span><span class="sxs-lookup"><span data-stu-id="cd38a-278">The explanation library also includes commonly used *regular expression* explanations, including:</span></span>

- <span data-ttu-id="cd38a-279">Números de 6 a 17 dígitos: Corresponde qualquer número entre 6 e 17 dígitos.</span><span class="sxs-lookup"><span data-stu-id="cd38a-279">6 to 17 digit numbers: Matches any number from 6 to 17 digits long.</span></span> <span data-ttu-id="cd38a-280">Números de contas bancárias dos EUA se ajustam a esse padrão.</span><span class="sxs-lookup"><span data-stu-id="cd38a-280">US bank account numbers fit this pattern.</span></span>
- <span data-ttu-id="cd38a-281">Endereço de email: Corresponde a um tipo comum de endereço de email como meganb@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="cd38a-281">Email address: Matches a common type of email address like meganb@contoso.com.</span></span>
- <span data-ttu-id="cd38a-282">Número de Identificação de Contribuinte dos EUA: Corresponde a um número de três dígitos que começa com 9 seguido de um número de 6 dígitos, começando com 7 ou 8.</span><span class="sxs-lookup"><span data-stu-id="cd38a-282">US taxpayer ID number: Matches a three-digit number starting with 9 followed by a 6 digit number starting with 7 or 8.</span></span> 
- <span data-ttu-id="cd38a-283">Endereço Web (URL): corresponde ao formato de um endereço Web, começando por http:// ou https://.</span><span class="sxs-lookup"><span data-stu-id="cd38a-283">Web address (URL): Matches the format of a web address, starting with http:// or https://.</span></span>

<span data-ttu-id="cd38a-284">Além disso, a biblioteca de explicações inclui três tipos de modelos automáticos que funcionam com os dados rotulados nos seus arquivos de exemplo:</span><span class="sxs-lookup"><span data-stu-id="cd38a-284">In addition, the explanation library includes three automatic template types that work with the data you've labeled in your example files:</span></span>

- <span data-ttu-id="cd38a-285">Depois do rótulo: As palavras ou caracteres que ocorrem após os rótulos nos arquivos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="cd38a-285">After label: The words or characters that occur after the labels in the example files.</span></span>
- <span data-ttu-id="cd38a-286">Antes do rótulo: As palavras ou caracteres que ocorrem antes dos rótulos nos arquivos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="cd38a-286">Before label: The words or characters that occur before the labels in the example files.</span></span>
- <span data-ttu-id="cd38a-287">Rótulos: Até os primeiros 10 rótulos dos arquivos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="cd38a-287">Labels: Up to the first 10 labels from the example files.</span></span>

<span data-ttu-id="cd38a-288">Para lhe dar um exemplo de como os modelos automáticos funcionam, no arquivo de exemplo a seguir, usaremos o modelo de explicação Antes do rótulo para ajudar a fornecer ao modelo mais informações para obter uma correspondência mais precisa.</span><span class="sxs-lookup"><span data-stu-id="cd38a-288">To give you an example of how automatic templates work, in the following example file, we'll use the Before label explanation template to help give the model more information to get a more accurate match.</span></span>

![Arquivo de exemplo](../media/content-understanding/before-label.png)

<span data-ttu-id="cd38a-290">Quando você seleciona o modelo de explicação Antes do rótulo, ele procura o primeiro conjunto de palavras que aparece antes do rótulo em seus arquivos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="cd38a-290">When you select the Before label explanation template, it will look for the first set of words that appear before the label in your example files.</span></span> <span data-ttu-id="cd38a-291">No exemplo, as palavras identificadas no primeiro arquivo de exemplo são "A partir de".</span><span class="sxs-lookup"><span data-stu-id="cd38a-291">In the example, the words that are identified in the first example file is "As of".</span></span>

![Antes do Modelo do Rótulo](../media/content-understanding/before-label-explanation.png)

<span data-ttu-id="cd38a-293">Você pode selecionar **Adicionar** para criar uma explicação a partir do modelo.</span><span class="sxs-lookup"><span data-stu-id="cd38a-293">You can select **Add** to create an explanation from the template.</span></span>  <span data-ttu-id="cd38a-294">Conforme você adiciona mais arquivos de exemplo, palavras adicionais serão identificadas e adicionadas à lista de frases.</span><span class="sxs-lookup"><span data-stu-id="cd38a-294">As you add more example files, additional words will be identified and added to the phrase list.</span></span>

![Adicionar o rótulo](../media/content-understanding/before-label-add.png)
 
#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="cd38a-296">Para usar um modelo da biblioteca de explicações</span><span class="sxs-lookup"><span data-stu-id="cd38a-296">To use a template from the explanation library</span></span>

1. <span data-ttu-id="cd38a-297">Na seção **Explicações** da página de **Treinamento** do seu modelo, selecione **Novo** e, em seguida, selecione **De um modelo**.</span><span class="sxs-lookup"><span data-stu-id="cd38a-297">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span>

   ![Adicionar Antes do Rótulo](../media/content-understanding/from-template.png)

2.  <span data-ttu-id="cd38a-299">Na página **Modelos de explicação**, selecione a explicação que você deseja usar e, em seguida, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="cd38a-299">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span>

    ![Selecionar um modelo](../media/content-understanding/phone-template.png)

3. <span data-ttu-id="cd38a-301">As informações do modelo que você selecionou são exibidas na página **Criar uma explicação**.</span><span class="sxs-lookup"><span data-stu-id="cd38a-301">The information for the template you selected displays on the **Create an explanation** page.</span></span> <span data-ttu-id="cd38a-302">Se necessário, edite o nome da explicação e adicione ou remova itens da lista de frases.</span><span class="sxs-lookup"><span data-stu-id="cd38a-302">If needed, edit the explanation name and add or remove items from the phrase list.</span></span>  

    ![Editar modelo](../media/content-understanding/phone-template-live.png)

4. <span data-ttu-id="cd38a-304">Quando concluir, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="cd38a-304">When finished, select **Save**.</span></span>