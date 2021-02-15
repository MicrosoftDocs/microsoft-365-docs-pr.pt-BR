---
title: Saiba mais sobre classificadores treináveis
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Um classificador de treinamento do Microsoft 365 é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo, dando a ele exemplos positivos e negativos para olhar. Depois que o classificador for treinado, confirme se seus resultados são precisos. Em seguida, use-o para pesquisar o conteúdo da sua organização e classificá-lo para aplicar rótulos de retenção ou sensibilidade ou incluí-lo em políticas de retenção ou prevenção contra perda de dados (DLP).
ms.openlocfilehash: 0e5f712b76af2fba3d456997a47352773d92d766
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49759895"
---
# <a name="learn-about-trainable-classifiers"></a><span data-ttu-id="e936e-105">Saiba mais sobre classificadores treináveis</span><span class="sxs-lookup"><span data-stu-id="e936e-105">Learn about trainable classifiers</span></span>

<span data-ttu-id="e936e-106">Classificar e rotular o conteúdo para que ele possa ser protegido e manipulado corretamente é o ponto de partida para a disciplina de proteção de informações.</span><span class="sxs-lookup"><span data-stu-id="e936e-106">Classifying and labeling content so it can be protected and handled properly is the starting place for the information protection discipline.</span></span> <span data-ttu-id="e936e-107">O Microsoft 365 tem três maneiras de classificar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e936e-107">Microsoft 365 has three ways to classify content.</span></span>

## <a name="manually"></a><span data-ttu-id="e936e-108">Manualmente</span><span class="sxs-lookup"><span data-stu-id="e936e-108">Manually</span></span>

<span data-ttu-id="e936e-109">Esse método requer críticas e ações humanas.</span><span class="sxs-lookup"><span data-stu-id="e936e-109">This method requires human judgment and action.</span></span> <span data-ttu-id="e936e-110">Um administrador pode usar os rótulos pré-existentes e tipos de informações confidenciais ou criar seus próprios e publicá-los.</span><span class="sxs-lookup"><span data-stu-id="e936e-110">An admin may either use the pre-existing labels and sensitive information types or create their own and then publish them.</span></span> <span data-ttu-id="e936e-111">Os usuários e administradores os aplicam ao conteúdo à medida que o encontram.</span><span class="sxs-lookup"><span data-stu-id="e936e-111">Users and admins apply them to content as they encounter it.</span></span> <span data-ttu-id="e936e-112">Em seguida, você pode proteger o conteúdo e gerenciar sua disposição.</span><span class="sxs-lookup"><span data-stu-id="e936e-112">You can then protect the content and manage its disposition.</span></span>

## <a name="automated-pattern-matching"></a><span data-ttu-id="e936e-113">Correspondência automatizada de padrões</span><span class="sxs-lookup"><span data-stu-id="e936e-113">Automated pattern matching</span></span>

<span data-ttu-id="e936e-114">Essa categoria de mecanismos de classificação inclui localizar conteúdo por:</span><span class="sxs-lookup"><span data-stu-id="e936e-114">This category of classification mechanisms include finding content by:</span></span>

