---
title: Personalizar ou criar um novo tipo de informação confidencial
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.custom: ''
ms.assetid: ''
description: Saiba como modificar ou criar novos tipos de informação confidencial do Office 365 para GDPR.
ms.openlocfilehash: 264e310c019c47d1b3109b20fbdd61b323ec5530
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072011"
---
# <a name="customize-or-create-a-new-sensitive-information-type"></a><span data-ttu-id="0e37e-103">Personalizar ou criar um novo tipo de informação confidencial</span><span class="sxs-lookup"><span data-stu-id="0e37e-103">Customize or create a new sensitive information type</span></span>

<span data-ttu-id="0e37e-104">Este artigo fornece três exemplos para demonstrar como modificar ou criar novos tipos de informação confidencial do Office 365 para GDPR.</span><span class="sxs-lookup"><span data-stu-id="0e37e-104">This article provides three examples to demonstrate how to modify or create new Office 365 sensitive information types for GDPR.</span></span>

- <span data-ttu-id="0e37e-105">Modificar um tipo de informação confidencial existente – Número de Cartão de Débito da UE</span><span class="sxs-lookup"><span data-stu-id="0e37e-105">Modify an existing sensitive information type — EU Debit Card Number</span></span>

- <span data-ttu-id="0e37e-106">Criar um novo tipo de informação confidencial – endereço de email</span><span class="sxs-lookup"><span data-stu-id="0e37e-106">Create a new sensitive information type — email address</span></span>

- <span data-ttu-id="0e37e-107">Criar um novo tipo de informação confidencial com o arquivo XML de exemplo – número de cliente da Contoso</span><span class="sxs-lookup"><span data-stu-id="0e37e-107">Create a new sensitive information type with example XML file — Contoso customer number</span></span>

<span data-ttu-id="0e37e-108">Confira também:</span><span class="sxs-lookup"><span data-stu-id="0e37e-108">Also see:</span></span>

