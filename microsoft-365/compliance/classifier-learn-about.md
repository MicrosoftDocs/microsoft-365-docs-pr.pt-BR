---
title: Saiba mais sobre classificadores de treinamento (visualização)
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
description: Um classificador do Microsoft 365 treinado é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo dando amostras positivas e negativas. Depois que o classificador for treinado, você confirmará que os resultados são precisos. Em seguida, use-o para pesquisar o conteúdo da sua organização e classificá-lo para aplicar os rótulos de retenção ou confidencialidade ou incluí-lo em políticas de retenção ou prevenção de perda de dados (DLP).
ms.openlocfilehash: 77ebefe338f393a916f0a6844b42b16e3d011d49
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620157"
---
# <a name="learn-about-classifiers-preview"></a><span data-ttu-id="640bd-105">Saiba mais sobre classificadores (visualização)</span><span class="sxs-lookup"><span data-stu-id="640bd-105">Learn about classifiers (preview)</span></span>

<span data-ttu-id="640bd-106">Classificar e rotular o conteúdo para que ele possa ser protegido e manipulado adequadamente é o local inicial da disciplina de proteção de informações.</span><span class="sxs-lookup"><span data-stu-id="640bd-106">Classifying and labeling content so it can be protected and handled properly is the starting place for the information protection discipline.</span></span> <span data-ttu-id="640bd-107">O Microsoft 365 tem três maneiras de classificar conteúdo.</span><span class="sxs-lookup"><span data-stu-id="640bd-107">Microsoft 365 has three ways to classify content.</span></span>

## <a name="manually"></a><span data-ttu-id="640bd-108">Manualmente</span><span class="sxs-lookup"><span data-stu-id="640bd-108">Manually</span></span>

<span data-ttu-id="640bd-109">Esse método requer ações e julgamento humana.</span><span class="sxs-lookup"><span data-stu-id="640bd-109">This method requires human judgment and action.</span></span> <span data-ttu-id="640bd-110">Um administrador pode usar os rótulos preexistentes e os tipos de informações confidenciais ou criar seus próprios e publicá-los.</span><span class="sxs-lookup"><span data-stu-id="640bd-110">An admin may either use the pre-existing labels and sensitive information types or create their own and then publish them.</span></span> <span data-ttu-id="640bd-111">Os usuários e administradores aplicam-se ao conteúdo à medida que encontrá-lo.</span><span class="sxs-lookup"><span data-stu-id="640bd-111">Users and admins apply them to content as they encounter it.</span></span> <span data-ttu-id="640bd-112">Você pode proteger o conteúdo e gerenciar sua disposição.</span><span class="sxs-lookup"><span data-stu-id="640bd-112">You can then protect the content and manage its disposition.</span></span>

## <a name="automated-pattern-matching"></a><span data-ttu-id="640bd-113">Correspondência de padrões automatizados</span><span class="sxs-lookup"><span data-stu-id="640bd-113">Automated pattern matching</span></span>

<span data-ttu-id="640bd-114">Esta categoria de mecanismos de classificação inclui localizar conteúdo por:</span><span class="sxs-lookup"><span data-stu-id="640bd-114">This category of classification mechanisms include finding content by:</span></span>