- <span data-ttu-id="e936e-115">Palavras-chave ou valores de metadados (linguagem de consulta de palavra-chave).</span><span class="sxs-lookup"><span data-stu-id="e936e-115">Keywords or metadata values (keyword query language).</span></span>
- <span data-ttu-id="e936e-116">Usando padrões identificados anteriormente de informações confidenciais, como seguro social, cartão de crédito ou números de contas [bancárias (definições de](sensitive-information-type-entity-definitions.md)entidade de tipo de informação confidenciais).</span><span class="sxs-lookup"><span data-stu-id="e936e-116">Using previously identified patterns of sensitive information like social security, credit card or bank account numbers [(Sensitive information type entity definitions)](sensitive-information-type-entity-definitions.md).</span></span>
- <span data-ttu-id="e936e-117">Reconhecer um item porque é uma variação em um modelo [(impressão digital de documento).](document-fingerprinting.md)</span><span class="sxs-lookup"><span data-stu-id="e936e-117">Recognizing an item because it's a variation on a template [(document finger printing)](document-fingerprinting.md).</span></span>
- <span data-ttu-id="e936e-118">Usando a presença de cadeias de caracteres [exatas (exact data match)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="e936e-118">Using the presence of exact strings [(exact data match)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

<span data-ttu-id="e936e-119">Os rótulos de retenção e sensibilidade podem ser aplicados automaticamente para disponibilizar o conteúdo para uso na prevenção de perda de dados [(DLP)](data-loss-prevention-policies.md) e políticas de aplicação automática para rótulos de [retenção.](apply-retention-labels-automatically.md)</span><span class="sxs-lookup"><span data-stu-id="e936e-119">Sensitivity and retention labels can then be automatically applied to make the content available for use in [data loss prevention (DLP)](data-loss-prevention-policies.md) and [auto-apply polices for retention labels](apply-retention-labels-automatically.md).</span></span>

## <a name="classifiers"></a><span data-ttu-id="e936e-120">Classificadores</span><span class="sxs-lookup"><span data-stu-id="e936e-120">Classifiers</span></span>

<span data-ttu-id="e936e-121">Esse método de classificação é particularmente adequado ao conteúdo que não é facilmente identificado pelos métodos de correspondência de padrões manuais ou automatizados.</span><span class="sxs-lookup"><span data-stu-id="e936e-121">This classification method is particularly well suited to content that isn't easily identified by either the manual or automated pattern matching methods.</span></span> <span data-ttu-id="e936e-122">Esse método de classificação é mais sobre o treinamento de um classificador para identificar um item com base no que é o item, não por elementos que estão no item (correspondência de padrões).</span><span class="sxs-lookup"><span data-stu-id="e936e-122">This method of classification is more about training a classifier to identify an item based on what the item is, not by elements that are in the item (pattern matching).</span></span> <span data-ttu-id="e936e-123">Um classificador aprende a identificar um tipo de conteúdo analisando centenas de exemplos do conteúdo que você tem interesse em classificar.</span><span class="sxs-lookup"><span data-stu-id="e936e-123">A classifier learns how to identify a type of content by looking at hundreds of examples of the content you're interested in classifying.</span></span> <span data-ttu-id="e936e-124">Você começa alimentando exemplos que definitivamente estão na categoria.</span><span class="sxs-lookup"><span data-stu-id="e936e-124">You start by feeding it examples that are definitely in the category.</span></span> <span data-ttu-id="e936e-125">Depois de processá-los, você o testará, dando a ele uma mistura de exemplos correspondentes e não correspondentes.</span><span class="sxs-lookup"><span data-stu-id="e936e-125">Once it processes those, you test it by giving it a mix of both matching and non-matching examples.</span></span> <span data-ttu-id="e936e-126">Em seguida, o classificador faz previsões sobre se um determinado item se enquadra na categoria que você está criando.</span><span class="sxs-lookup"><span data-stu-id="e936e-126">The classifier then makes predictions as to whether any given item falls into the category you're building.</span></span> <span data-ttu-id="e936e-127">Em seguida, confirme seus resultados, ordenando os verdadeiros positivos, verdadeiros negativos, falsos positivos e falsos negativos para ajudar a aumentar a precisão de suas previsões.</span><span class="sxs-lookup"><span data-stu-id="e936e-127">You then confirm its results, sorting out the true positives, true negatives, false positives, and false negatives to help increase the accuracy of its predictions.</span></span> 

<span data-ttu-id="e936e-128">Quando você publica o classificador, ele classifica os itens em locais como SharePoint Online, Exchange e OneDrive e classifica o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e936e-128">When you publish the classifier, it sorts through items in locations like SharePoint Online, Exchange, and OneDrive, and classifies the content.</span></span> <span data-ttu-id="e936e-129">Depois de publicar o classificador, você pode continuar a treiná-lo usando um processo de feedback semelhante ao processo de treinamento inicial.</span><span class="sxs-lookup"><span data-stu-id="e936e-129">After you publish the classifier, you can continue to train it using a feedback process that is similar to the initial training process.</span></span>

### <a name="where-you-can-use-trainable-classifiers"></a><span data-ttu-id="e936e-130">Onde você pode usar classificadores de treinamento</span><span class="sxs-lookup"><span data-stu-id="e936e-130">Where you can use trainable classifiers</span></span>
<span data-ttu-id="e936e-131">Os classificadores integrados e os classificadores de treinamento estão disponíveis como uma condição para rotular automaticamente o [Office](apply-sensitivity-label-automatically.md)com rótulos de [sensibilidade,](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) aplicar automaticamente a política de rótulo de retenção com base em uma condição e na conformidade de [comunicação.](communication-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="e936e-131">Both built-in classifiers and trainable classifiers are available as a condition for [Office autolabeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [communication compliance](communication-compliance.md).</span></span> 

<span data-ttu-id="e936e-132">Os rótulos de sensibilidade podem usar classificadores como condições, consulte Aplicar um [rótulo de sensibilidade ao conteúdo automaticamente.](apply-sensitivity-label-automatically.md)</span><span class="sxs-lookup"><span data-stu-id="e936e-132">Sensitivity labels can use classifiers as conditions, see [Apply a sensitivity label to content automatically](apply-sensitivity-label-automatically.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e936e-133">Classificadores só funcionam com itens que não são criptografados e estão em inglês.</span><span class="sxs-lookup"><span data-stu-id="e936e-133">Classifiers only work with items that are not encrypted and are in English.</span></span>

## <a name="types-of-classifiers"></a><span data-ttu-id="e936e-134">Tipos de classificadores</span><span class="sxs-lookup"><span data-stu-id="e936e-134">Types of classifiers</span></span>

- <span data-ttu-id="e936e-135">**classificadores previamente** treinados - A Microsoft criou e treinamentou previamente vários classificadores que você pode começar a usar sem treinamento.</span><span class="sxs-lookup"><span data-stu-id="e936e-135">**pre-trained classifiers** - Microsoft has created and pre-trained a number of classifiers that you can start using without training them.</span></span> <span data-ttu-id="e936e-136">Esses classificadores aparecerão com o status de `Ready to use` .</span><span class="sxs-lookup"><span data-stu-id="e936e-136">These classifiers will appear with the status of `Ready to use`.</span></span>
- <span data-ttu-id="e936e-137">**classificadores personalizados** - Se você tiver necessidades de classificação que vão além do que os classificadores previamente treinados cobrem, você pode criar e treinar seus próprios classificadores.</span><span class="sxs-lookup"><span data-stu-id="e936e-137">**custom classifiers** - If you have classification needs that extend beyond what the pre-trained classifiers cover, you can create and train your own classifiers.</span></span>

### <a name="pre-trained-classifiers"></a><span data-ttu-id="e936e-138">Classificadores previamente treinados</span><span class="sxs-lookup"><span data-stu-id="e936e-138">Pre-trained classifiers</span></span>

<span data-ttu-id="e936e-139">O Microsoft 365 vem com cinco classificadores previamente treinados:</span><span class="sxs-lookup"><span data-stu-id="e936e-139">Microsoft 365 comes with five pre-trained classifiers:</span></span>

> [!CAUTION]
> <span data-ttu-id="e936e-140">Estamos preterindo  o classificador de Linguagem Ofensiva previamente treinado porque ele está produzindo um grande número de falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="e936e-140">We are deprecating the **Offensive Language** pre-trained classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="e936e-141">Não use-o e, se você estiver usando-o no momento, deverá tirar seus processos de negócios dele.</span><span class="sxs-lookup"><span data-stu-id="e936e-141">Don't use it and if you are currently using it, you should move your business processes off of it.</span></span> <span data-ttu-id="e936e-142">Em vez **disso,** **recomendamos** o  uso dos classificadores Ameaças , Profanação e Profanação.</span><span class="sxs-lookup"><span data-stu-id="e936e-142">We recommend using the **Threat**, **Profanity**, and **Harassment** pre-trained classifiers instead.</span></span>

- <span data-ttu-id="e936e-143">**Currículos:** detecta itens que são contas textuais de qualificações pessoais, educacionais, profissionais, profissionais e outras informações de identificação pessoal de um candidato</span><span class="sxs-lookup"><span data-stu-id="e936e-143">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information</span></span>
- <span data-ttu-id="e936e-144">**Código-fonte**: detecta itens que contêm um conjunto de instruções e instruções escritas nas 25 principais linguagens de programação de computador usadas no GitHub</span><span class="sxs-lookup"><span data-stu-id="e936e-144">**Source Code**: detects items that contain a set of instructions and statements written in the top 25 used computer programming languages on GitHub</span></span>
    - <span data-ttu-id="e936e-145">ActionScript</span><span class="sxs-lookup"><span data-stu-id="e936e-145">ActionScript</span></span>
    - <span data-ttu-id="e936e-146">C</span><span class="sxs-lookup"><span data-stu-id="e936e-146">C</span></span>
    - <span data-ttu-id="e936e-147">C#</span><span class="sxs-lookup"><span data-stu-id="e936e-147">C#</span></span>
    - <span data-ttu-id="e936e-148">C++</span><span class="sxs-lookup"><span data-stu-id="e936e-148">C++</span></span>
    - <span data-ttu-id="e936e-149">Tamajure</span><span class="sxs-lookup"><span data-stu-id="e936e-149">Clojure</span></span>
    - <span data-ttu-id="e936e-150">CoffeeScript</span><span class="sxs-lookup"><span data-stu-id="e936e-150">CoffeeScript</span></span>
    - <span data-ttu-id="e936e-151">Ir</span><span class="sxs-lookup"><span data-stu-id="e936e-151">Go</span></span>
    - <span data-ttu-id="e936e-152">Hascall</span><span class="sxs-lookup"><span data-stu-id="e936e-152">Haskell</span></span>
    - <span data-ttu-id="e936e-153">Java</span><span class="sxs-lookup"><span data-stu-id="e936e-153">Java</span></span>
    - <span data-ttu-id="e936e-154">JavaScript</span><span class="sxs-lookup"><span data-stu-id="e936e-154">JavaScript</span></span>
    - <span data-ttu-id="e936e-155">Lua</span><span class="sxs-lookup"><span data-stu-id="e936e-155">Lua</span></span>
    - <span data-ttu-id="e936e-156">MATLAB</span><span class="sxs-lookup"><span data-stu-id="e936e-156">MATLAB</span></span>
    - <span data-ttu-id="e936e-157">Objective-C</span><span class="sxs-lookup"><span data-stu-id="e936e-157">Objective-C</span></span>
    - <span data-ttu-id="e936e-158">Perl</span><span class="sxs-lookup"><span data-stu-id="e936e-158">Perl</span></span>
    - <span data-ttu-id="e936e-159">PHP</span><span class="sxs-lookup"><span data-stu-id="e936e-159">PHP</span></span>
    - <span data-ttu-id="e936e-160">Python</span><span class="sxs-lookup"><span data-stu-id="e936e-160">Python</span></span>
    - <span data-ttu-id="e936e-161">R</span><span class="sxs-lookup"><span data-stu-id="e936e-161">R</span></span>
    - <span data-ttu-id="e936e-162">Ruby</span><span class="sxs-lookup"><span data-stu-id="e936e-162">Ruby</span></span>
    - <span data-ttu-id="e936e-163">Scala</span><span class="sxs-lookup"><span data-stu-id="e936e-163">Scala</span></span>
    - <span data-ttu-id="e936e-164">Shell</span><span class="sxs-lookup"><span data-stu-id="e936e-164">Shell</span></span>
    - <span data-ttu-id="e936e-165">Swift</span><span class="sxs-lookup"><span data-stu-id="e936e-165">Swift</span></span>
    - <span data-ttu-id="e936e-166">Tex</span><span class="sxs-lookup"><span data-stu-id="e936e-166">Tex</span></span>
    - <span data-ttu-id="e936e-167">Vim Script</span><span class="sxs-lookup"><span data-stu-id="e936e-167">Vim Script</span></span>

> [!NOTE]
> <span data-ttu-id="e936e-168">O Código-fonte é treinado para detectar quando a maior parte do texto é o código-fonte.</span><span class="sxs-lookup"><span data-stu-id="e936e-168">Source Code is trained to detect when the bulk of the text is source code.</span></span> <span data-ttu-id="e936e-169">Ele não detecta o texto do código-fonte que é intercalado com texto sem texto simples.</span><span class="sxs-lookup"><span data-stu-id="e936e-169">It does not detect source code text that is interspersed with plain text.</span></span>

- <span data-ttu-id="e936e-170">**Abuso**: detecta uma categoria específica de itens de texto de linguagem ofensiva relacionados à conduta ofensiva, direcionando um ou vários indivíduos com base nas seguintes características: corrida, racial, país de origem, origem nacional, sexo, orientação sexual, idade, deficiência</span><span class="sxs-lookup"><span data-stu-id="e936e-170">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability</span></span>
- <span data-ttu-id="e936e-171">**Profanidade**: detecta uma categoria específica de itens de texto de idioma ofensivo que contêm expressões que a maioria das pessoas</span><span class="sxs-lookup"><span data-stu-id="e936e-171">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people</span></span>
- <span data-ttu-id="e936e-172">**Ameaça**: detecta uma categoria específica de itens de texto de idioma ofensivos relacionados a ameaças para comprometer a violência ou fazer danos físicos ou danos a uma pessoa ou propriedade</span><span class="sxs-lookup"><span data-stu-id="e936e-172">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property</span></span>

<span data-ttu-id="e936e-173">Eles aparecem no centro de **conformidade do Microsoft 365, na** exibição classificadores de classificação de dados  >    >  **tremíveis** com o status de `Ready to use` .</span><span class="sxs-lookup"><span data-stu-id="e936e-173">These appear in the **Microsoft 365 compliance center** > **Data classification** > **Trainable classifiers** view with the status of `Ready to use`.</span></span>

![classificadores-pre-trained-classifiers](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> <span data-ttu-id="e936e-175">Observe que os classificadores de linguagem ofensiva, ofensivo, profanação e ameaças só funcionam com texto pesquisável não são completos ou completos.</span><span class="sxs-lookup"><span data-stu-id="e936e-175">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span>  <span data-ttu-id="e936e-176">Além disso, os padrões de idioma e cultura mudam continuamente e, à luz dessas pessoas, a Microsoft reserva-se o direito de atualizar esses classificadores a seu critério.</span><span class="sxs-lookup"><span data-stu-id="e936e-176">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="e936e-177">Embora os classificadores possam ajudar sua organização no monitoramento ofensivo e em outros idiomas usados, os classificadores não abordam as consequências desse idioma e não têm a intenção de fornecer o único meio de monitoramento ou resposta da sua organização ao uso desse idioma.</span><span class="sxs-lookup"><span data-stu-id="e936e-177">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization's sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="e936e-178">Sua organização, e não a Microsoft ou suas subsidiárias, permanece responsável por todas as decisões relacionadas ao monitoramento, imposição, bloqueio, remoção e retenção de qualquer conteúdo identificado por um classificador previamente treinado.</span><span class="sxs-lookup"><span data-stu-id="e936e-178">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

### <a name="custom-classifiers"></a><span data-ttu-id="e936e-179">Classificadores personalizados</span><span class="sxs-lookup"><span data-stu-id="e936e-179">Custom classifiers</span></span>

<span data-ttu-id="e936e-180">Quando os classificadores previamente treinados não atenderem às suas necessidades, você poderá criar e treinar seus próprios classificadores.</span><span class="sxs-lookup"><span data-stu-id="e936e-180">When the pre-trained classifiers don't meet your needs, you can create and train your own classifiers.</span></span> <span data-ttu-id="e936e-181">Há muito mais trabalho envolvido na criação de suas próprias, mas elas serão muito mais adaptadas às suas necessidades de organizações.</span><span class="sxs-lookup"><span data-stu-id="e936e-181">There's significantly more work involved with creating your own, but they'll be much better tailored to your organizations needs.</span></span> 

<span data-ttu-id="e936e-182">Por exemplo, você pode criar classificadores de treinamento para:</span><span class="sxs-lookup"><span data-stu-id="e936e-182">For example you could create trainable classifiers for:</span></span>
 
- <span data-ttu-id="e936e-183">Documentos jurídicos - como privilégio de advogado cliente, conjuntos de fechamento, declaração de trabalho</span><span class="sxs-lookup"><span data-stu-id="e936e-183">Legal documents - such as attorney client privilege, closing sets, statement of work</span></span>
- <span data-ttu-id="e936e-184">Documentos estratégicos de negócios, como comunicados de imprensa, fusão e aquisição, ofertas, planos de negócios ou marketing, propriedade intelectual, patentes, documentos de design</span><span class="sxs-lookup"><span data-stu-id="e936e-184">Strategic business documents - like press releases, merger and acquisition, deals, business or marketing plans, intellectual property, patents, design docs</span></span>
- <span data-ttu-id="e936e-185">Informações de preço - como faturas, cotações, pedidos de trabalho, documentos de documentos de negociação</span><span class="sxs-lookup"><span data-stu-id="e936e-185">Pricing information - like invoices, price quotes, work orders, bidding documents</span></span> 
- <span data-ttu-id="e936e-186">Informações financeiras – como investimentos organizacionais, resultados trimestrais ou anuais</span><span class="sxs-lookup"><span data-stu-id="e936e-186">Financial information - such as organizational investments, quarterly or annual results</span></span>    

#### <a name="process-flow-for-creating-custom-classifiers"></a><span data-ttu-id="e936e-187">Fluxo de processo para a criação de classificadores personalizados</span><span class="sxs-lookup"><span data-stu-id="e936e-187">Process flow for creating custom classifiers</span></span>

<span data-ttu-id="e936e-188">A criação e publicação de um classificador para uso em soluções de conformidade, como políticas de retenção e supervisão de comunicação, segue esse fluxo.</span><span class="sxs-lookup"><span data-stu-id="e936e-188">Creating and publishing a classifier for use in compliance solutions, such as retention policies and communication supervision, follows this flow.</span></span> <span data-ttu-id="e936e-189">For more detail on creating a custom trainable classifier see, [Creating a custom classifier](classifier-get-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="e936e-189">For more detail on creating a custom trainable classifier see, [Creating a custom classifier](classifier-get-started-with.md).</span></span>

![classificador personalizado de fluxo de processo](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a><span data-ttu-id="e936e-191">Retraining classifiers</span><span class="sxs-lookup"><span data-stu-id="e936e-191">Retraining classifiers</span></span>

<span data-ttu-id="e936e-192">Você pode ajudar a melhorar a precisão de todos os classificadores personalizados e alguns classificadores pré-treinados, fornecendo comentários sobre a precisão da classificação que eles executam.</span><span class="sxs-lookup"><span data-stu-id="e936e-192">You can help improve the accuracy of all custom classifiers and some pre-trained classifiers by providing them with feedback on the accuracy of the classification that they perform.</span></span> <span data-ttu-id="e936e-193">Isso é chamado de restrição e siga este fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e936e-193">This is called retraining and follow this workflow.</span></span>

![fluxo de trabalho de retraining do classificador](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a><span data-ttu-id="e936e-195">Confira também</span><span class="sxs-lookup"><span data-stu-id="e936e-195">See also</span></span>

- [<span data-ttu-id="e936e-196">Rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="e936e-196">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="e936e-197">DLP (Prevenção contra perda de dados)</span><span class="sxs-lookup"><span data-stu-id="e936e-197">Data loss prevention (DLP)</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="e936e-198">Rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="e936e-198">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="e936e-199">Definições da entidade do tipo de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="e936e-199">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="e936e-200">Impressão digital de documento</span><span class="sxs-lookup"><span data-stu-id="e936e-200">Document finger printing</span></span>](document-fingerprinting.md)
- [<span data-ttu-id="e936e-201">Exact data match</span><span class="sxs-lookup"><span data-stu-id="e936e-201">Exact data match</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
