---
title: Testando classificadores internos usando rótulos de retenção (visualização)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: A Microsoft 365 vem com uma série de classificadores internos que você pode usar para identificar e rotular o conteúdo em sua organização. Este tópico mostra como se preparar para usar esses classificadores.
ms.openlocfilehash: 2652df8d79b06d6614e2478843195e67de0a8ebb
ms.sourcegitcommit: 87eff6e8a08cec3cb0464a3b765434717584a4a9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/26/2020
ms.locfileid: "44371403"
---
# <a name="testing-built-in-classifiers-using-retention-labels-preview"></a><span data-ttu-id="3dac3-104">Testando classificadores internos usando rótulos de retenção (visualização)</span><span class="sxs-lookup"><span data-stu-id="3dac3-104">Testing built-in classifiers using retention labels (preview)</span></span>

<span data-ttu-id="3dac3-105">A Microsoft treinou e testou cinco classificadores que podem ajudar a identificar determinadas categorias de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="3dac3-105">Microsoft has trained and tested five classifiers which can help to identify certain categories of content.</span></span> <span data-ttu-id="3dac3-106">Esses classificadores aparecem no `Ready to use` grupo por padrão e foram treinados usando conjuntos de dados de amostra muito grandes.</span><span class="sxs-lookup"><span data-stu-id="3dac3-106">These classifiers show up in the `Ready to use` group by default and were trained using very large sample data sets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3dac3-107">Antes de usar classificadores internos em seu fluxo de trabalho de classificação e rotulação, você deve testá-lo em uma amostra do conteúdo da sua organização que você sente que se sinta à categoria para verificar se suas previsões de classificação atendem às suas expectativas.</span><span class="sxs-lookup"><span data-stu-id="3dac3-107">Before using built-in classifiers in your classification and labeling workflow, you should test it against a sample of your organization's content that you feel fits the category to verify that its classification predictions meet your expectations.</span></span>

