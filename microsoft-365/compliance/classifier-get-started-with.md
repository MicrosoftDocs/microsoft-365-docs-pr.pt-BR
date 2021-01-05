---
title: Introdução aos classificadores estagiários
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
description: Um classificador da Microsoft 365 é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo fornecendo amostras de ti para ver. Este artigo mostra como criar e treinar um classificador personalizado e como retreiná-los para aumentar a precisão.
ms.openlocfilehash: bca1de5edc3efd38f943b02091c3f47d832e6a19
ms.sourcegitcommit: 54d1a2f363b2d5b63aae258c3cec0573a08f2866
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49752655"
---
# <a name="get-started-with-trainable-classifiers"></a><span data-ttu-id="6b130-104">Introdução aos classificadores estagiários</span><span class="sxs-lookup"><span data-stu-id="6b130-104">Get started with trainable classifiers</span></span>

<span data-ttu-id="6b130-105">Um classificador Microsoft 365 treinado é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo dando amostras a eles.</span><span class="sxs-lookup"><span data-stu-id="6b130-105">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="6b130-106">Depois de treinado, você pode usá-lo para identificar o item para a aplicação de rótulos de confidencialidade do Office, políticas de conformidade de comunicações e políticas de rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="6b130-106">Once trained, you can use it to identify item for application of Office sensitivity labels, Communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="6b130-107">A criação de um classificador personalizável personalizado primeiro envolve fornecer amostras de ti de forma humana e coincidir positivamente a categoria.</span><span class="sxs-lookup"><span data-stu-id="6b130-107">Creating a custom trainable classifier first involves giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="6b130-108">Depois de ter processado esses, você testará a capacidade dos classificadores para prever dando a ele uma mistura de amostras positivas e negativas.</span><span class="sxs-lookup"><span data-stu-id="6b130-108">Then, after it has processed those, you test the classifiers ability to predict by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="6b130-109">Este artigo mostra como criar e treinar um classificador personalizado e como melhorar o desempenho de classificadores treinados personalizados e classificadores pré-qualificados em seu tempo de vida por meio de um retreinamento.</span><span class="sxs-lookup"><span data-stu-id="6b130-109">This article shows you how to create and train a custom classifier and how to improve the performance of custom trainable classifiers and pre-trained classifiers over their lifetime through retraining.</span></span>