- <span data-ttu-id="640bd-115">Palavras-chave ou valores de metadados (idioma de consulta de palavra-chave).</span><span class="sxs-lookup"><span data-stu-id="640bd-115">Keywords or metadata values (keyword query language).</span></span>
- <span data-ttu-id="640bd-116">Usando padrões identificados anteriormente de informações confidenciais, como segurança social, cartão de crédito ou números de contas bancárias [(definições de entidade de tipo de informação confidencial)](sensitive-information-type-entity-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="640bd-116">Using previously identified patterns of sensitive information like social security, credit card or bank account numbers [(Sensitive information type entity definitions)](sensitive-information-type-entity-definitions.md).</span></span>
- <span data-ttu-id="640bd-117">Reconhecendo um item porque ele é uma variação em um modelo [(impressão digital de documento)](document-fingerprinting.md).</span><span class="sxs-lookup"><span data-stu-id="640bd-117">Recognizing an item because it's a variation on a template [(document finger printing)](document-fingerprinting.md).</span></span>
- <span data-ttu-id="640bd-118">Usando a presença de cadeias de caracteres exatas [(correspondência exata de dados)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="640bd-118">Using the presence of exact strings [(exact data match)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

<span data-ttu-id="640bd-119">Os rótulos de confidencialidade e retenção podem ser automaticamente aplicados para tornar o conteúdo disponível para uso na [prevenção de perda de dados (DLP)](data-loss-prevention-policies.md) e [aplicar políticas para os rótulos de retenção](apply-retention-labels-automatically.md).</span><span class="sxs-lookup"><span data-stu-id="640bd-119">Sensitivity and retention labels can then be automatically applied to make the content available for use in [data loss prevention (DLP)](data-loss-prevention-policies.md) and [auto-apply polices for retention labels](apply-retention-labels-automatically.md).</span></span>

## <a name="classifiers"></a><span data-ttu-id="640bd-120">Classificadores</span><span class="sxs-lookup"><span data-stu-id="640bd-120">Classifiers</span></span>

<span data-ttu-id="640bd-121">Esse método de classificação é especialmente adequado ao conteúdo que não é facilmente identificado pelos métodos de correspondência de padrões manuais ou automatizados.</span><span class="sxs-lookup"><span data-stu-id="640bd-121">This classification method is particularly well suited to content that isn't easily identified by either the manual or automated pattern matching methods.</span></span> <span data-ttu-id="640bd-122">Esse método de classificação é mais sobre o treinamento de um classificador para identificar um item com base no que o item é, não por elementos que estão no item (correspondência de padrão).</span><span class="sxs-lookup"><span data-stu-id="640bd-122">This method of classification is more about training a classifier to identify an item based on what the item is, not by elements that are in the item (pattern matching).</span></span> <span data-ttu-id="640bd-123">Um classificador aprende como identificar um tipo de conteúdo observando centenas de exemplos do conteúdo que você está interessado em classificar.</span><span class="sxs-lookup"><span data-stu-id="640bd-123">A classifier learns how to identify a type of content by looking at hundreds of examples of the content you're interested in classifying.</span></span> <span data-ttu-id="640bd-124">Comece por alimentar exemplos de ti que são definitivamente na categoria.</span><span class="sxs-lookup"><span data-stu-id="640bd-124">You start by feeding it examples that are definitely in the category.</span></span> <span data-ttu-id="640bd-125">Depois de processar esses, você o testará dando um mix de exemplos de correspondência e de não correspondência.</span><span class="sxs-lookup"><span data-stu-id="640bd-125">Once it processes those, you test it by giving it a mix of both matching and non-matching examples.</span></span> <span data-ttu-id="640bd-126">Em seguida, o classificador faz previsões como se um determinado item está na categoria que você está criando.</span><span class="sxs-lookup"><span data-stu-id="640bd-126">The classifier then makes predictions as to whether any given item falls into the category you're building.</span></span> <span data-ttu-id="640bd-127">Em seguida, você confirma seus resultados, classificando os positivos verdadeiros, verdadeiros negativos, falsos positivos e falsos negativos para ajudar a aumentar a precisão de suas previsões.</span><span class="sxs-lookup"><span data-stu-id="640bd-127">You then confirm its results, sorting out the true positives, true negatives, false positives, and false negatives to help increase the accuracy of its predictions.</span></span> 

<span data-ttu-id="640bd-128">Quando você publica o classificador, ele classifica itens em locais como o SharePoint Online, o Exchange e o OneDrive e classifica o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="640bd-128">When you publish the classifier, it sorts through items in locations like SharePoint Online, Exchange, and OneDrive, and classifies the content.</span></span> <span data-ttu-id="640bd-129">Após publicar o classificador, você pode continuar a treiná-lo usando um processo de feedback semelhante ao processo de treinamento inicial.</span><span class="sxs-lookup"><span data-stu-id="640bd-129">After you publish the classifier, you can continue to train it using a feedback process that is similar to the initial training process.</span></span>

### <a name="where-you-can-use-trainable-classifiers"></a><span data-ttu-id="640bd-130">Onde você pode usar os classificadores estagiários</span><span class="sxs-lookup"><span data-stu-id="640bd-130">Where you can use trainable classifiers</span></span>
<span data-ttu-id="640bd-131">Tanto classificadores internos quanto classificadores estagiários estão disponíveis como uma condição para o [Office autolabeling com rótulos de sensibilidade](apply-sensitivity-label-automatically.md), [aplicar automaticamente a política de rótulo de retenção com base em uma condição](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) e em [conformidade de comunicação](communication-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="640bd-131">Both built-in classifiers and trainable classifiers are available as a condition for [Office autolabeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [communication compliance](communication-compliance.md).</span></span> 

<span data-ttu-id="640bd-132">Os rótulos de confidencialidade podem usar classificadores como condições, consulte [aplicar um rótulo de confidencialidade ao conteúdo automaticamente](apply-sensitivity-label-automatically.md).</span><span class="sxs-lookup"><span data-stu-id="640bd-132">Sensitivity labels can use classifiers as conditions, see [Apply a sensitivity label to content automatically](apply-sensitivity-label-automatically.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="640bd-133">Os classificadores só funcionam com itens não criptografados e estão em inglês.</span><span class="sxs-lookup"><span data-stu-id="640bd-133">Classifiers only work with items that are not encrypted and are in English.</span></span>

## <a name="types-of-classifiers"></a><span data-ttu-id="640bd-134">Tipos de classificadores</span><span class="sxs-lookup"><span data-stu-id="640bd-134">Types of classifiers</span></span>

- <span data-ttu-id="640bd-135">**classificadores já treinados** -a Microsoft criou e treinava um número de classificadores que você pode começar a usar sem treinar.</span><span class="sxs-lookup"><span data-stu-id="640bd-135">**pre-trained classifiers** - Microsoft has created and pre-trained a number of classifiers that you can start using without training them.</span></span> <span data-ttu-id="640bd-136">Esses classificadores serão exibidos com o status de `Ready to use` .</span><span class="sxs-lookup"><span data-stu-id="640bd-136">These classifiers will appear with the status of `Ready to use`.</span></span>
- <span data-ttu-id="640bd-137">**classificadores personalizados** : se você tiver necessidades de classificação que vão além do que os classificadores já treinados cobrem, você pode criar e treinar seus próprios classificadores.</span><span class="sxs-lookup"><span data-stu-id="640bd-137">**custom classifiers** - If you have classification needs that extend beyond what the pre-trained classifiers cover, you can create and train your own classifiers.</span></span>

### <a name="pre-trained-classifiers"></a><span data-ttu-id="640bd-138">Classificadores pré-qualificados</span><span class="sxs-lookup"><span data-stu-id="640bd-138">Pre-trained classifiers</span></span>

<span data-ttu-id="640bd-139">A Microsoft 365 vem com cinco classificadores pré-qualificados:</span><span class="sxs-lookup"><span data-stu-id="640bd-139">Microsoft 365 comes with five pre-trained classifiers:</span></span>

> [!CAUTION]
> <span data-ttu-id="640bd-140">Estamos preterindo o classificador de **idiomas ofensivos** antes de produzir um grande número de falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="640bd-140">We are deprecating the **Offensive Language** pre-trained classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="640bd-141">Não usá-lo e, se estiver usando, você deverá mover seus processos de negócios para fora dele.</span><span class="sxs-lookup"><span data-stu-id="640bd-141">Don't use it and if you are currently using it, you should move your business processes off of it.</span></span> <span data-ttu-id="640bd-142">É recomendável usar os classificadores treinados **contra ameaças**, **profanação** e **assédio** .</span><span class="sxs-lookup"><span data-stu-id="640bd-142">We recommend using the **Threat**, **Profanity**, and **Harassment** pre-trained classifiers instead.</span></span>

- <span data-ttu-id="640bd-143">**Currículos**: detecta itens que são contas de texto das qualificações pessoais, educacionais, profissionais, experiência de trabalho e outras informações de identificação pessoal de um candidato</span><span class="sxs-lookup"><span data-stu-id="640bd-143">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information</span></span>
- <span data-ttu-id="640bd-144">**Código-fonte**: detecta itens que contêm um conjunto de instruções e instruções escritas nas principais linguagens de programação de computador usadas no github</span><span class="sxs-lookup"><span data-stu-id="640bd-144">**Source Code**: detects items that contain a set of instructions and statements written in the top 25 used computer programming languages on GitHub</span></span>
    - <span data-ttu-id="640bd-145">Código</span><span class="sxs-lookup"><span data-stu-id="640bd-145">ActionScript</span></span>
    - <span data-ttu-id="640bd-146">C</span><span class="sxs-lookup"><span data-stu-id="640bd-146">C</span></span>
    - <span data-ttu-id="640bd-147">C#</span><span class="sxs-lookup"><span data-stu-id="640bd-147">C#</span></span>
    - <span data-ttu-id="640bd-148">C++</span><span class="sxs-lookup"><span data-stu-id="640bd-148">C++</span></span>
    - <span data-ttu-id="640bd-149">Clojure</span><span class="sxs-lookup"><span data-stu-id="640bd-149">Clojure</span></span>
    - <span data-ttu-id="640bd-150">CoffeeScript</span><span class="sxs-lookup"><span data-stu-id="640bd-150">CoffeeScript</span></span>
    - <span data-ttu-id="640bd-151">Ir</span><span class="sxs-lookup"><span data-stu-id="640bd-151">Go</span></span>
    - <span data-ttu-id="640bd-152">Haskell</span><span class="sxs-lookup"><span data-stu-id="640bd-152">Haskell</span></span>
    - <span data-ttu-id="640bd-153">Java</span><span class="sxs-lookup"><span data-stu-id="640bd-153">Java</span></span>
    - <span data-ttu-id="640bd-154">JavaScript</span><span class="sxs-lookup"><span data-stu-id="640bd-154">JavaScript</span></span>
    - <span data-ttu-id="640bd-155">Lua</span><span class="sxs-lookup"><span data-stu-id="640bd-155">Lua</span></span>
    - <span data-ttu-id="640bd-156">MATLAB</span><span class="sxs-lookup"><span data-stu-id="640bd-156">MATLAB</span></span>
    - <span data-ttu-id="640bd-157">Objective-C</span><span class="sxs-lookup"><span data-stu-id="640bd-157">Objective-C</span></span>
    - <span data-ttu-id="640bd-158">Perl</span><span class="sxs-lookup"><span data-stu-id="640bd-158">Perl</span></span>
    - <span data-ttu-id="640bd-159">PHP</span><span class="sxs-lookup"><span data-stu-id="640bd-159">PHP</span></span>
    - <span data-ttu-id="640bd-160">Python</span><span class="sxs-lookup"><span data-stu-id="640bd-160">Python</span></span>
    - <span data-ttu-id="640bd-161">R</span><span class="sxs-lookup"><span data-stu-id="640bd-161">R</span></span>
    - <span data-ttu-id="640bd-162">Ruby</span><span class="sxs-lookup"><span data-stu-id="640bd-162">Ruby</span></span>
    - <span data-ttu-id="640bd-163">Scale</span><span class="sxs-lookup"><span data-stu-id="640bd-163">Scala</span></span>
    - <span data-ttu-id="640bd-164">Shell</span><span class="sxs-lookup"><span data-stu-id="640bd-164">Shell</span></span>
    - <span data-ttu-id="640bd-165">Swift</span><span class="sxs-lookup"><span data-stu-id="640bd-165">Swift</span></span>
    - <span data-ttu-id="640bd-166">Tex</span><span class="sxs-lookup"><span data-stu-id="640bd-166">Tex</span></span>
    - <span data-ttu-id="640bd-167">Script vim</span><span class="sxs-lookup"><span data-stu-id="640bd-167">Vim Script</span></span>

> [!NOTE]
> <span data-ttu-id="640bd-168">O código-fonte é treinado para detectar quando a maior parte do texto é o código-fonte.</span><span class="sxs-lookup"><span data-stu-id="640bd-168">Source Code is trained to detect when the bulk of the text is source code.</span></span> <span data-ttu-id="640bd-169">Ele não detecta o texto do código-fonte que é intercalado com texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="640bd-169">It does not detect source code text that is interspersed with plain text.</span></span>

- <span data-ttu-id="640bd-170">**Assédio**: detecta uma categoria específica de itens de texto de linguagem ofensiva relacionadas à conduta ofensiva direcionando uma ou várias pessoas com base nas seguintes características: corrida, étnica, Religion, origem nacional, sexo, orientação sexual, idade, deficiência</span><span class="sxs-lookup"><span data-stu-id="640bd-170">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability</span></span>
- <span data-ttu-id="640bd-171">**Profanação**: detecta uma categoria específica de itens de texto de idioma ofensivo que contêm expressões que constrangim a maioria das pessoas</span><span class="sxs-lookup"><span data-stu-id="640bd-171">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people</span></span>
- <span data-ttu-id="640bd-172">**Ameaça**: detecta uma categoria específica de itens de texto de linguagem ofensiva relacionadas a ameaças para confirmar a violência ou danos físicos ou danos a uma pessoa ou a uma propriedade</span><span class="sxs-lookup"><span data-stu-id="640bd-172">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property</span></span>

<span data-ttu-id="640bd-173">Eles aparecem no modo de exibição de classificação de dados do **centro de conformidade da Microsoft 365**  >  **(visualização)**  >  **classificadores estagiários** com o status de `Ready to use` .</span><span class="sxs-lookup"><span data-stu-id="640bd-173">These appear in the **Microsoft 365 compliance center** > **Data classification (preview)** > **Trainable classifiers** view with the status of `Ready to use`.</span></span>

![classificadores-classificadores pré treinado](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> <span data-ttu-id="640bd-175">Observe que a linguagem ofensiva, assédio, profanação e classificadores de ameaças só funcionam com o texto pesquisável não é completo nem completo.</span><span class="sxs-lookup"><span data-stu-id="640bd-175">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span>  <span data-ttu-id="640bd-176">Além disso, os padrões culturais e de idioma mudam continuamente e, em claro, a Microsoft reserva-se o direito de atualizar esses classificadores em seu critério.</span><span class="sxs-lookup"><span data-stu-id="640bd-176">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="640bd-177">Embora os classificadores possam ajudar sua organização a monitorar ofensivas e outros idiomas usados, os classificadores não resolvem as conseqüências de tal linguagem e não se destinam a fornecer o único meio de monitoramento ou resposta ao uso dessa linguagem.</span><span class="sxs-lookup"><span data-stu-id="640bd-177">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization's sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="640bd-178">Sua organização, e não a Microsoft ou suas subsidiárias, permanece responsável por todas as decisões relacionadas ao monitoramento, imposição, bloqueio, remoção e retenção de qualquer conteúdo identificado por um classificador treinado.</span><span class="sxs-lookup"><span data-stu-id="640bd-178">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

### <a name="custom-classifiers"></a><span data-ttu-id="640bd-179">Classificadores personalizados</span><span class="sxs-lookup"><span data-stu-id="640bd-179">Custom classifiers</span></span>

<span data-ttu-id="640bd-180">Quando os classificadores treinados não atenderem às suas necessidades, você poderá criar e treinar seus próprios classificadores.</span><span class="sxs-lookup"><span data-stu-id="640bd-180">When the pre-trained classifiers don't meet your needs, you can create and train your own classifiers.</span></span> <span data-ttu-id="640bd-181">Há muito mais trabalho envolvido na criação de suas próprias, mas eles serão muito mais adequados às suas necessidades de organizações.</span><span class="sxs-lookup"><span data-stu-id="640bd-181">There's significantly more work involved with creating your own, but they'll be much better tailored to your organizations needs.</span></span> 

<span data-ttu-id="640bd-182">Por exemplo, você poderia criar classificadores estagiários para:</span><span class="sxs-lookup"><span data-stu-id="640bd-182">For example you could create trainable classifiers for:</span></span>
 
- <span data-ttu-id="640bd-183">Documentos legais, como privilégio de cliente de advogados, conjuntos de fechamento, proposta de serviço</span><span class="sxs-lookup"><span data-stu-id="640bd-183">Legal documents - such as attorney client privilege, closing sets, statement of work</span></span>
- <span data-ttu-id="640bd-184">Documentos estratégicos de negócios, como Press Releases, fusão e aquisição, negócios, planos de negócios ou marketing, propriedade intelectual, patentes, documentos de design</span><span class="sxs-lookup"><span data-stu-id="640bd-184">Strategic business documents - like press releases, merger and acquisition, deals, business or marketing plans, intellectual property, patents, design docs</span></span>
- <span data-ttu-id="640bd-185">Informações sobre preços-como faturas, cotações de preços, pedidos de trabalho, documentos de apostas</span><span class="sxs-lookup"><span data-stu-id="640bd-185">Pricing information - like invoices, price quotes, work orders, bidding documents</span></span> 
- <span data-ttu-id="640bd-186">Informações financeiras – como investimentos organizacionais, resultados trimestrais ou anuais</span><span class="sxs-lookup"><span data-stu-id="640bd-186">Financial information - such as organizational investments, quarterly or annual results</span></span>    

#### <a name="process-flow-for-creating-custom-classifiers"></a><span data-ttu-id="640bd-187">Fluxo do processo de criação de classificadores personalizados</span><span class="sxs-lookup"><span data-stu-id="640bd-187">Process flow for creating custom classifiers</span></span>

<span data-ttu-id="640bd-188">A criação e publicação de um classificador para uso em soluções de conformidade, como políticas de retenção e supervisão de comunicação, segue este fluxo.</span><span class="sxs-lookup"><span data-stu-id="640bd-188">Creating and publishing a classifier for use in compliance solutions, such as retention policies and communication supervision, follows this flow.</span></span> <span data-ttu-id="640bd-189">Para obter mais detalhes sobre como criar um classificador treinado personalizado, consulte [criando um classificador personalizado](classifier-get-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="640bd-189">For more detail on creating a custom trainable classifier see, [Creating a custom classifier](classifier-get-started-with.md).</span></span>

![classificador personalizado de fluxo de processo](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a><span data-ttu-id="640bd-191">Retreinando classificadores</span><span class="sxs-lookup"><span data-stu-id="640bd-191">Retraining classifiers</span></span>

<span data-ttu-id="640bd-192">Você pode ajudar a melhorar a precisão de todos os classificadores personalizados e alguns classificadores pré-qualificados, fornecendo comentários sobre a precisão da classificação que eles executam.</span><span class="sxs-lookup"><span data-stu-id="640bd-192">You can help improve the accuracy of all custom classifiers and some pre-trained classifiers by providing them with feedback on the accuracy of the classification that they perform.</span></span> <span data-ttu-id="640bd-193">Isso é chamado de retreinamento e acompanhamento deste fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="640bd-193">This is called retraining and follow this workflow.</span></span>

![fluxo de trabalho de retreinamento do classificador](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a><span data-ttu-id="640bd-195">Confira também</span><span class="sxs-lookup"><span data-stu-id="640bd-195">See also</span></span>

- [<span data-ttu-id="640bd-196">Rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="640bd-196">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="640bd-197">Data loss prevention (DLP)</span><span class="sxs-lookup"><span data-stu-id="640bd-197">Data loss prevention (DLP)</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="640bd-198">Rótulos de confidencialidade </span><span class="sxs-lookup"><span data-stu-id="640bd-198">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="640bd-199">Definições da entidade do tipo de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="640bd-199">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="640bd-200">Impressão digital do documento</span><span class="sxs-lookup"><span data-stu-id="640bd-200">Document finger printing</span></span>](document-fingerprinting.md)
- [<span data-ttu-id="640bd-201">Correspondência de dados exata</span><span class="sxs-lookup"><span data-stu-id="640bd-201">Exact data match</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