- [<span data-ttu-id="0e37e-109">Criar um tipo de informação confidencial personalizado usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e37e-109">Create a custom sensitive information type using PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

- [<span data-ttu-id="0e37e-110">Personalizar um tipo de informação confidencial interno</span><span class="sxs-lookup"><span data-stu-id="0e37e-110">Customize a built-in sensitive information type</span></span>](customize-a-built-in-sensitive-information-type.md)

## <a name="modify-a-sensitive-information-type-to-improve-accuracy"></a><span data-ttu-id="0e37e-111">Modificar um tipo de informação confidencial para melhorar a precisão</span><span class="sxs-lookup"><span data-stu-id="0e37e-111">Modify a sensitive information type to improve accuracy</span></span>

<span data-ttu-id="0e37e-112">Se você estiver usando a Pesquisa de Conteúdo para pesquisar dados pessoais usando tipos de informação confidencial e não estiver recebendo os resultados esperados ou a consulta retornar muitos falsos positivos, considere a possibilidade de modificar o tipo de informação confidencial para se adequar melhor ao seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="0e37e-112">If you’re using Content Search to search for personal data using sensitive information types and you’re not returning the expected results, or the query returns too many false positives, consider modifying the sensitive information type to work better with your environment.</span></span>

<span data-ttu-id="0e37e-p101">A prática recomendada ao criar ou personalizar um tipo de informação confidencial é criar um novo tipo de informação confidencial com base em uma informação existente, dando a ela um nome exclusivo e identificadores. Por exemplo, se quiser ajustar os parâmetros do tipo de informação confidencial do "Número de Cartão de Débito da UE", dê o nome "Cartão de Débito da UE Aprimorado" à sua cópia da regra para diferenciá-la do tipo original.</span><span class="sxs-lookup"><span data-stu-id="0e37e-p101">The best practice when creating or customizing a sensitive information type is to create a new sensitive information type based on an existing one, giving it a unique name and identifiers. For example, if you wish to adjust the parameters of the “EU Debit Card Number” sensitive information type, you could name your copy of that rule “EU Debit Card Enhanced” to distinguish it from the original.</span></span>

<span data-ttu-id="0e37e-p102">No novo tipo de informação confidencial, basta modificar os valores que você deseja alterar para melhorar a precisão. Depois de concluído, carregue seu novo tipo de informação confidencial e crie uma nova regra DLP (ou modifique uma existente) para usar o novo tipo de informação confidencial que você acabou de adicionar. Modificar a precisão de tipos de informação confidencial pode exigir algumas tentativas e erros, portanto, manter uma cópia do tipo original permite recuperá-lo posteriormente, caso isso seja necessário.</span><span class="sxs-lookup"><span data-stu-id="0e37e-p102">In your new sensitive information type, simply modify the values you wish to change to improve its accuracy. Once complete, upload your new sensitive information type and create a new DLP rule (or modify an existing one) to use the new sensitive information type you just added. Modifying the accuracy of sensitive information types might require some trial and error, so maintaining a copy of the original type allows you to fall back to it if required in the future.</span></span>

<span data-ttu-id="0e37e-118">Para personalizar um tipo de informação confidencial:</span><span class="sxs-lookup"><span data-stu-id="0e37e-118">To customize a sensitive information type:</span></span>

1.  <span data-ttu-id="0e37e-119">Exporte o Pacote de Regras da Microsoft existente de tipos de informação confidencial internos no Office 365.</span><span class="sxs-lookup"><span data-stu-id="0e37e-119">Export the existing Microsoft Rule Package of built in sensitive information types in Office 365.</span></span>

2.  <span data-ttu-id="0e37e-120">Renomeie este arquivo XML e abra-o em seu editor de XML favorito.</span><span class="sxs-lookup"><span data-stu-id="0e37e-120">Rename this XML file and open it in your favorite XML editor.</span></span>

3.  <span data-ttu-id="0e37e-121">Isole o tipo de informação confidencial e remova os demais.</span><span class="sxs-lookup"><span data-stu-id="0e37e-121">Isolate the sensitive information type and remove all others.</span></span>

4.  <span data-ttu-id="0e37e-122">Use o PowerShell para gerar dois novos GUIDs para o tipo de informação confidencial que você está modificando.</span><span class="sxs-lookup"><span data-stu-id="0e37e-122">Use PowerShell to generate two new GUIDs for the sensitive information type you are modifying.</span></span>

5.  <span data-ttu-id="0e37e-123">Modifique a ID e outros elementos básicos para que o tipo de informação confidencial seja exclusivo (isso inclui substituir dois GUIDs pelos novos GUIDs gerados).</span><span class="sxs-lookup"><span data-stu-id="0e37e-123">Modify the ID and other basic elements so the sensitive information type is unique (this includes replacing two GUIDs with the new ones you generated).</span></span>

6.  <span data-ttu-id="0e37e-124">Ajuste os requisitos de correspondência para melhorar a precisão.</span><span class="sxs-lookup"><span data-stu-id="0e37e-124">Tune the match requirements to improve accuracy.</span></span>

    1.  <span data-ttu-id="0e37e-125">Modificações de proximidade – Modifique a proximidade do padrão de caracteres para expandir ou reduzir a janela na qual as palavras-chave devem ser encontradas em todos os tipos de informação confidencial.</span><span class="sxs-lookup"><span data-stu-id="0e37e-125">Proximity modifications — Modify the character pattern proximity to expand or shrink the window in which keywords must be found around the sensitive information type.</span></span>

    2.  <span data-ttu-id="0e37e-p103">Modificações de palavras-chave – Adicione palavras-chave a um dos elementos \<Keywords\> para fornecer ao tipo de informação confidencial evidências comprobatórias mais específicas para a pesquisa com o intuito de sinalizar uma correspondência nessa regra. Você também pode remover palavras-chave que estejam gerando falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="0e37e-p103">Keyword modifications — Add keywords to one of the \<Keywords\> element in order to provide our sensitive information type more specific corroborative evidence to search for in order to signal a match on this rule. Or remove keywords that are causing false positives.</span></span>

    3.  <span data-ttu-id="0e37e-128">Modificações de confiança – Modifique a confiança com que o tipo de informação confidencial deverá corresponder aos critérios especificados nessa definição antes de uma correspondência ser sinalizada e relatada.</span><span class="sxs-lookup"><span data-stu-id="0e37e-128">Confidence modifications — Modify the confidence with which the sensitive information type must match the criteria specified in its definition before a match is signaled and reported.</span></span>

7.  <span data-ttu-id="0e37e-129">Carregue o novo tipo de informação confidencial.</span><span class="sxs-lookup"><span data-stu-id="0e37e-129">Upload the new sensitive information type.</span></span>

8.  <span data-ttu-id="0e37e-p104">Repita o rastreamento do conteúdo para identificar informações confidenciais. Confira [Solicitar manualmente o rastreamento e a reindexação de um site](https://support.office.com/pt-BR/article/Manually-request-crawling-and-re-indexing-of-a-site-a-library-or-a-list-9AFA977D-39DE-4321-B4CA-8C7C7E6D264E).</span><span class="sxs-lookup"><span data-stu-id="0e37e-p104">Recrawl your content to identify the sensitive information. See [Manually request crawling and re-indexing of a site](https://support.office.com/pt-BR/article/Manually-request-crawling-and-re-indexing-of-a-site-a-library-or-a-list-9AFA977D-39DE-4321-B4CA-8C7C7E6D264E).</span></span>

## <a name="example-modify-the-eu-debit-card-number-sensitive-information-type"></a><span data-ttu-id="0e37e-132">Exemplo: modificar o tipo de informação confidencial do 'Número de Cartão de Débito da UE'</span><span class="sxs-lookup"><span data-stu-id="0e37e-132">Example: modify the ‘EU Debit Card Number’ sensitive information type</span></span>

<span data-ttu-id="0e37e-p105">Melhorar a precisão das regras de DLP nos sistemas exige testes para detectar um conjunto de dados de exemplo e pode exigir um ajuste aprimorado por meio de testes e modificações repetitivas. Este exemplo demonstra modificações realizadas no tipo de informação confidencial do "Número de Cartão de Débito da UE" para melhorar a precisão.</span><span class="sxs-lookup"><span data-stu-id="0e37e-p105">Improving the accuracy of DLP rules in any system requires testing against a sample data set, and may require fine tuning through repetitive modifications and tests. This example demonstrates modifications to the ‘EU Debit Card Number’ sensitive information type to improve its accuracy.</span></span>

<span data-ttu-id="0e37e-p106">Ao pesquisar um Número de Cartão de Débito da UE em nosso exemplo, a definição do número estará rigorosamente definida como 16 dígitos usando um padrão complexo e estará sujeita à validação de uma soma de verificação. Não será possível alterar esse padrão devido à definição da cadeia de caracteres desse tipo de informação confidencial. No entanto, podemos fazer os seguintes ajustes para aumentar a precisão da forma como o Office 365 DLP localiza esse tipo de informação confidencial no Office 365.</span><span class="sxs-lookup"><span data-stu-id="0e37e-p106">When searching for an EU Debit Card Number in our example, the definition of that number is strictly defined as 16 digits using a complex pattern, and being subject to the validation of a checksum. We cannot alter this pattern due to the string definition of this sensitive information type. However, we can make the following adjustments to improve the accuracy of how Office 365 DLP finds this sensitive information type within Office 365.</span></span>

### <a name="proximity-modification"></a><span data-ttu-id="0e37e-138">Modificação de proximidade</span><span class="sxs-lookup"><span data-stu-id="0e37e-138">Proximity modification</span></span>

<span data-ttu-id="0e37e-p107">Reduziremos a janela modificando o valor patternProximity em nosso elemento \<Entity\> de 300 a 150 caracteres. Isso significa que nossas evidências comprobatórias, ou nossas palavras-chave, devem estar mais próximas do tipo de informação confidencial para sinalizar uma correspondência nessa regra.</span><span class="sxs-lookup"><span data-stu-id="0e37e-p107">We'll shrink the window by modifying the patternProximity value in our \<Entity\> element from 300 to 150 characters. This means that our corroborative evidence, or our keywords, must be closer to our sensitive information type in order to signal a match on this rule.</span></span>

<span data-ttu-id="0e37e-141">\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\></span><span class="sxs-lookup"><span data-stu-id="0e37e-141">\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\></span></span>

### <a name="keyword-modifications"></a><span data-ttu-id="0e37e-142">Modificações de palavras-chave</span><span class="sxs-lookup"><span data-stu-id="0e37e-142">Keyword modifications</span></span>

<span data-ttu-id="0e37e-p108">Algumas palavras-chave podem levar a falsos positivos, por isso, convém removê-las. Veja as palavras-chave neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="0e37e-p108">Some keywords might cause false positives to occur. As a result you might want to remove keywords. Here are the keywords for this example::</span></span>

<span data-ttu-id="0e37e-146">\<Keyword id="Keyword\_card\_terms\_dict"\></span><span class="sxs-lookup"><span data-stu-id="0e37e-146">\<Keyword id="Keyword\_card\_terms\_dict"\></span></span>

<span data-ttu-id="0e37e-147">\<Group\></span><span class="sxs-lookup"><span data-stu-id="0e37e-147">\<Group\></span></span>

<span data-ttu-id="0e37e-148">\<Term\>corporate card\</Term\></span><span class="sxs-lookup"><span data-stu-id="0e37e-148">\<Term\>corporate card\</Term\></span></span>

<span data-ttu-id="0e37e-149">\<Term\>organization card\</Term\></span><span class="sxs-lookup"><span data-stu-id="0e37e-149">\<Term\>organization card\</Term\></span></span>

<span data-ttu-id="0e37e-150">\<Term\>acct nbr\</Term\></span><span class="sxs-lookup"><span data-stu-id="0e37e-150">\<Term\>acct nbr\</Term\></span></span>

<span data-ttu-id="0e37e-151">\<Term\>acct num\</Term\></span><span class="sxs-lookup"><span data-stu-id="0e37e-151">\<Term\>acct num\</Term\></span></span>

<span data-ttu-id="0e37e-152">\<Term\>acct no\</Term\></span><span class="sxs-lookup"><span data-stu-id="0e37e-152">\<Term\>acct no\</Term\></span></span>

<span data-ttu-id="0e37e-153">…</span><span class="sxs-lookup"><span data-stu-id="0e37e-153">…</span></span>

<span data-ttu-id="0e37e-154">\</Group\></span><span class="sxs-lookup"><span data-stu-id="0e37e-154">\</Group\></span></span>

<span data-ttu-id="0e37e-155">\</Keyword\></span><span class="sxs-lookup"><span data-stu-id="0e37e-155">\</Keyword\></span></span>

### <a name="confidence-modifications"></a><span data-ttu-id="0e37e-156">Modificações de confiança</span><span class="sxs-lookup"><span data-stu-id="0e37e-156">Confidence modifications</span></span>

<span data-ttu-id="0e37e-p109">Se você removesse palavras-chave da definição, geralmente desejaria ajustar seu nível de certeza que indica que esse tipo de informação confidencial foi encontrado com a redução desse valor. O nível padrão do tipo de Número do cartão de débito da UE é 85.</span><span class="sxs-lookup"><span data-stu-id="0e37e-p109">If you remove keywords from the definition, you would typically want to adjust how confident you are that this sensitive information type was found by lowering this value. The default level for EU Debit Card Number type is 85.</span></span>

<span data-ttu-id="0e37e-159">\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\></span><span class="sxs-lookup"><span data-stu-id="0e37e-159">\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\></span></span>

<span data-ttu-id="0e37e-160">\<Pattern confidenceLevel="85"\></span><span class="sxs-lookup"><span data-stu-id="0e37e-160">\<Pattern confidenceLevel="85"\></span></span>

<span data-ttu-id="0e37e-161">…</span><span class="sxs-lookup"><span data-stu-id="0e37e-161">…</span></span>

<span data-ttu-id="0e37e-162">\</Pattern\></span><span class="sxs-lookup"><span data-stu-id="0e37e-162">\</Pattern\></span></span>

<span data-ttu-id="0e37e-163">\</Entity\></span><span class="sxs-lookup"><span data-stu-id="0e37e-163">\</Entity\></span></span>

## <a name="create-a-new-custom-sensitive-information-type"></a><span data-ttu-id="0e37e-164">Criar um novo tipo de informação confidencial personalizada</span><span class="sxs-lookup"><span data-stu-id="0e37e-164">Create a new custom sensitive information type</span></span>

<span data-ttu-id="0e37e-165">Para criar um novo tipo de informação confidencial personalizada, comece usando a Pesquisa de Conteúdo:</span><span class="sxs-lookup"><span data-stu-id="0e37e-165">To create a new custom sensitive information type, start by using Content Search to:</span></span>

-   <span data-ttu-id="0e37e-166">Otimizar uma consulta KQL</span><span class="sxs-lookup"><span data-stu-id="0e37e-166">Optimize a KQL query</span></span>

-   <span data-ttu-id="0e37e-167">Ver quais palavras-chave são mais úteis</span><span class="sxs-lookup"><span data-stu-id="0e37e-167">See which keywords are most useful</span></span>

<span data-ttu-id="0e37e-p110">Use esses resultados para criar um novo tipo de informação confidencial e otimize o novo tipo de informação confidencial para seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="0e37e-p110">Use these results to create a new sensitive information type. Then optimize the new sensitive information type for your environment.</span></span>

<span data-ttu-id="0e37e-p111">Observação: vários novos tipos de informação confidencial estarão brevemente disponíveis para dados pessoais de países da UE. Se precisar criar novos tipos de informação confidencial, comece direcionando dados personalizados para seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="0e37e-p111">Note: Many new sensitive information types are coming soon for personal data in EU countries. If you need to create new sensitive information types, begin by targeting data that is custom to your environment.</span></span>

### <a name="step-1--use-kql-queries-and-key-words-to-find-additional-data-in-your-environment"></a><span data-ttu-id="0e37e-172">Etapa 1: Usar consultas KQL e palavras-chave para encontrar dados adicionais em seu ambiente</span><span class="sxs-lookup"><span data-stu-id="0e37e-172">Step 1 — Use KQL queries and key words to find additional data in your environment</span></span>

<span data-ttu-id="0e37e-p112">Talvez seja preciso criar outras consultas para localizar dados pessoais sujeitos à GDPR. A Pesquisa de Conteúdo usa a Keyword Query Language (KQL) para localizar os dados. Não é possível detectar os dados confidenciais mais importantes com precisão usando apenas a KQL sem os tipos de informação confidencial. Portanto, o objetivo é testar e otimizar cadeias de caracteres da KQL usando a Pesquisa de Conteúdo e usá-las para criar e ajustar novos tipos de informação confidencial para alcançar ainda mais precisão.</span><span class="sxs-lookup"><span data-stu-id="0e37e-p112">You might need to create additional queries to find personal data that is subject to GDPR. Content Search uses Keyword Query Language (KQL) to find data. Most sensitive data can’t be accurately detected using just KQL without sensitive information types. So the goal is to test and optimize KQL strings using Content Search and then use these to create and tune new sensitive information types where you can achieve even greater accuracy.</span></span>

<span data-ttu-id="0e37e-177">Use estes recursos para formular e otimizar consultas usando KQL:</span><span class="sxs-lookup"><span data-stu-id="0e37e-177">Use these resources to formulate and optimize queries using KQL:</span></span>

-   [<span data-ttu-id="0e37e-178">Referência de sintaxe (DMC) da Keyword Query Language(KQL)</span><span class="sxs-lookup"><span data-stu-id="0e37e-178">Keyword Query Language (KQL) syntax reference (DMC)</span></span>](https://docs.microsoft.com/pt-BR/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

-   [<span data-ttu-id="0e37e-179">Executar uma Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="0e37e-179">Run a Content Search</span></span>](https://support.office.com/pt-BR/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a) 

<span data-ttu-id="0e37e-p113">A Pesquisa de Conteúdo oferece outro recurso para ajudar você a desenvolver consultas KQL e tipos de informação confidencial – as palavras-chave. Por que usar a lista de palavras-chave? Para ver estatísticas que mostram o número de itens que correspondem a cada palavra-chave, o que pode ajudar a identificar rapidamente quais palavras-chave são mais (e menos) eficientes. Para saber mais sobre as estatísticas de pesquisas, confira [Exibir as estatísticas de palavras-chave dos resultados da Pesquisa de Conteúdo](https://support.office.com/pt-BR/article/View-keyword-statistics-for-Content-Search-results-9701a024-c52e-43f0-b545-9a53478aec04).</span><span class="sxs-lookup"><span data-stu-id="0e37e-p113">Content Search provides another resource to help you develop KQL queries and sensitive information types — keywords. Why use the keyword list? You can get statistics that show how many items match each keyword. This can help you quickly identify which keywords are the most (and least) effective. For more information about search statistics, see [View keyword statistics for Content Search results](https://support.office.com/pt-BR/article/View-keyword-statistics-for-Content-Search-results-9701a024-c52e-43f0-b545-9a53478aec04).</span></span>

<span data-ttu-id="0e37e-p114">As palavras-chave de cada linha são conectadas pelo operador OR na consulta da pesquisa que é criada. Você também pode usar uma frase de palavra-chave (entre parênteses) em uma linha.</span><span class="sxs-lookup"><span data-stu-id="0e37e-p114">Keywords on each row are connected by the OR operator in the search query that's created. You can also use a keyword phrase (surrounded by parentheses) in a row.</span></span>

<span data-ttu-id="0e37e-187">Para saber mais, confira [Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo](https://support.office.com/pt-BR/article/Keyword-queries-and-search-conditions-for-Content-Search-c4639c2e-7223-4302-8e0d-b6e10f1c3be3).</span><span class="sxs-lookup"><span data-stu-id="0e37e-187">For more information, see [Keyword queries and search conditions for Content Search](https://support.office.com/pt-BR/article/Keyword-queries-and-search-conditions-for-Content-Search-c4639c2e-7223-4302-8e0d-b6e10f1c3be3).</span></span>

### <a name="exampleusing-content-search-to-identify-email-addresses"></a><span data-ttu-id="0e37e-188">Exemplo – Usar a Pesquisa de Conteúdo para identificar endereços de email</span><span class="sxs-lookup"><span data-stu-id="0e37e-188">Example—Using Content Search to identify email addresses</span></span>

<span data-ttu-id="0e37e-p115">Os endereços de email são considerados informações confidenciais relacionadas aos assuntos de dados. Isso é um exemplo simples para demonstrar como a Pesquisa de Conteúdo pode ajudar.</span><span class="sxs-lookup"><span data-stu-id="0e37e-p115">Email addresses are considered sensitive information related to data subjects. This is a simple example to demonstrate how Content Search can help.</span></span>

<span data-ttu-id="0e37e-p116">As palavras-chave e o KQL não podem ser usados em conjunto. Use essas ferramentas separadamente para aperfeiçoar sua consulta e determinar as palavras-chave que podem ser úteis para os tipos de informação confidencial.</span><span class="sxs-lookup"><span data-stu-id="0e37e-p116">KQL and keywords can’t be used together. Use these tools separately to hone your query and determine keywords that might be useful in sensitive information types.</span></span>

### <a name="kql-query"></a><span data-ttu-id="0e37e-193">Consulta KQL</span><span class="sxs-lookup"><span data-stu-id="0e37e-193">KQL query</span></span>

<span data-ttu-id="0e37e-194">(^|\\b)([a-zA-Z0-9\_\\-\\.]+)@([a-zA-Z0-9\_\\-\\.]+)\\.([a-zA-Z]{2,5})($|\\b)</span><span class="sxs-lookup"><span data-stu-id="0e37e-194">(^|\\b)([a-zA-Z0-9\_\\-\\.]+)@([a-zA-Z0-9\_\\-\\.]+)\\.([a-zA-Z]{2,5})($|\\b)</span></span>

<span data-ttu-id="0e37e-195">Observações:</span><span class="sxs-lookup"><span data-stu-id="0e37e-195">Notes:</span></span>

-   <span data-ttu-id="0e37e-196">você pode usar NEAR e ONEAR para pesquisas de proximidade.</span><span class="sxs-lookup"><span data-stu-id="0e37e-196">You can use NEAR and ONEAR for proximity searches.</span></span>

-   <span data-ttu-id="0e37e-197">Infelizmente, o KQL não oferece suporte a consultas com a Classe Regex (por exemplo: IdRef="Regex\_email\_address")</span><span class="sxs-lookup"><span data-stu-id="0e37e-197">Unfortunately, KQL doesn’t support queries with the Regex Class (ex: IdRef="Regex\_email\_address")</span></span>

### <a name="keywords"></a><span data-ttu-id="0e37e-198">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="0e37e-198">Keywords</span></span>

<span data-ttu-id="0e37e-p117">Insira cada palavra-chave em uma linha separada. Essas são palavras-chave de exemplo:</span><span class="sxs-lookup"><span data-stu-id="0e37e-p117">Enter each keyword on a separate line. Example keywords:</span></span>

-   <span data-ttu-id="0e37e-201">endereço de email</span><span class="sxs-lookup"><span data-stu-id="0e37e-201">email address</span></span>

-   <span data-ttu-id="0e37e-202">email</span><span class="sxs-lookup"><span data-stu-id="0e37e-202">mail</span></span>

-   <span data-ttu-id="0e37e-203">contato</span><span class="sxs-lookup"><span data-stu-id="0e37e-203">contact</span></span>

-   <span data-ttu-id="0e37e-204">remetente</span><span class="sxs-lookup"><span data-stu-id="0e37e-204">sender</span></span>

-   <span data-ttu-id="0e37e-205">destinatário</span><span class="sxs-lookup"><span data-stu-id="0e37e-205">recipient</span></span>

-   <span data-ttu-id="0e37e-206">cc</span><span class="sxs-lookup"><span data-stu-id="0e37e-206">cc</span></span>

-   <span data-ttu-id="0e37e-207">bcc</span><span class="sxs-lookup"><span data-stu-id="0e37e-207">bcc</span></span>

<span data-ttu-id="0e37e-208">Neste exemplo, você pode perceber que as palavras-chave não são necessárias e geram muitos resultados falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="0e37e-208">In this example, you might learn the keywords are not necessary and produce a lot of false positive results.</span></span>

### <a name="step-2--create-a-new-custom-sensitive-information-type"></a><span data-ttu-id="0e37e-209">Etapa 2 – Criar um novo tipo de informação confidencial personalizada</span><span class="sxs-lookup"><span data-stu-id="0e37e-209">Step 2 — Create a new custom sensitive information type</span></span>

<span data-ttu-id="0e37e-p118">Após usar as consultas KQL e palavras-chave para identificar informações confidenciais, use-as para criar novos tipos de informação confidencial personalizadas. Em muitos casos, você precisará da sofisticação dos tipos de informação confidencial para atingir o nível certo de precisão. Em seguida, use esses tipos de informação confidencial personalizadas com a Pesquisa de Conteúdo em políticas DLP, em outras ferramentas e em outras consultas KQL.</span><span class="sxs-lookup"><span data-stu-id="0e37e-p118">After using KQL queries and keywords to identify sensitive information, use these to create new custom sensitive information types. In many cases, you’ll require the sophistication of sensitive information types to achieve the right level of accuracy. You can then use these custom sensitive information types with Content Search, in DLP policies and other tools, and within other KQL queries.</span></span>

<span data-ttu-id="0e37e-p119">A prática recomendada é criar um novo tipo de informação confidencial com base em um tipo existente. Use o mesmo processo descrito anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="0e37e-p119">The best practice is to create a new sensitive information type based on an existing one. Use the same process described earlier in this article.</span></span>

### <a name="example--create-a-new-sensitive-information-for-email-addresses"></a><span data-ttu-id="0e37e-215">Exemplo – Criar um novo tipo de informação confidencial para endereços de email</span><span class="sxs-lookup"><span data-stu-id="0e37e-215">Example — Create a new sensitive information for email addresses</span></span> 

<span data-ttu-id="0e37e-p120">Por ser simples, vamos continuar a usar o endereço de email como exemplo. A tabela a seguir fornece detalhes sobre as alterações recomendadas para um novo tipo de informação confidencial de email.</span><span class="sxs-lookup"><span data-stu-id="0e37e-p120">We’ll continue with the email address as an example because it’s simple. The following table details the modifications recommended for a new email sensitive information type.</span></span>

<table><span data-ttu-id="0e37e-218">
<thead>
<tr class="header">
<th align="left"><strong>Etapa</strong></span><span class="sxs-lookup"><span data-stu-id="0e37e-218">Step</span></span></th>
<th align="left"><span data-ttu-id="0e37e-219"><strong>Modificação </strong></span><span class="sxs-lookup"><span data-stu-id="0e37e-219"><strong>Modification </strong></span></span></th>
<th align="left"><span data-ttu-id="0e37e-220"><strong>Exemplo de sintaxe XML</strong></span><span class="sxs-lookup"><span data-stu-id="0e37e-220"><strong>Example XML syntax</strong></span></span></th>
</tr><span data-ttu-id="0e37e-221">
</thead>
<tbody>
<tr class="odd">
<td align="left">1</span><span class="sxs-lookup"><span data-stu-id="0e37e-221">1.</span></span></td>
<td align="left"><span data-ttu-id="0e37e-222">Definir a propriedade IdRef</span><span class="sxs-lookup"><span data-stu-id="0e37e-222">Set the IdRef property</span></span>
<p><span data-ttu-id="0e37e-p121">No elemento &lt;Entity&gt;, modifique o elemento &lt;IdMatch&gt; para que sua propriedade idRef seja = a um valor único. Esse valor apontará para um elemento que define nossa expressão regular para localizar endereços de email.</span><span class="sxs-lookup"><span data-stu-id="0e37e-p121">Within the &lt;Entity&gt; element, modify the &lt;IdMatch&gt; element so that its idRef property is = to a unique value. This value will point to an element that defines our regular expression to find email addresses.</span></span></p></td>
<td align="left"><span data-ttu-id="0e37e-225">IdRef=&quot;Regex_email_address&quot;</span><span class="sxs-lookup"><span data-stu-id="0e37e-225">IdRef=&quot;Regex_email_address&quot;</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="0e37e-226">2</span><span class="sxs-lookup"><span data-stu-id="0e37e-226">2</span></span></td>
<td align="left"><p><span data-ttu-id="0e37e-227">Atributo de proximidade</span><span class="sxs-lookup"><span data-stu-id="0e37e-227">Proximity attribute</span></span></p>
<p><span data-ttu-id="0e37e-228">Vamos começar com um valor patternProximity de 300 em nosso elemento &lt;entity&gt;.</span><span class="sxs-lookup"><span data-stu-id="0e37e-228">We'll start with a patternProximity value in our &lt;Entity&gt; element of 300.</span></span></p></td>
<td align="left"><span data-ttu-id="0e37e-229">patternsProximity=&quot;300&quot;</span><span class="sxs-lookup"><span data-stu-id="0e37e-229">patternsProximity=&quot;300&quot;</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="0e37e-230">3</span><span class="sxs-lookup"><span data-stu-id="0e37e-230">3</span></span></td>
<td align="left"><p><span data-ttu-id="0e37e-231">Nível de confiança</span><span class="sxs-lookup"><span data-stu-id="0e37e-231">Confidence level</span></span></p>
<p><span data-ttu-id="0e37e-p122">Defina a propriedade recommendedConfidence com um valor que você sente que representará a confiança de encontrar uma correspondência precisa. Isso provavelmente exigirá testes com um conjunto representativo de dados para obter um resultado preciso. Para uma configuração inicial, defina esse valor como 75.</span><span class="sxs-lookup"><span data-stu-id="0e37e-p122">Set the recommendedConfidence property to a value you feel will represent the confidence of finding an accurate match. This will likely require testing with a representative data set to get an accurate result. As an initial setting, set this value to 75.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e37e-235">recommendedConfidence=&quot;75&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="0e37e-235">recommendedConfidence=&quot;75&quot;&gt;</span></span></p>
<p><span data-ttu-id="0e37e-236">O XML resultante desses três primeiros elementos combinados tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="0e37e-236">The resulting XML for these first three elements combined looks like this:</span></span></p>
<p><span data-ttu-id="0e37e-237">&lt;Entity id=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot; patternsProximity=&quot;300&quot; recommendedConfidence=&quot;75&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="0e37e-237">&lt;Entity id=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot; patternsProximity=&quot;300&quot; recommendedConfidence=&quot;75&quot;&gt;</span></span></p>
<p><span data-ttu-id="0e37e-238">&lt;Pattern confidenceLevel=&quot;75&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="0e37e-238">&lt;Pattern confidenceLevel=&quot;75&quot;&gt;</span></span></p>
<p><span data-ttu-id="0e37e-239">&lt;IdMatch idRef=&quot;Regex_email_address&quot; /&gt;</span><span class="sxs-lookup"><span data-stu-id="0e37e-239">&lt;IdMatch idRef=&quot;Regex_email_address&quot; /&gt;</span></span></p>
<p><span data-ttu-id="0e37e-240">&lt;Any minMatches=&quot;1&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="0e37e-240">&lt;Any minMatches=&quot;1&quot;&gt;</span></span></p>
<p><span data-ttu-id="0e37e-241">&lt;Match idRef=&quot;Keyword_email_terms&quot; /&gt;</span><span class="sxs-lookup"><span data-stu-id="0e37e-241">&lt;Match idRef=&quot;Keyword_email_terms&quot; /&gt;</span></span></p>
<p><span data-ttu-id="0e37e-242">&lt;/Any&gt;</span><span class="sxs-lookup"><span data-stu-id="0e37e-242">&lt;/Any&gt;</span></span></p>
<p><span data-ttu-id="0e37e-243">&lt;/Pattern&gt;</span><span class="sxs-lookup"><span data-stu-id="0e37e-243">&lt;/Pattern&gt;</span></span></p>
<p><span data-ttu-id="0e37e-244">&lt;/Entity&gt;</span><span class="sxs-lookup"><span data-stu-id="0e37e-244">&lt;/Entity&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="0e37e-245">4</span><span class="sxs-lookup"><span data-stu-id="0e37e-245">4</span></span></td>
<td align="left"><p><span data-ttu-id="0e37e-246">Elemento Regex</span><span class="sxs-lookup"><span data-stu-id="0e37e-246">Regex element</span></span></p>
<p><span data-ttu-id="0e37e-247">Adicione um novo elemento &lt;Regex&gt; logo abaixo dos elementos &lt;Entity&gt; que definem a expressão regular usada para identificar os endereços de email.</span><span class="sxs-lookup"><span data-stu-id="0e37e-247">Add a new &lt;Regex&gt; element immediately be below the &lt;Entity&gt; elements that defines the regular expression used to identify email addresses.</span></span></p></td>
<td align="left"><span data-ttu-id="0e37e-248">&lt;Regex id=&quot;Endereço_email_Regex&quot;&gt;(^|\b)([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})($|\b)&lt;/Regex&gt;</span><span class="sxs-lookup"><span data-stu-id="0e37e-248">&lt;Regex id=&quot;Regex_email_address&quot;&gt;(^|\b)([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})($|\b)&lt;/Regex&gt;</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="0e37e-249">5</span><span class="sxs-lookup"><span data-stu-id="0e37e-249">5</span></span></td>
<td align="left"><p><span data-ttu-id="0e37e-250">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="0e37e-250">Keywords</span></span></p>
<p><span data-ttu-id="0e37e-p123">Adicione um novo elemento &lt;Keyword&gt; abaixo do elemento &lt;Regex&gt; que define a lista de palavras-chave relacionadas dos endereços de email. Verifique se o valor de id do elemento &lt;Keyword&gt; corresponde ao valor &lt;Match idRef&gt; no elemento &lt;Entity&gt;&lt;Pattern&gt;. Se necessário, você pode continuar a adicionar suas próprias palavras-chave.</span><span class="sxs-lookup"><span data-stu-id="0e37e-p123">Add a new &lt;Keyword&gt; element below the &lt;Regex&gt; element that defines list of email address related keywords. Ensure that the id value for the &lt;Keyword&gt; element matches the &lt;Match idRef&gt; value in the &lt;Entity&gt;&lt;Pattern&gt; element. You may continue to add your own keywords if needed.</span></span></p>
<p><span data-ttu-id="0e37e-p124">Há palavras-chave que provavelmente não precisarão ser incluídas em um tipo de informação confidencial de email. Elas são fornecidas como exemplo.</span><span class="sxs-lookup"><span data-stu-id="0e37e-p124">Keywords are likely not necessary to include in an email sensitive information type. These are provided as an example.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e37e-256">&lt;Keyword id=&quot;Keyword_email_terms&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="0e37e-256">&lt;Keyword id=&quot;Keyword_email_terms&quot;&gt;</span></span></p>
<p><span data-ttu-id="0e37e-257">&lt;Group&gt;</span><span class="sxs-lookup"><span data-stu-id="0e37e-257">&lt;Group&gt;</span></span></p>
<p><span data-ttu-id="0e37e-258">&lt;Term&gt;email&lt;/Term&gt;</span><span class="sxs-lookup"><span data-stu-id="0e37e-258">&lt;Term&gt;email&lt;/Term&gt;</span></span></p>
<p><span data-ttu-id="0e37e-259">&lt;Term&gt;email address&lt;/Term&gt;</span><span class="sxs-lookup"><span data-stu-id="0e37e-259">&lt;Term&gt;email address&lt;/Term&gt;</span></span></p>
<p><span data-ttu-id="0e37e-260">&lt;Term&gt;contact&lt;/Term&gt;</span><span class="sxs-lookup"><span data-stu-id="0e37e-260">&lt;Term&gt;contact&lt;/Term&gt;</span></span></p>
<p><span data-ttu-id="0e37e-261">&lt;/Group&gt;</span><span class="sxs-lookup"><span data-stu-id="0e37e-261">&lt;/Group&gt;</span></span></p>
<p><span data-ttu-id="0e37e-262">&lt;/Keyword&gt;</span><span class="sxs-lookup"><span data-stu-id="0e37e-262">&lt;/Keyword&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="0e37e-263">6</span><span class="sxs-lookup"><span data-stu-id="0e37e-263">6</span></span></td>
<td align="left"><p><span data-ttu-id="0e37e-264">Elemento LocalizedStrings</span><span class="sxs-lookup"><span data-stu-id="0e37e-264">LocalizedStrings element</span></span></p>
<p><span data-ttu-id="0e37e-265">No elemento &lt;LocalizedStrings&gt;&lt;Resource&gt;, verifique você se tem um nome exclusivo para identificar seu tipo de informação confidencial.</span><span class="sxs-lookup"><span data-stu-id="0e37e-265">In the &lt;LocalizedStrings&gt;&lt;Resource&gt; element ensure that you have a unique name that identifies your sensitive information type.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e37e-266">&lt;LocalizedStrings&gt;</span><span class="sxs-lookup"><span data-stu-id="0e37e-266">&lt;LocalizedStrings&gt;</span></span></p>
<p><span data-ttu-id="0e37e-267">&lt;Resource idRef=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="0e37e-267">&lt;Resource idRef=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot;&gt;</span></span></p>
<p><span data-ttu-id="0e37e-268">&lt;Name default=&quot;true&quot; langcode=&quot;pt-br&quot;&gt;Endereço de Email&lt;/Name&gt;</span><span class="sxs-lookup"><span data-stu-id="0e37e-268">&lt;Name default=&quot;true&quot; langcode=&quot;en-us&quot;&gt;Email Address&lt;/Name&gt;</span></span></p>
<p><span data-ttu-id="0e37e-269">&lt;Description default=&quot;true&quot; langcode=&quot;pt-br&quot;&gt;Detecta endereços de email.&lt;/Description&gt;</span><span class="sxs-lookup"><span data-stu-id="0e37e-269">&lt;Description default=&quot;true&quot; langcode=&quot;en-us&quot;&gt;Detects email addresses.&lt;/Description&gt;</span></span></p>
<p><span data-ttu-id="0e37e-270">&lt;/Resource&gt;</span><span class="sxs-lookup"><span data-stu-id="0e37e-270">&lt;/Resource&gt;</span></span></p>
<p><span data-ttu-id="0e37e-271">&lt;/LocalizedStrings&gt;</span><span class="sxs-lookup"><span data-stu-id="0e37e-271">&lt;/LocalizedStrings&gt;</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="create-a-new-sensitive-information-type-with-example-powershell-and-xml-file--contoso-customer-number"></a><span data-ttu-id="0e37e-272">Criar um novo tipo de informação confidencial com o exemplo do PowerShell e do arquivo XML - número de cliente da Contoso</span><span class="sxs-lookup"><span data-stu-id="0e37e-272">Create a new sensitive information type with example PowerShell and XML file — Contoso customer number</span></span>

<span data-ttu-id="0e37e-p125">A Contoso usa um Número de cliente da Contoso (CCN) para identificar cada cliente em seu banco de dados do cliente. Um CCN tem a seguinte taxonomia:</span><span class="sxs-lookup"><span data-stu-id="0e37e-p125">Contoso uses a Contoso Customer Number (CCN) to identify each customer in their customer database. A CCN consists of the following taxonomy:</span></span>

-   <span data-ttu-id="0e37e-p126">Dois dígitos para representar o ano em que o registro foi criado. A Contoso foi fundada em 2002, portanto, o valor mais antigo possível seria 02.</span><span class="sxs-lookup"><span data-stu-id="0e37e-p126">Two digits to represent the year that the record was created. Contoso was founded in 2002; therefore, the earliest possible value would be 02.</span></span>

-   <span data-ttu-id="0e37e-p127">Três dígitos para representar o órgão responsável pela criação do registro. O intervalo de valores possível do órgão vai do 000 ao 999.</span><span class="sxs-lookup"><span data-stu-id="0e37e-p127">Three digits to represent the partner agency that created the record. Possible agency values range from 000 to 999.</span></span>

-   <span data-ttu-id="0e37e-p128">Um caractere alfabético para representar o ramo de atividade. Os valores possíveis vão de A a Z e não devem diferenciar maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0e37e-p128">An alpha character to represent the line of business. Possible values are a-z and should be case insensitive.</span></span>

-   <span data-ttu-id="0e37e-p129">Um número de série de quatro dígitos. O intervalo de valores possível de um número de série que vai de 0000 a 9999.</span><span class="sxs-lookup"><span data-stu-id="0e37e-p129">A four-digit serial number. Possible serial number values range from 0000 to 9999.</span></span>

<span data-ttu-id="0e37e-283">Exemplos de CCNs:</span><span class="sxs-lookup"><span data-stu-id="0e37e-283">Example CCNs:</span></span>

> <span data-ttu-id="0e37e-284">15080P9562</span><span class="sxs-lookup"><span data-stu-id="0e37e-284">15080P9562</span></span>
>
> <span data-ttu-id="0e37e-285">14040O1119</span><span class="sxs-lookup"><span data-stu-id="0e37e-285">14040O1119</span></span>
>
> <span data-ttu-id="0e37e-286">15020J8317</span><span class="sxs-lookup"><span data-stu-id="0e37e-286">15020J8317</span></span>
>
> <span data-ttu-id="0e37e-287">14050E2330</span><span class="sxs-lookup"><span data-stu-id="0e37e-287">14050E2330</span></span>
>
> <span data-ttu-id="0e37e-288">16050E2166</span><span class="sxs-lookup"><span data-stu-id="0e37e-288">16050E2166</span></span>
>
> <span data-ttu-id="0e37e-289">17040O1118</span><span class="sxs-lookup"><span data-stu-id="0e37e-289">17040O1118</span></span>

<span data-ttu-id="0e37e-290">A Contoso sempre faz referência aos clientes usando um CCN nas correspondências interna e externa, em documentos, etc. A empresa deseja criar um tipo de informação confidencial personalizado para detectar o uso do CCN no Office 365 e assim aplicar proteção no uso desse formulário de dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="0e37e-290">Contoso always refers to customers by using a CCN in internal correspondence, external correspondence, documents, etc. They would like to create a custom sensitive information type to detect the use of CCN in Office 365 so that they may apply protection to the use of this form of personal data.</span></span>

### <a name="create-a-new-sensitive-information-type-for-contoso-customer-number"></a><span data-ttu-id="0e37e-291">Criar um novo tipo de informação confidencial para o número de cliente da Contoso</span><span class="sxs-lookup"><span data-stu-id="0e37e-291">Create a new sensitive information type for Contoso customer number</span></span>

<table><span data-ttu-id="0e37e-292">
<thead>
<tr class="header">
<th align="left"><strong>Etapa</strong></span><span class="sxs-lookup"><span data-stu-id="0e37e-292">Step</span></span></th>
<th align="left"><span data-ttu-id="0e37e-293"><strong>Ação</strong></span><span class="sxs-lookup"><span data-stu-id="0e37e-293"><strong>Action </strong></span></span></th>
<th align="left"><span data-ttu-id="0e37e-294"><strong>Resultado</strong></span><span class="sxs-lookup"><span data-stu-id="0e37e-294"><strong>Result</strong></span></span></th>
</tr><span data-ttu-id="0e37e-295">
</thead>
<tbody>
<tr class="odd">
<td align="left">1</span><span class="sxs-lookup"><span data-stu-id="0e37e-295">1.</span></span></td>
<td align="left"><span data-ttu-id="0e37e-296">A Contoso usa o PowerShell e a Pesquisa de Conteúdo para encontrar documentos que correspondem a um conjunto de exemplos de CCNs.</span><span class="sxs-lookup"><span data-stu-id="0e37e-296">Contoso uses PowerShell and Content Search to find documents that match an example set of CCNs.</span></span></td>
<td align="left">

<p><span data-ttu-id="0e37e-297">#Conectar-se ao Centro de Conformidade e Segurança do Office 365</span><span class="sxs-lookup"><span data-stu-id="0e37e-297">#Connect to Office 365 Security &amp; Compliance Center</span></span></p>
<p><span data-ttu-id="0e37e-298">$adminUser = &quot;davib@contoso.com&quot;</span><span class="sxs-lookup"><span data-stu-id="0e37e-298">$adminUser = &quot;alland@contoso.com&quot;</span></span></p>
<p><span data-ttu-id="0e37e-299">Connect-IPPSSession -UserPrincipalName $adminUser</span><span class="sxs-lookup"><span data-stu-id="0e37e-299">Connect-IPPSSession -UserPrincipalName $adminUser</span></span></p>
<p><span data-ttu-id="0e37e-300">#Criar e iniciar pesquisa de dados de exemplo</span><span class="sxs-lookup"><span data-stu-id="0e37e-300">#Create &amp; start search for sample data</span></span></p>
<p><span data-ttu-id="0e37e-301">$searchName = &quot;Exemplo de Pesquisa de informações do cliente&quot;</span><span class="sxs-lookup"><span data-stu-id="0e37e-301">$searchName = &quot;Sample Customer Information Search&quot;</span></span></p>
<p><span data-ttu-id="0e37e-302">$searchQuery = &quot;15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118&quot;</span><span class="sxs-lookup"><span data-stu-id="0e37e-302">$searchQuery = &quot;15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118&quot;</span></span></p>
<p><span data-ttu-id="0e37e-303">New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery</span><span class="sxs-lookup"><span data-stu-id="0e37e-303">New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery</span></span></p>
<p><span data-ttu-id="0e37e-304">Start-ComplianceSearch -Identity $searchName</span><span class="sxs-lookup"><span data-stu-id="0e37e-304">Start-ComplianceSearch -Identity $searchName</span></span></p>
</td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="0e37e-305">2</span><span class="sxs-lookup"><span data-stu-id="0e37e-305">2</span></span></td>
<td align="left"><span data-ttu-id="0e37e-p130">A Contoso analisa os resultados. Todas as vezes que o CCN foi usado, uma data com formato da UE foi utilizada e uma dessas palavras-chave também foi usada em cerca de 300 caracteres.</span><span class="sxs-lookup"><span data-stu-id="0e37e-p130">Contoso analyzes the results. Every time the CCN was used, an EU formatted date was used and one of these keywords were also used within a proximity of 300 characters.</span></span></td>
<td align="left"><span data-ttu-id="0e37e-308">número de cliente, núm de cliente, n.º de cliente, n.cliente, cliente da Contoso</span><span class="sxs-lookup"><span data-stu-id="0e37e-308">customer number, customer no, customer #, customer#, Contoso customer</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="0e37e-309">3</span><span class="sxs-lookup"><span data-stu-id="0e37e-309">3</span></span></td>
<td align="left"><span data-ttu-id="0e37e-310">A Contoso desenvolveu o seguinte padrão de Expressão Regular (RegEx) para identificar seu CCN.</span><span class="sxs-lookup"><span data-stu-id="0e37e-310">Contoso developed the following Regular Expression (RegEx) pattern to identify their CCN.</span></span></td>
<td align="left"><span data-ttu-id="0e37e-311">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</span><span class="sxs-lookup"><span data-stu-id="0e37e-311">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="0e37e-312">4</span><span class="sxs-lookup"><span data-stu-id="0e37e-312">4</span></span></td>
<td align="left"><span data-ttu-id="0e37e-313">A Contoso desenvolveu o seguinte padrão de Expressão Regular (RegEx) para identificar datas com formatos da UE usadas por suas diversas subsidiárias.</span><span class="sxs-lookup"><span data-stu-id="0e37e-313">Contoso developed the following Regular Expression (RegEx) pattern to identify EU dates in the formats used by their various subsidiaries.</span></span></td>
<td align="left">
````xml
(0?[1-9]|[12][0-9]|3[0-1])[\/-](0?[1-9]|1[0-2]|j\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)?|‌ feb(ruary|ruari|rero|braio|ruar|br)?|f\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\x00e4rz|maart|‌ apr(ile|il)?|abr(il)?|avril|may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|‌ oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)?|nov(ember|iembre|embre|embro)?|dec(ember)?|‌ dic(iembre|embre)?|dez(ember|embro)?|d\x00e9c(embre)?)[ \/-](19|20)?[0-9]{2}
````
</td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="0e37e-314">5</span><span class="sxs-lookup"><span data-stu-id="0e37e-314">5</span></span></td>
<td align="left"><span data-ttu-id="0e37e-315">A Contoso usa o PowerShell para gerar três GUIDs exclusivos.</span><span class="sxs-lookup"><span data-stu-id="0e37e-315">Contoso uses PowerShell to generate three unique GUIDs.</span></span></td>
<td align="left"><p><span data-ttu-id="0e37e-316">#Gerar um GUID exclusivo para RulePack Id, Publisher Id e Entity Id</span><span class="sxs-lookup"><span data-stu-id="0e37e-316">#Generate a unique GUID for RulePack Id, Publisher Id, and Entity Id</span></span></p>
<p>[guid]::NewGuid().Guid</p>
<p>[guid]::NewGuid().Guid</p>
<p>[guid]::NewGuid().Guid</p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="0e37e-317">6</span><span class="sxs-lookup"><span data-stu-id="0e37e-317">6</span></span></td>
<td align="left"><span data-ttu-id="0e37e-318">A Contoso define os seguintes parâmetros para a regra de tipo de item confidencial.</span><span class="sxs-lookup"><span data-stu-id="0e37e-318">Contoso defines the following parameters for their sensitive item type rule.</span></span></td>
<td align="left"><p><span data-ttu-id="0e37e-319">Nome: Número de cliente da Contoso (CCN)</span><span class="sxs-lookup"><span data-stu-id="0e37e-319">Name: Contoso Customer Number (CCN)</span></span></p>
<p><span data-ttu-id="0e37e-320">Descrição: o Número de cliente da Contoso (CCN) que procura outras palavras-chave e datas com o formato da UE</span><span class="sxs-lookup"><span data-stu-id="0e37e-320">Description: Contoso Customer Number (CCN) that looks for additional keywords and EU formatted date</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="0e37e-321">7</span><span class="sxs-lookup"><span data-stu-id="0e37e-321">7</span></span></td>
<td align="left"><span data-ttu-id="0e37e-322">A Contoso cria um arquivo XML de um novo tipo de informação confidencial usado para detectar um Número de cliente da Contoso (CCN) e salva-o em um sistema de arquivos local como C:\Scripts\ContosoCCN.xml com codificação UTF-8.</span><span class="sxs-lookup"><span data-stu-id="0e37e-322">Contoso creates an XML file for a new sensitive information type to detect a Contoso Customer Number (CCN) and saves this to a local file system as C:\Scripts\ContosoCCN.xml in with UTF-8 encoding.</span></span></td>
<td align="left"><span data-ttu-id="0e37e-323">Veja o arquivo XML abaixo desta tabela.</span><span class="sxs-lookup"><span data-stu-id="0e37e-323">See the XML file below this table.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="0e37e-324">8</span><span class="sxs-lookup"><span data-stu-id="0e37e-324">8</span></span></td>
<td align="left"><span data-ttu-id="0e37e-325">A Contoso cria o tipo de informação confidencial personalizada com o seguinte PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e37e-325">Contoso creates the custom sensitive information type with the following PowerShell.</span></span></td>
<td align="left"><p><span data-ttu-id="0e37e-326">#Conectar-se ao Centro de Conformidade e Segurança do Office 365</span><span class="sxs-lookup"><span data-stu-id="0e37e-326">#Connect to Office 365 Security &amp; Compliance Center</span></span></p>
<p><span data-ttu-id="0e37e-327">$adminUser = &quot;davib@contoso.com&quot;</span><span class="sxs-lookup"><span data-stu-id="0e37e-327">$adminUser = &quot;alland@contoso.com&quot;</span></span></p>
<p><span data-ttu-id="0e37e-328">Connect-IPPSSession -UserPrincipalName $adminUser</span><span class="sxs-lookup"><span data-stu-id="0e37e-328">Connect-IPPSSession -UserPrincipalName $adminUser</span></span></p>
<p><span data-ttu-id="0e37e-329">#Criar novo tipo de informação confidencial</span><span class="sxs-lookup"><span data-stu-id="0e37e-329">#Create new Sensitive Information Type</span></span></p>
<p><span data-ttu-id="0e37e-330">New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path &quot;C:\Scripts\ContosoCCN.xml&quot; -Encoding Byte -ReadCount 0)</span><span class="sxs-lookup"><span data-stu-id="0e37e-330">New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path &quot;C:\Scripts\ContosoCCN.xml&quot; -Encoding Byte -ReadCount 0)</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="example-xml-file-for-the-new-sensitive-information-type-step-7"></a><span data-ttu-id="0e37e-331">Exemplo de arquivo XML para o novo tipo de informação confidencial (etapa 7)</span><span class="sxs-lookup"><span data-stu-id="0e37e-331">Example XML file for the new sensitive information type (step 7)</span></span>
```xml
\<?xml version="1.0" encoding="utf-8"?\>

\<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce"\>

\<RulePack id="130ae63b-a91e-4a12-9e02-a90e36a83d7f"\>

\<Version major="1" minor="0" build="0" revision="0" /\>

\<Publisher id="47148982-defd-42a1-890a-7b9472099f1f" /\>

\<Details defaultLangCode="en"\>

\<LocalizedDetails langcode="en"\>

\<PublisherName\>Contoso Ltd.\</PublisherName\>

\<Name\>Contoso Rule Package\</Name\>

\<Description\>Defines Contoso's custom set of classification rules\</Description\>

\</LocalizedDetails\>

\</Details\>

\</RulePack\>

\<Rules\>

\<!-- Contoso Customer Number (CCN) --\>

\<Entity id="a91f9a2e-6cfc-4622-8c5d-954875aa5b2b" patternsProximity="300" recommendedConfidence="85"\>

\<Pattern confidenceLevel="85"\>

\<IdMatch idRef="Regex\_contoso\_ccn" /\>

\<Match idRef="Keyword\_contoso\_ccn" /\>

\<Match idRef="Regex\_eu\_date" /\>

\</Pattern\>

\</Entity\>

\<Regex id="Regex\_contoso\_ccn"\>[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}\</Regex\>

\<Keyword id="Keyword\_contoso\_ccn"\>

\<Group matchStyle="word"\>

\<Term caseSensitive="false"\>customer number\</Term\>

\<Term caseSensitive="false"\>customer no\</Term\>

\<Term caseSensitive="false"\>customer \#\</Term\>

\<Term caseSensitive="false"\>customer\#\</Term\>

\<Term caseSensitive="false"\>Contoso customer\</Term\>

\</Group\>

\</Keyword\>

\<Regex id="Regex\_eu\_date"\> (0?[1-9]|[12][0-9]|3[0-1])[\\/-](0?[1-9]|1[0-2]|j\\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)?‌ |feb(ruary|ruari|rero|braio|ruar|br)?|f\\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\\x00e4rz|maart‌|apr(ile|il)?|abr(il)?|avril‌ |may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)?‌ |nov(ember|iembre|embre|embro)?|dec(ember)?|dic(iembre|embre)?|dez(ember|embro)?|d\\x00e9c(embre)?)[ \\/-](19|20)?[0-9]{2}\</Regex\>

\<LocalizedStrings\>

\<Resource idRef="a91f9a2e-6cfc-4622-8c5d-954875aa5b2b"\>

\<Name default="true" langcode="en-us"\>Contoso Customer Number (CCN)\</Name\>

\<Description default="true" langcode="en-us"\>Contoso Customer Number (CCN) that looks for additional keywords and EU formatted date\</Description\>

\</Resource\>

\</LocalizedStrings\>

\</Rules\>

\</RulePackage\>
```