<span data-ttu-id="3dac3-108">Para obter mais informações sobre classificadores destreinados, confira introdução [aos classificadores ferroviárias (visualização)](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="3dac3-108">For more information on trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="3dac3-109">A Microsoft 365 vem com cinco classificadores internos recomendados:</span><span class="sxs-lookup"><span data-stu-id="3dac3-109">Microsoft 365 comes with five recommended built-in classifiers:</span></span>

> [!CAUTION]
> <span data-ttu-id="3dac3-110">Vamos substituir o classificador interno **Idioma Ofensivo** porque ele tem uma grande quantidade de falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="3dac3-110">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="3dac3-111">Não usá-lo e, se estiver usando, você deverá mover seus processos de negócios para fora dele.</span><span class="sxs-lookup"><span data-stu-id="3dac3-111">Don't use it and if you are currently using it, you should move your business processes off of it.</span></span> <span data-ttu-id="3dac3-112">Recomendamos o uso de classificadores internos **contra ameaças**, **profanação**e **assédio** .</span><span class="sxs-lookup"><span data-stu-id="3dac3-112">We recommend using the **Threat**, **Profanity**, and **Harassment** built-in classifiers instead.</span></span>

- <span data-ttu-id="3dac3-113">**Currículos**: detecta itens que são contas de texto das qualificações pessoais, educacionais, profissionais, experiência de trabalho e outras informações de identificação pessoal de um candidato</span><span class="sxs-lookup"><span data-stu-id="3dac3-113">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information</span></span>
- <span data-ttu-id="3dac3-114">**Código-fonte**: detecta itens que contêm um conjunto de instruções e instruções escritas nas principais linguagens de programação de computador usadas no github</span><span class="sxs-lookup"><span data-stu-id="3dac3-114">**Source Code**: detects items that contain a set of instructions and statements written in the top 25 used computer programming languages on GitHub</span></span>

  |<span data-ttu-id="3dac3-115">nome do idioma</span><span class="sxs-lookup"><span data-stu-id="3dac3-115">language name</span></span>|||||
  |---------|---------|---------|---------|---------|
  |<span data-ttu-id="3dac3-116">Código</span><span class="sxs-lookup"><span data-stu-id="3dac3-116">ActionScript</span></span>|<span data-ttu-id="3dac3-117">C</span><span class="sxs-lookup"><span data-stu-id="3dac3-117">C</span></span>        |<span data-ttu-id="3dac3-118">Unidade #</span><span class="sxs-lookup"><span data-stu-id="3dac3-118">C#</span></span>       |<span data-ttu-id="3dac3-119">C++</span><span class="sxs-lookup"><span data-stu-id="3dac3-119">C++</span></span>     |<span data-ttu-id="3dac3-120">Clojure</span><span class="sxs-lookup"><span data-stu-id="3dac3-120">Clojure</span></span>  |
  |<span data-ttu-id="3dac3-121">CoffeeScript</span><span class="sxs-lookup"><span data-stu-id="3dac3-121">CoffeeScript</span></span>|<span data-ttu-id="3dac3-122">CSS</span><span class="sxs-lookup"><span data-stu-id="3dac3-122">CSS</span></span>     |<span data-ttu-id="3dac3-123">Ir</span><span class="sxs-lookup"><span data-stu-id="3dac3-123">Go</span></span>       |<span data-ttu-id="3dac3-124">Haskell</span><span class="sxs-lookup"><span data-stu-id="3dac3-124">Haskell</span></span> |<span data-ttu-id="3dac3-125">HTML</span><span class="sxs-lookup"><span data-stu-id="3dac3-125">HTML</span></span>     |
  |<span data-ttu-id="3dac3-126">Java</span><span class="sxs-lookup"><span data-stu-id="3dac3-126">Java</span></span>     |<span data-ttu-id="3dac3-127">JavaScript</span><span class="sxs-lookup"><span data-stu-id="3dac3-127">JavaScript</span></span>|<span data-ttu-id="3dac3-128">Lua</span><span class="sxs-lookup"><span data-stu-id="3dac3-128">Lua</span></span>      |<span data-ttu-id="3dac3-129">MATLAB</span><span class="sxs-lookup"><span data-stu-id="3dac3-129">MATLAB</span></span>   |<span data-ttu-id="3dac3-130">Objective-C</span><span class="sxs-lookup"><span data-stu-id="3dac3-130">Objective-C</span></span>|
  |<span data-ttu-id="3dac3-131">Perl</span><span class="sxs-lookup"><span data-stu-id="3dac3-131">Perl</span></span>     |<span data-ttu-id="3dac3-132">PHP</span><span class="sxs-lookup"><span data-stu-id="3dac3-132">PHP</span></span>      |<span data-ttu-id="3dac3-133">Python</span><span class="sxs-lookup"><span data-stu-id="3dac3-133">Python</span></span>   |<span data-ttu-id="3dac3-134">R</span><span class="sxs-lookup"><span data-stu-id="3dac3-134">R</span></span>        |<span data-ttu-id="3dac3-135">Ruby</span><span class="sxs-lookup"><span data-stu-id="3dac3-135">Ruby</span></span>     |
  |<span data-ttu-id="3dac3-136">Scale</span><span class="sxs-lookup"><span data-stu-id="3dac3-136">Scala</span></span>    |<span data-ttu-id="3dac3-137">Shell</span><span class="sxs-lookup"><span data-stu-id="3dac3-137">Shell</span></span>    |<span data-ttu-id="3dac3-138">Swift</span><span class="sxs-lookup"><span data-stu-id="3dac3-138">Swift</span></span>    |<span data-ttu-id="3dac3-139">Tex</span><span class="sxs-lookup"><span data-stu-id="3dac3-139">Tex</span></span>      |<span data-ttu-id="3dac3-140">Script vim</span><span class="sxs-lookup"><span data-stu-id="3dac3-140">Vim Script</span></span>|

> [!NOTE]
> <span data-ttu-id="3dac3-141">O código-fonte é treinado para detectar quando a maior parte do texto é o código-fonte.</span><span class="sxs-lookup"><span data-stu-id="3dac3-141">Source Code is trained to detect when the bulk of the text is source code.</span></span> <span data-ttu-id="3dac3-142">Ele não detecta o texto do código-fonte que é intercalado com texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="3dac3-142">It does not detect source code text that is interspersed with plain text.</span></span>

- <span data-ttu-id="3dac3-143">**Assédio**: detecta uma categoria específica de itens de texto de linguagem ofensiva relacionadas à conduta ofensiva direcionando uma ou várias pessoas com base nas seguintes características: corrida, étnica, Religion, origem nacional, sexo, orientação sexual, idade, deficiência</span><span class="sxs-lookup"><span data-stu-id="3dac3-143">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability</span></span>
- <span data-ttu-id="3dac3-144">**Profanação**: detecta uma categoria específica de itens de texto de idioma ofensivo que contêm expressões que constrangim a maioria das pessoas</span><span class="sxs-lookup"><span data-stu-id="3dac3-144">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people</span></span>
- <span data-ttu-id="3dac3-145">**Ameaça**: detecta uma categoria específica de itens de texto de linguagem ofensiva relacionadas a ameaças para confirmar a violência ou danos físicos ou danos a uma pessoa ou a uma propriedade</span><span class="sxs-lookup"><span data-stu-id="3dac3-145">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3dac3-146">Observe que a linguagem ofensiva, assédio, profanação e classificadores de ameaças só funcionam com o texto pesquisável não é completo nem completo.</span><span class="sxs-lookup"><span data-stu-id="3dac3-146">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span> <span data-ttu-id="3dac3-147">Além disso, os padrões culturais e de idioma mudam continuamente e, em claro, a Microsoft reserva-se o direito de atualizar esses classificadores em seu critério.</span><span class="sxs-lookup"><span data-stu-id="3dac3-147">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="3dac3-148">Embora os classificadores possam ajudar sua organização a monitorar ofensivas e outros idiomas usados, os classificadores não resolvem as conseqüências de tal linguagem e não se destinam a fornecer o único meio de monitoramento ou resposta ao uso dessa linguagem.</span><span class="sxs-lookup"><span data-stu-id="3dac3-148">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization's sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="3dac3-149">Sua organização, e não a Microsoft ou suas subsidiárias, permanece responsável por todas as decisões relacionadas ao monitoramento, imposição, bloqueio, remoção e retenção de qualquer conteúdo identificado por um classificador treinado.</span><span class="sxs-lookup"><span data-stu-id="3dac3-149">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

## <a name="how-to-verify-that-a-built-in-classifier-will-meet-your-needs"></a><span data-ttu-id="3dac3-150">Como verificar se um classificador interno atende às suas necessidades</span><span class="sxs-lookup"><span data-stu-id="3dac3-150">How to verify that a built-in classifier will meet your needs</span></span>

1. <span data-ttu-id="3dac3-151">Coletar itens de conteúdo de teste descartáveis que você sente que pertencem à categoria do classificador interno (correspondências positivas) e aqueles que não devem ser incluídos (correspondências negativas) na categoria que você está testando.</span><span class="sxs-lookup"><span data-stu-id="3dac3-151">Collect disposable test content items that you feel belong in the category of the built-in classifier (positive matches) and ones that shouldn't be included (negative matches) in the category you're testing.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="3dac3-152">Os itens de exemplo não devem ser criptografados e devem estar em inglês.</span><span class="sxs-lookup"><span data-stu-id="3dac3-152">The sample items must not be encrypted and they must be in English.</span></span>

2. <span data-ttu-id="3dac3-153">Criar uma pasta dedicada do SharePoint Online; Aguarde pelo menos uma hora para a pasta a ser adicionada ao índice de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="3dac3-153">Create a dedicated SharePoint Online folder; wait at least an hour for the folder to be added to the search index.</span></span> <span data-ttu-id="3dac3-154">Anote a URL da pasta.</span><span class="sxs-lookup"><span data-stu-id="3dac3-154">Make note of the folder URL.</span></span>

3. <span data-ttu-id="3dac3-155">Entre no centro de conformidade da Microsoft 365 com administrador de conformidade ou acesso à função de **Microsoft 365 compliance center**administrador de segurança e abra a  >  guia**de políticas de gerenciamento de registros**do centro de conformidade da Microsoft 365 (visualização)  >  **Label policies** .</span><span class="sxs-lookup"><span data-stu-id="3dac3-155">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Records management (preview)** > **Label policies** tab.</span></span>

4. <span data-ttu-id="3dac3-156">Escolha `Auto-apply a label` .</span><span class="sxs-lookup"><span data-stu-id="3dac3-156">Choose `Auto-apply a label`.</span></span>

5. <span data-ttu-id="3dac3-157">Escolha `Choose a label to auto-apply` .</span><span class="sxs-lookup"><span data-stu-id="3dac3-157">Choose `Choose a label to auto-apply`.</span></span>

6. <span data-ttu-id="3dac3-158">Escolha `Create new labels` e crie um rótulo para uso apenas com este teste.</span><span class="sxs-lookup"><span data-stu-id="3dac3-158">Choose `Create new labels` and create a label for use just with this test.</span></span> <span data-ttu-id="3dac3-159">Ao fazer isso, deixe `Retention` definido para `off` .</span><span class="sxs-lookup"><span data-stu-id="3dac3-159">When you do this, leave `Retention` set to `off`.</span></span> <span data-ttu-id="3dac3-160">Você não deseja ativar nenhuma retenção ou outras ações.</span><span class="sxs-lookup"><span data-stu-id="3dac3-160">You don't want to turn on any retention or other actions.</span></span> <span data-ttu-id="3dac3-161">Nesse caso, você usará o rótulo de retenção simplesmente como um rótulo de texto, sem impor qualquer ação.</span><span class="sxs-lookup"><span data-stu-id="3dac3-161">In this case, you'll be using the retention label simply as a text label, without enforcing any actions.</span></span> <span data-ttu-id="3dac3-162">Por exemplo, você pode criar um rótulo de retenção chamado "teste de classificador SourceCode" sem ações e, em seguida, aplicar automaticamente esse rótulo de retenção ao conteúdo que tenha classificador de código-fonte como uma condição.</span><span class="sxs-lookup"><span data-stu-id="3dac3-162">For example, you can create a retention label named "SourceCode classifier test" with no actions, and then auto-apply that retention label to content that has Source code classifier as a condition.</span></span> <span data-ttu-id="3dac3-163">Para saber mais sobre a criação de rótulos de retenção, confira [visão geral dos rótulos de retenção](labels.md).</span><span class="sxs-lookup"><span data-stu-id="3dac3-163">To learn more about creating retention labels, see [Overview of retention labels](labels.md).</span></span>
  
7. <span data-ttu-id="3dac3-164">Escolha `Auto-apply a label` e, em seguida `Choose a label to auto-apply` .</span><span class="sxs-lookup"><span data-stu-id="3dac3-164">Choose `Auto-apply a label` and then `Choose a label to auto-apply`.</span></span> <span data-ttu-id="3dac3-165">Para saber mais sobre como usar a condição com base em aplicar automaticamente um rótulo, confira [aplicar automaticamente a política de rótulo de retenção com base em uma condição](labels.md#applying-a-retention-label-automatically-based-on-conditions).</span><span class="sxs-lookup"><span data-stu-id="3dac3-165">To learn more about using condition based auto-apply a label see, [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions).</span></span>

8. <span data-ttu-id="3dac3-166">Escolha seu rótulo de teste na lista e escolha `Next` .</span><span class="sxs-lookup"><span data-stu-id="3dac3-166">Choose your test label from the list and choose `Next`.</span></span>

9. <span data-ttu-id="3dac3-167">Escolha `Apply label to content that matches a trainable classifier` .</span><span class="sxs-lookup"><span data-stu-id="3dac3-167">Choose `Apply label to content that matches a trainable classifier`.</span></span>

   ![selecionar classificador como uma condição](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

10. <span data-ttu-id="3dac3-169">Escolha seu classificador na lista, neste caso`Source Code`</span><span class="sxs-lookup"><span data-stu-id="3dac3-169">Choose your classifier from the list, in this case `Source Code`</span></span>

11. <span data-ttu-id="3dac3-170">Nomeie a política, por exemplo, "teste de classificador interno de código-fonte".</span><span class="sxs-lookup"><span data-stu-id="3dac3-170">Name the policy, for example "Source code built-in classifier test".</span></span>

12. <span data-ttu-id="3dac3-171">Escolha `Let me choose specific locations` .</span><span class="sxs-lookup"><span data-stu-id="3dac3-171">Choose `Let me choose specific locations`.</span></span>

13. <span data-ttu-id="3dac3-172">Desative todos os locais, exceto `SharePoint sites` e escolha `Choose sites` .</span><span class="sxs-lookup"><span data-stu-id="3dac3-172">Turn off all locations except `SharePoint sites` and choose `Choose sites`.</span></span>

14. <span data-ttu-id="3dac3-173">Insira a URL do site na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="3dac3-173">Enter the URL for the site from step 2.</span></span>

15. <span data-ttu-id="3dac3-174">Finalize o assistente e escolha`Auto-apply`</span><span class="sxs-lookup"><span data-stu-id="3dac3-174">Finish the wizard and choose `Auto-apply`</span></span>

16. <span data-ttu-id="3dac3-175">Coloque os itens de teste na pasta dedicada do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="3dac3-175">Place the test items into the dedicated SharePoint Online folder.</span></span>

17. <span data-ttu-id="3dac3-176">Permite que uma hora para o rótulo seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="3dac3-176">Allow an hour for the label to be applied.</span></span>

18. <span data-ttu-id="3dac3-177">Verifique as propriedades dos documentos do rótulo para ver se o classificador incluiu e excluiu o conteúdo de teste conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="3dac3-177">Check the properties of the documents for the label to see if the classifier included and excluded the test content as you expected.</span></span>

19. <span data-ttu-id="3dac3-178">Revise os itens que foram rotulados.</span><span class="sxs-lookup"><span data-stu-id="3dac3-178">Review the items that were labeled.</span></span>

20. <span data-ttu-id="3dac3-179">Exclua o conteúdo e a política de rótulo se você tiver feito o teste.</span><span class="sxs-lookup"><span data-stu-id="3dac3-179">Delete the content and the label policy if you're done with your testing.</span></span>

<span data-ttu-id="3dac3-180">Confira também:</span><span class="sxs-lookup"><span data-stu-id="3dac3-180">See also:</span></span>

- [<span data-ttu-id="3dac3-181">Introdução aos classificadores treináveis (visualização)</span><span class="sxs-lookup"><span data-stu-id="3dac3-181">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
- [<span data-ttu-id="3dac3-182">Visão geral de rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="3dac3-182">Overview of retention labels</span></span>](labels.md)
- [<span data-ttu-id="3dac3-183">Aplicar automaticamente a política de rótulo de retenção com base em uma condição</span><span class="sxs-lookup"><span data-stu-id="3dac3-183">Auto-apply retention label policy based on a condition</span></span>](labels.md#applying-a-retention-label-automatically-based-on-conditions)
