---
title: Criar um classificador treinado (visualização)
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
description: Use classificadores treinados quando um dos classificadores de caixa pronto para usar não atender às suas necessidades. Um classificador da Microsoft 365 é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo fornecendo amostras de ti para ver. Este tópico mostra como criar um classificador personalizado.
ms.openlocfilehash: cb3cda9777d692a56263e92cd908eb09bfa99895
ms.sourcegitcommit: 8fda7852b2a5baa92b8a365865b014ea6d100bbc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2019
ms.locfileid: "39813369"
---
# <a name="creating-a-trainable-classifier-preview"></a><span data-ttu-id="e1281-105">Criar um classificador treinado (visualização)</span><span class="sxs-lookup"><span data-stu-id="e1281-105">Creating a trainable classifier (preview)</span></span>

<span data-ttu-id="e1281-106">Use classificadores treinados quando um dos classificadores prontos para uso não atender às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="e1281-106">Use trainable classifiers when one of the out of the box classifiers won't meet your needs.</span></span> <span data-ttu-id="e1281-107">Um classificador da Microsoft 365 é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo fornecendo amostras de ti para ver.</span><span class="sxs-lookup"><span data-stu-id="e1281-107">A Microsoft 365 classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="e1281-108">O treinamento do classificador envolve primeiro a atribuição de exemplos de ti que são separados e positivamente correspondem à categoria.</span><span class="sxs-lookup"><span data-stu-id="e1281-108">Training the classifier involves first giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="e1281-109">Depois de ter processado esses, você testará as previsões dando uma mistura de amostras positivas e negativas.</span><span class="sxs-lookup"><span data-stu-id="e1281-109">Then, after it has processed those, you test the predictions by giving it a mix of positive and negative samples.</span></span>

<span data-ttu-id="e1281-110">Para saber mais sobre os diferentes tipos de classificadores, confira [introdução aos classificadores ferroviárias (visualização)](classifier-getting-started-with.md)</span><span class="sxs-lookup"><span data-stu-id="e1281-110">To learn more about the different types of classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md)</span></span>

<span data-ttu-id="e1281-111">Esta linha do tempo reflete uma implantação de amostra.</span><span class="sxs-lookup"><span data-stu-id="e1281-111">This timeline reflects a sample deployment.</span></span>