<span data-ttu-id="6b130-110">Para saber mais sobre os diferentes tipos de classificadores, confira [saiba mais sobre classificadores estagiários](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="6b130-110">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6b130-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="6b130-111">Prerequisites</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="6b130-112">Requisitos de licença</span><span class="sxs-lookup"><span data-stu-id="6b130-112">Licensing requirements</span></span>

<span data-ttu-id="6b130-113">Os classificadores são um recurso de conformidade do Microsoft 365 E5 ou e5.</span><span class="sxs-lookup"><span data-stu-id="6b130-113">Classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="6b130-114">Você deve ter uma dessas assinaturas para usá-las.</span><span class="sxs-lookup"><span data-stu-id="6b130-114">You must have one of these subscriptions to make use of them.</span></span>

### <a name="permissions"></a><span data-ttu-id="6b130-115">Permissions</span><span class="sxs-lookup"><span data-stu-id="6b130-115">Permissions</span></span>

<span data-ttu-id="6b130-116">Para acessar classificadores na interface do usuário:</span><span class="sxs-lookup"><span data-stu-id="6b130-116">To access classifiers in the UI:</span></span> 

- <span data-ttu-id="6b130-117">o administrador global precisa aceitar o locatário para criar classificadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="6b130-117">the Global admin needs to opt in for the tenant to create custom classifiers.</span></span>
- <span data-ttu-id="6b130-118">A função de administrador de conformidade é necessária para treinar um classificador.</span><span class="sxs-lookup"><span data-stu-id="6b130-118">Compliance Administrator role is required to train a classifier.</span></span>

<span data-ttu-id="6b130-119">Você precisará de contas com essas permissões para usar classificadores nestes cenários:</span><span class="sxs-lookup"><span data-stu-id="6b130-119">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="6b130-120">Cenário de política de rótulo de retenção: gerenciamento de registros e funções de gerenciamento de retenção</span><span class="sxs-lookup"><span data-stu-id="6b130-120">Retention label policy scenario: Record Management and Retention Management roles</span></span> 
- <span data-ttu-id="6b130-121">Cenário de política de rótulo de confidencialidade: administrador de segurança, administrador de conformidade, administrador de dados de conformidade</span><span class="sxs-lookup"><span data-stu-id="6b130-121">Sensitivity label policy scenario: Security Administrator, Compliance Administrator, Compliance Data Administrator</span></span>
- <span data-ttu-id="6b130-122">Cenário de política de conformidade de comunicação: administração de gerenciamento de risco do Insider, administrador de análise de supervisão</span><span class="sxs-lookup"><span data-stu-id="6b130-122">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="6b130-123">Por padrão, apenas o usuário que cria um classificador personalizado pode treinar e revisar previsões feitas por esse classificador.</span><span class="sxs-lookup"><span data-stu-id="6b130-123">By default, only the user who creates a custom classifier can train and review predictions made by that classifier.</span></span>

## <a name="prepare-for-a-custom-trainable-classifier"></a><span data-ttu-id="6b130-124">Preparar-se para um classificador treinado personalizado</span><span class="sxs-lookup"><span data-stu-id="6b130-124">Prepare for a custom trainable classifier</span></span> 

<span data-ttu-id="6b130-125">É útil entender o que está envolvido na criação de um classificador treinado personalizado antes de você se aprofundar no.</span><span class="sxs-lookup"><span data-stu-id="6b130-125">It's helpful to understand what's involved in creating a custom trainable classifier before you dive in.</span></span> 

### <a name="timeline"></a><span data-ttu-id="6b130-126">Linha do tempo</span><span class="sxs-lookup"><span data-stu-id="6b130-126">Timeline</span></span>

<span data-ttu-id="6b130-127">Esta linha do tempo reflete um exemplo de implantação de classificadores ferroviárias.</span><span class="sxs-lookup"><span data-stu-id="6b130-127">This timeline reflects a sample deployment of trainable classifiers.</span></span>

![Estagiário-classificador-linha do tempo](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="6b130-129">O consentimento é obrigatório pela primeira vez para os classificadores treináveis.</span><span class="sxs-lookup"><span data-stu-id="6b130-129">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="6b130-130">O Microsoft 365 leva 12 dias para concluir a avaliação da linha de base do conteúdo da sua organização.</span><span class="sxs-lookup"><span data-stu-id="6b130-130">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span> <span data-ttu-id="6b130-131">Entre em contato com seu administrador global para iniciar o processo de consentimento.</span><span class="sxs-lookup"><span data-stu-id="6b130-131">Contact your global administrator to kick off the opt-in process.</span></span>

### <a name="overall-workflow"></a><span data-ttu-id="6b130-132">Fluxo de trabalho geral</span><span class="sxs-lookup"><span data-stu-id="6b130-132">Overall workflow</span></span>

<span data-ttu-id="6b130-133">Para entender mais sobre o fluxo de trabalho geral de criação de classificadores destreinados personalizados, confira o [fluxo de processo para criar os classificadores estagiários do cliente](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).</span><span class="sxs-lookup"><span data-stu-id="6b130-133">To understand more about the overall workflow of creating custom trainable classifiers, see [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).</span></span>

### <a name="seed-content"></a><span data-ttu-id="6b130-134">Conteúdo semente</span><span class="sxs-lookup"><span data-stu-id="6b130-134">Seed content</span></span>

<span data-ttu-id="6b130-135">Quando você quiser um classificador treinado para identificar de forma independente e precisa um item como estando em uma categoria específica de conteúdo, primeiro é preciso apresentá-lo com vários exemplos do tipo de conteúdo que está na categoria.</span><span class="sxs-lookup"><span data-stu-id="6b130-135">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="6b130-136">Esta alimentação de amostras para o classificador treinado é conhecida como *propagação*.</span><span class="sxs-lookup"><span data-stu-id="6b130-136">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="6b130-137">O conteúdo semente é selecionado por uma pessoa e é julgada para representar a categoria do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="6b130-137">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="6b130-138">Você precisa ter pelo menos 50 amostras positivas e até 500.</span><span class="sxs-lookup"><span data-stu-id="6b130-138">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="6b130-139">O classificador treinado será processado até os 500 exemplos criados mais recentes (por data de criação do arquivo/carimbo de hora).</span><span class="sxs-lookup"><span data-stu-id="6b130-139">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="6b130-140">Quanto mais amostras você fornecer, mais precisará das previsões que o classificador fará.</span><span class="sxs-lookup"><span data-stu-id="6b130-140">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

### <a name="testing-content"></a><span data-ttu-id="6b130-141">Testando conteúdo</span><span class="sxs-lookup"><span data-stu-id="6b130-141">Testing content</span></span>

<span data-ttu-id="6b130-142">Depois que o classificador treinado tiver processado exemplos positivos suficientes para criar um modelo de previsão, você precisará testar as previsões feitas para ver se o classificador pode distinguir corretamente os itens que correspondem à categoria e aos itens que não estão.</span><span class="sxs-lookup"><span data-stu-id="6b130-142">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="6b130-143">Para fazer isso, selecione outro, espero maior, um conjunto de conteúdo separado para o homem que consiste em exemplos que devem se enquadrar na categoria e exemplos que não.</span><span class="sxs-lookup"><span data-stu-id="6b130-143">You do this by selecting another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="6b130-144">Você deve testar com dados diferentes dos dados semente iniciais que você forneceu pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="6b130-144">You should test with different data than the initial seed data you first provided.</span></span> <span data-ttu-id="6b130-145">Depois de processá-los, você passará manualmente pelos resultados e verificará se cada previsão está correta, incorreta ou se não tem certeza.</span><span class="sxs-lookup"><span data-stu-id="6b130-145">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="6b130-146">O classificador treinado usa esse feedback para melhorar seu modelo de previsão.</span><span class="sxs-lookup"><span data-stu-id="6b130-146">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="6b130-147">Para obter melhores resultados, tenha pelo menos 200 itens em seu conjunto de amostra de teste com uma distribuição uniforme de correspondências positivas e negativas.</span><span class="sxs-lookup"><span data-stu-id="6b130-147">For best results, have at least 200 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="6b130-148">Como criar um classificador treinado</span><span class="sxs-lookup"><span data-stu-id="6b130-148">How to create a trainable classifier</span></span>

1. <span data-ttu-id="6b130-149">Coleta entre 50-500 itens de conteúdo semente.</span><span class="sxs-lookup"><span data-stu-id="6b130-149">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="6b130-150">Eles devem ser apenas exemplos que representam fortemente o tipo de conteúdo que você deseja que o classificador treinado identifique positivamente como estando na categoria de classificação.</span><span class="sxs-lookup"><span data-stu-id="6b130-150">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="6b130-151">Consulte, [extensões de nome de arquivo rastreado padrão e tipos de arquivo analisados no SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) para os tipos de arquivo com suporte.</span><span class="sxs-lookup"><span data-stu-id="6b130-151">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="6b130-152">Os itens de amostra de propagação e teste não devem ser criptografados e devem estar em inglês.</span><span class="sxs-lookup"><span data-stu-id="6b130-152">The seed and test sample items must not be encrypted and they must be in English.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="6b130-153">Certifique-se de que os itens em seu conjunto de propagação são exemplos **fortes** da categoria.</span><span class="sxs-lookup"><span data-stu-id="6b130-153">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="6b130-154">O classificador treinado inicialmente cria seu modelo com base no que você propaga com ele.</span><span class="sxs-lookup"><span data-stu-id="6b130-154">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="6b130-155">O classificador supõe que todos os exemplos de propagação são positivos fortes e não têm como saber se uma amostra é uma correspondência fraca ou negativa à categoria.</span><span class="sxs-lookup"><span data-stu-id="6b130-155">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="6b130-156">Coloque o conteúdo semente em uma pasta do SharePoint Online que seja dedicada a manter *somente o conteúdo semente*.</span><span class="sxs-lookup"><span data-stu-id="6b130-156">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="6b130-157">Anote o site, a biblioteca e a URL da pasta.</span><span class="sxs-lookup"><span data-stu-id="6b130-157">Make note of the site, library, and folder URL.</span></span>

   > [!TIP]
   > <span data-ttu-id="6b130-158">Se você criar um novo site e pasta para seus dados semente, permita que pelo menos uma hora para esse local seja indexado antes de criar o classificador treinado que usará esses dados de propagação.</span><span class="sxs-lookup"><span data-stu-id="6b130-158">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="6b130-159">Entre no centro de conformidade da Microsoft 365 com administrador de conformidade ou acesso à função de administrador de segurança e abra **o centro de conformidade** da Microsoft 365 ou a classificação de dados **do centro de segurança da Microsoft 365**  >  .</span><span class="sxs-lookup"><span data-stu-id="6b130-159">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**.</span></span>

4. <span data-ttu-id="6b130-160">Escolha a guia **classificadores estagiários** .</span><span class="sxs-lookup"><span data-stu-id="6b130-160">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="6b130-161">Escolha **criar classificador treinado**.</span><span class="sxs-lookup"><span data-stu-id="6b130-161">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="6b130-162">Preencha os valores apropriados para os `Name` `Description` campos e da categoria de itens que você deseja que esse classificador seja identificado.</span><span class="sxs-lookup"><span data-stu-id="6b130-162">Fill in appropriate values for the `Name` and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="6b130-163">Escolha o site, a biblioteca e a URL da pasta do SharePoint Online para o site de conteúdo semente da etapa 2.</span><span class="sxs-lookup"><span data-stu-id="6b130-163">Pick the SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="6b130-164">Escolha `Add` .</span><span class="sxs-lookup"><span data-stu-id="6b130-164">Choose `Add`.</span></span>

8. <span data-ttu-id="6b130-165">Revise as configurações e escolha `Create trainable classifier` .</span><span class="sxs-lookup"><span data-stu-id="6b130-165">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="6b130-166">Dentro de 24 horas, o classificador treinado processará os dados semente e criará um modelo de previsão.</span><span class="sxs-lookup"><span data-stu-id="6b130-166">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="6b130-167">O status do classificador é `In progress` enquanto processa os dados semente.</span><span class="sxs-lookup"><span data-stu-id="6b130-167">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="6b130-168">Quando o classificador terminar o processamento dos dados semente, o status mudará para `Need test items` .</span><span class="sxs-lookup"><span data-stu-id="6b130-168">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="6b130-169">Agora você pode exibir a página de detalhes escolhendo o classificador.</span><span class="sxs-lookup"><span data-stu-id="6b130-169">You can now view the details page by choosing the classifier.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6b130-170">![classificador de estagiário pronto para teste](../media/classifier-trainable-ready-to-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="6b130-170">![trainable classifier ready for testing](../media/classifier-trainable-ready-to-test-detail.png)</span></span>

11. <span data-ttu-id="6b130-171">Colete pelo menos 200 itens de conteúdo de teste (10.000 máx.) para obter os melhores resultados.</span><span class="sxs-lookup"><span data-stu-id="6b130-171">Collect at least 200 test content items (10,000 max) for best results.</span></span> <span data-ttu-id="6b130-172">Eles devem ser uma mistura de itens que são positivos fortes, negativos fortes e outros que são um pouco menos óbvios em sua natureza.</span><span class="sxs-lookup"><span data-stu-id="6b130-172">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="6b130-173">Consulte, [extensões de nome de arquivo rastreado padrão e tipos de arquivo analisados no SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) para os tipos de arquivo com suporte.</span><span class="sxs-lookup"><span data-stu-id="6b130-173">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6b130-174">Os itens de exemplo não devem ser criptografados e devem estar em inglês.</span><span class="sxs-lookup"><span data-stu-id="6b130-174">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="6b130-175">Coloque o conteúdo de teste em uma pasta do SharePoint Online que seja dedicada a conter *somente o conteúdo de teste*.</span><span class="sxs-lookup"><span data-stu-id="6b130-175">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="6b130-176">Anote o site, a biblioteca e a URL da pasta do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="6b130-176">Make note of the SharePoint Online site, library, and folder URL.</span></span>

    > [!TIP]
    > <span data-ttu-id="6b130-177">Se você criar um novo site e uma pasta para seus dados de teste, permita que pelo menos uma hora para esse local seja indexado antes de criar o classificador treinado que usará esses dados semente.</span><span class="sxs-lookup"><span data-stu-id="6b130-177">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="6b130-178">Escolha `Add items to test` .</span><span class="sxs-lookup"><span data-stu-id="6b130-178">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="6b130-179">Escolha o site, a biblioteca e a URL da pasta do SharePoint Online para o site de conteúdo de teste na etapa 12.</span><span class="sxs-lookup"><span data-stu-id="6b130-179">Pick the SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="6b130-180">Escolha `Add` .</span><span class="sxs-lookup"><span data-stu-id="6b130-180">Choose `Add`.</span></span>

15. <span data-ttu-id="6b130-181">Finalize o assistente escolhendo `Done` .</span><span class="sxs-lookup"><span data-stu-id="6b130-181">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="6b130-182">Seu classificador treinado levará até uma hora para processar os arquivos de teste.</span><span class="sxs-lookup"><span data-stu-id="6b130-182">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="6b130-183">Quando o classificador treinado termina de processar seus arquivos de teste, o status da página de detalhes será alterado para `Ready to review` .</span><span class="sxs-lookup"><span data-stu-id="6b130-183">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="6b130-184">Se você precisar aumentar o tamanho da amostra de teste, escolha `Add items to test` e permitir que o classificador treinado processe os itens adicionais.</span><span class="sxs-lookup"><span data-stu-id="6b130-184">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6b130-185">![Pronto para revisar captura de tela](../media/classifier-trainable-ready-to-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="6b130-185">![ready to review screenshot](../media/classifier-trainable-ready-to-review-detail.png)</span></span>

17. <span data-ttu-id="6b130-186">Escolha `Tested items to review` Tab para revisar itens.</span><span class="sxs-lookup"><span data-stu-id="6b130-186">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="6b130-187">A Microsoft 365 apresentará 30 itens por vez.</span><span class="sxs-lookup"><span data-stu-id="6b130-187">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="6b130-188">Examine-os e, na `We predict this item is "Relevant". Do you agree?` caixa, escolha `Yes` ou `No` ou `Not sure, skip to next item` .</span><span class="sxs-lookup"><span data-stu-id="6b130-188">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="6b130-189">A precisão do modelo é atualizada automaticamente após cada 30 itens.</span><span class="sxs-lookup"><span data-stu-id="6b130-189">Model accuracy is automatically updated after every 30 items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6b130-190">![caixa examinar itens](../media/classifier-trainable-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="6b130-190">![review items box](../media/classifier-trainable-review-detail.png)</span></span>

19. <span data-ttu-id="6b130-191">Revise *pelo menos* 200 itens.</span><span class="sxs-lookup"><span data-stu-id="6b130-191">Review *at least* 200 items.</span></span> <span data-ttu-id="6b130-192">Depois que a pontuação de precisão tiver estabilizado, a opção **publicar** ficará disponível e o status do classificador dirá `Ready to use` .</span><span class="sxs-lookup"><span data-stu-id="6b130-192">Once the accuracy score has stabilized, the **publish** option will become available and the classifier status will say `Ready to use`.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6b130-193">![Pontuação de precisão e pronto para publicar](../media/classifier-trainable-review-ready-to-publish.png)</span><span class="sxs-lookup"><span data-stu-id="6b130-193">![accuracy score and ready to publish](../media/classifier-trainable-review-ready-to-publish.png)</span></span>

20. <span data-ttu-id="6b130-194">Publicar o classificador.</span><span class="sxs-lookup"><span data-stu-id="6b130-194">Publish the classifier.</span></span>

21. <span data-ttu-id="6b130-195">Depois de publicado, o classificador estará disponível como uma condição na [rotulação automática do Office com rótulos de sensibilidade](apply-sensitivity-label-automatically.md), [aplicar automaticamente a política de rótulo de retenção com base em uma condição](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) e em [conformidade de comunicação](communication-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="6b130-195">Once published your classifier will be available as a condition in [Office auto-labeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [Communication compliance](communication-compliance.md).</span></span>