![Estagiário-classificador-linha do tempo](media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="e1281-113">O consentimento é obrigatório pela primeira vez para os classificadores treináveis.</span><span class="sxs-lookup"><span data-stu-id="e1281-113">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="e1281-114">O Microsoft 365 leva 12 dias para concluir a avaliação da linha de base do conteúdo da sua organização.</span><span class="sxs-lookup"><span data-stu-id="e1281-114">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span>

## <a name="seed-content"></a><span data-ttu-id="e1281-115">Conteúdo semente</span><span class="sxs-lookup"><span data-stu-id="e1281-115">Seed content</span></span>

<span data-ttu-id="e1281-116">Quando você quiser um classificador treinado para identificar de forma independente e precisa um item como estando em uma categoria específica de conteúdo, primeiro é preciso apresentá-lo com vários exemplos do tipo de conteúdo que está na categoria.</span><span class="sxs-lookup"><span data-stu-id="e1281-116">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="e1281-117">Esta alimentação de amostras para o classificador treinado é conhecida como *propagação*.</span><span class="sxs-lookup"><span data-stu-id="e1281-117">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="e1281-118">O conteúdo semente é selecionado por uma pessoa e é julgada para representar a categoria do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e1281-118">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="e1281-119">Você precisa ter pelo menos 50 amostras positivas e até 500.</span><span class="sxs-lookup"><span data-stu-id="e1281-119">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="e1281-120">O classificador treinado será processado até os 500 exemplos criados mais recentes (por data de criação do arquivo/carimbo de hora).</span><span class="sxs-lookup"><span data-stu-id="e1281-120">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="e1281-121">Quanto mais amostras você fornecer, mais precisará das previsões que o classificador fará.</span><span class="sxs-lookup"><span data-stu-id="e1281-121">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

## <a name="testing-content"></a><span data-ttu-id="e1281-122">Testando conteúdo</span><span class="sxs-lookup"><span data-stu-id="e1281-122">Testing content</span></span>

<span data-ttu-id="e1281-123">Depois que o classificador treinado tiver processado exemplos positivos suficientes para criar um modelo de previsão, você precisará testar as previsões feitas para ver se o classificador pode distinguir corretamente os itens que correspondem à categoria e aos itens que não estão.</span><span class="sxs-lookup"><span data-stu-id="e1281-123">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="e1281-124">Você faz isso alimentando o outro, espero maior, um conjunto de conteúdo separado para o homem que consiste em exemplos que devem se enquadrar na categoria e exemplos que não.</span><span class="sxs-lookup"><span data-stu-id="e1281-124">You do this by feeding it another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="e1281-125">Depois de processá-los, você passará manualmente pelos resultados e verificará se cada previsão está correta, incorreta ou se não tem certeza.</span><span class="sxs-lookup"><span data-stu-id="e1281-125">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="e1281-126">O classificador treinado usa esse feedback para melhorar seu modelo de previsão.</span><span class="sxs-lookup"><span data-stu-id="e1281-126">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="e1281-127">Para obter melhores resultados, tenha 10.000 itens em seu conjunto de amostra de teste com uma distribuição uniforme de correspondências positivas e negativas.</span><span class="sxs-lookup"><span data-stu-id="e1281-127">For best results, have 10,000 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="e1281-128">Como criar um classificador treinado</span><span class="sxs-lookup"><span data-stu-id="e1281-128">How to create a trainable classifier</span></span>

1. <span data-ttu-id="e1281-129">Coleta entre 50-500 itens de conteúdo semente.</span><span class="sxs-lookup"><span data-stu-id="e1281-129">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="e1281-130">Eles devem ser apenas exemplos que representam fortemente o tipo de conteúdo que você deseja que o classificador treinado identifique positivamente como estando na categoria de classificação.</span><span class="sxs-lookup"><span data-stu-id="e1281-130">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="e1281-131">Consulte, [extensões de nome de arquivo rastreado padrão e tipos de arquivo analisados no SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) para os tipos de arquivo com suporte.</span><span class="sxs-lookup"><span data-stu-id="e1281-131">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e1281-132">Os itens de amostra de propagação e teste não devem ser criptografados e devem estar em inglês.</span><span class="sxs-lookup"><span data-stu-id="e1281-132">The seed and test sample items must not be encrypted and they must be in English.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e1281-133">Certifique-se de que os itens em seu conjunto de propagação são exemplos **fortes** da categoria.</span><span class="sxs-lookup"><span data-stu-id="e1281-133">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="e1281-134">O classificador treinado inicialmente cria seu modelo com base no que você propaga com ele.</span><span class="sxs-lookup"><span data-stu-id="e1281-134">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="e1281-135">O classificador supõe que todos os exemplos de propagação são positivos fortes e não têm como saber se uma amostra é uma correspondência fraca ou negativa à categoria.</span><span class="sxs-lookup"><span data-stu-id="e1281-135">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="e1281-136">Coloque o conteúdo semente em uma pasta do SharePoint Online que seja dedicada a manter *somente o conteúdo semente*.</span><span class="sxs-lookup"><span data-stu-id="e1281-136">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="e1281-137">Anote o site, a biblioteca e a URL da pasta.</span><span class="sxs-lookup"><span data-stu-id="e1281-137">Make note of the site, library, and folder URL.</span></span>

> [!TIP]
> <span data-ttu-id="e1281-138">Se você criar um novo site e pasta para seus dados semente, permita que pelo menos uma hora para esse local seja indexado antes de criar o classificador treinado que usará esses dados de propagação.</span><span class="sxs-lookup"><span data-stu-id="e1281-138">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="e1281-139">Entre no centro de conformidade da Microsoft 365 com administrador de conformidade ou acesso à função de administrador de segurança e abra **o centro de conformidade** da Microsoft 365 ou a**classificação de dados** **do centro** > de segurança da Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e1281-139">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**</span></span>

4. <span data-ttu-id="e1281-140">Escolha a guia **classificadores estagiários** .</span><span class="sxs-lookup"><span data-stu-id="e1281-140">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="e1281-141">Escolha **criar classificador treinado**.</span><span class="sxs-lookup"><span data-stu-id="e1281-141">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="e1281-142">Preencha os valores apropriados para o `Name`e `Description` os campos da categoria de itens que você deseja que esse classificador seja identificado.</span><span class="sxs-lookup"><span data-stu-id="e1281-142">Fill in appropriate values for the `Name`, and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="e1281-143">Insira o site, a biblioteca e a URL exata do SharePoint Online para o site de conteúdo semente da etapa 2.</span><span class="sxs-lookup"><span data-stu-id="e1281-143">Enter the exact SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="e1281-144">Escolha `Add`.</span><span class="sxs-lookup"><span data-stu-id="e1281-144">Choose `Add`.</span></span>

8. <span data-ttu-id="e1281-145">Revise as configurações e `Create trainable classifier`escolha.</span><span class="sxs-lookup"><span data-stu-id="e1281-145">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="e1281-146">Dentro de 24 horas, o classificador treinado processará os dados semente e criará um modelo de previsão.</span><span class="sxs-lookup"><span data-stu-id="e1281-146">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="e1281-147">O status do classificador é `In progress` enquanto processa os dados semente.</span><span class="sxs-lookup"><span data-stu-id="e1281-147">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="e1281-148">Quando o classificador terminar o processamento dos dados semente, o status mudará para `Need test items`.</span><span class="sxs-lookup"><span data-stu-id="e1281-148">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="e1281-149">Agora você pode exibir a página de detalhes escolhendo o classificador.</span><span class="sxs-lookup"><span data-stu-id="e1281-149">You can now view the details page by choosing the classifier.</span></span>


![classificador de estagiário pronto para teste](media/classifier-trainable-ready-to-test-detail.png)

11. <span data-ttu-id="e1281-151">Colete pelo menos 200 itens de conteúdo de teste.</span><span class="sxs-lookup"><span data-stu-id="e1281-151">Collect at least 200 test content items.</span></span> <span data-ttu-id="e1281-152">A Microsoft recomenda 10.000 para obter os melhores resultados.</span><span class="sxs-lookup"><span data-stu-id="e1281-152">Microsoft recommends 10,000 for best results.</span></span> <span data-ttu-id="e1281-153">Eles devem ser uma mistura de itens que são positivos fortes, negativos fortes e outros que são um pouco menos óbvios em sua natureza.</span><span class="sxs-lookup"><span data-stu-id="e1281-153">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="e1281-154">Consulte, [extensões de nome de arquivo rastreado padrão e tipos de arquivo analisados no SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) para os tipos de arquivo com suporte.</span><span class="sxs-lookup"><span data-stu-id="e1281-154">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e1281-155">Os itens de exemplo não devem ser criptografados e devem estar em inglês.</span><span class="sxs-lookup"><span data-stu-id="e1281-155">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="e1281-156">Coloque o conteúdo de teste em uma pasta do SharePoint Online que seja dedicada a conter *somente o conteúdo de teste*.</span><span class="sxs-lookup"><span data-stu-id="e1281-156">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="e1281-157">Anote o site, a biblioteca e a URL da pasta do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e1281-157">Make note of the SharePoint Online site, library, and folder URL.</span></span>

> [!TIP]
> <span data-ttu-id="e1281-158">Se você criar um novo site e uma pasta para seus dados de teste, permita que pelo menos uma hora para esse local seja indexado antes de criar o classificador treinado que usará esses dados semente.</span><span class="sxs-lookup"><span data-stu-id="e1281-158">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="e1281-159">Escolha `Add items to test`.</span><span class="sxs-lookup"><span data-stu-id="e1281-159">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="e1281-160">Insira o site, a biblioteca e a URL exata do SharePoint Online para o site de conteúdo de teste da etapa 12.</span><span class="sxs-lookup"><span data-stu-id="e1281-160">Enter the exact SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="e1281-161">Escolha `Add`.</span><span class="sxs-lookup"><span data-stu-id="e1281-161">Choose `Add`.</span></span>

15. <span data-ttu-id="e1281-162">Finalize o assistente escolhendo `Done`.</span><span class="sxs-lookup"><span data-stu-id="e1281-162">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="e1281-163">Seu classificador treinado levará até uma hora para processar os arquivos de teste.</span><span class="sxs-lookup"><span data-stu-id="e1281-163">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="e1281-164">Quando o classificador treinado termina de processar seus arquivos de teste, o status da página de detalhes será alterado `Ready to review`para.</span><span class="sxs-lookup"><span data-stu-id="e1281-164">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="e1281-165">Se você precisar aumentar o tamanho da amostra de teste, `Add items to test` escolha e permitir que o classificador treinado processe os itens adicionais.</span><span class="sxs-lookup"><span data-stu-id="e1281-165">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

![Pronto para revisar captura de tela](media/classifier-trainable-ready-to-review-detail.png)

17. <span data-ttu-id="e1281-167">Escolha `Tested items to review` Tab para revisar itens.</span><span class="sxs-lookup"><span data-stu-id="e1281-167">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="e1281-168">A Microsoft 365 apresentará 30 itens por vez.</span><span class="sxs-lookup"><span data-stu-id="e1281-168">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="e1281-169">Examine-os e, `We predict this item is "Relevant". Do you agree?` na caixa, `Yes` escolha `No` ou `Not sure, skip to next item`ou.</span><span class="sxs-lookup"><span data-stu-id="e1281-169">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="e1281-170">A precisão do modelo é atualizada automaticamente após cada 30 itens.</span><span class="sxs-lookup"><span data-stu-id="e1281-170">Model accuracy is automatically updated after every 30 items.</span></span>

![caixa examinar itens](media/classifier-trainable-review-detail.png)

19. <span data-ttu-id="e1281-172">Revise *pelo menos* 200 itens.</span><span class="sxs-lookup"><span data-stu-id="e1281-172">Review *at least* 200 items.</span></span>

<!-- insert Analyze steps here-->

20. <span data-ttu-id="e1281-173">Continue a revisar até que a precisão alcance pelo menos 70 `Publish the classifier` % e `Ready to use`o status é.</span><span class="sxs-lookup"><span data-stu-id="e1281-173">Continue to review until the accuracy reaches at least 70% and the `Publish the classifier` status is `Ready to use`.</span></span>

![precisão e pronto para publicar](media/classifier-trainable-review-ready-to-publish.png)

21. <span data-ttu-id="e1281-175">Publicar o classificador.</span><span class="sxs-lookup"><span data-stu-id="e1281-175">Publish the classifier.</span></span>

22. <span data-ttu-id="e1281-176">Depois de publicado, seu classificador estará disponível como uma condição na [política de rótulo de retenção de aplicação automática com base em uma condição](labels.md#applying-a-retention-label-automatically-based-on-conditions) e em conformidade de [comunicação](communication-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="e1281-176">Once published your classifier will be available as a condition in the [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions) and in [Communication compliance](communication-compliance.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="e1281-177">Após a publicação de um classificador, ele não poderá passar por nenhum treinamento adicional, portanto, certifique-se de que você testou e analisou o máximo de itens possível para garantir que a precisão seja a mais alta possível.</span><span class="sxs-lookup"><span data-stu-id="e1281-177">Once a classifier is published, it can't go through any additional training, so be very sure that you have tested and reviewed as many items as possible to ensure that the accuracy is as high as possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1281-178">Confira também</span><span class="sxs-lookup"><span data-stu-id="e1281-178">See also</span></span>

- [<span data-ttu-id="e1281-179">Introdução aos classificadores de treinamento (visualização)</span><span class="sxs-lookup"><span data-stu-id="e1281-179">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
- [<span data-ttu-id="e1281-180">Extensões de nome de arquivo rastreado padrão e tipos de arquivos analisados no SharePoint Server Server</span><span class="sxs-lookup"><span data-stu-id="e1281-180">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
