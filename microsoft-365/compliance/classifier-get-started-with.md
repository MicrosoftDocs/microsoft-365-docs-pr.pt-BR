---
title: Introdução aos classificadores de treinamento (visualização)
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
ms.openlocfilehash: 4c9f5dae702c71fe7f2da1ccbc0364e7bdd15b0e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636980"
---
# <a name="get-started-with-trainable-classifiers-preview"></a><span data-ttu-id="69b75-104">Introdução aos classificadores de treinamento (visualização)</span><span class="sxs-lookup"><span data-stu-id="69b75-104">Get started with trainable classifiers (preview)</span></span>

<span data-ttu-id="69b75-105">Um classificador Microsoft 365 treinado é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo dando amostras a eles.</span><span class="sxs-lookup"><span data-stu-id="69b75-105">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="69b75-106">Depois de treinado, você pode usá-lo para identificar o item para a aplicação de rótulos de confidencialidade do Office, políticas de conformidade de comunicações e políticas de rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="69b75-106">Once trained, you can use it to identify item for application of Office sensitivity labels, Communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="69b75-107">A criação de um classificador personalizável personalizado primeiro envolve fornecer amostras de ti de forma humana e coincidir positivamente a categoria.</span><span class="sxs-lookup"><span data-stu-id="69b75-107">Creating a custom trainable classifier first involves giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="69b75-108">Depois de ter processado esses, você testará a capacidade dos classificadores para prever dando a ele uma mistura de amostras positivas e negativas.</span><span class="sxs-lookup"><span data-stu-id="69b75-108">Then, after it has processed those, you test the classifiers ability to predict by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="69b75-109">Este artigo mostra como criar e treinar um classificador personalizado e como melhorar o desempenho de classificadores treinados personalizados e classificadores pré-qualificados em seu tempo de vida por meio de um retreinamento.</span><span class="sxs-lookup"><span data-stu-id="69b75-109">This article shows you how to create and train a custom classifier and how to improve the performance of custom trainable classifiers and pre-trained classifiers over their lifetime through retraining.</span></span>

<span data-ttu-id="69b75-110">Para saber mais sobre os diferentes tipos de classificadores, confira [saiba mais sobre classificadores estagiários (visualização)](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="69b75-110">To learn more about the different types of classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="69b75-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="69b75-111">Prerequisites</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="69b75-112">Requisitos de licença</span><span class="sxs-lookup"><span data-stu-id="69b75-112">Licensing requirements</span></span>

<span data-ttu-id="69b75-113">Os classificadores são um recurso de conformidade do Microsoft 365 E5 ou e5.</span><span class="sxs-lookup"><span data-stu-id="69b75-113">Classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="69b75-114">Você deve ter uma dessas assinaturas para usá-las.</span><span class="sxs-lookup"><span data-stu-id="69b75-114">You must have one of these subscriptions to make use of them.</span></span>

### <a name="permissions"></a><span data-ttu-id="69b75-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="69b75-115">Permissions</span></span>

<span data-ttu-id="69b75-116">Para acessar classificadores na interface do usuário:</span><span class="sxs-lookup"><span data-stu-id="69b75-116">To access classifiers in the UI:</span></span> 

- <span data-ttu-id="69b75-117">o administrador global precisa aceitar o locatário para criar classificadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="69b75-117">the Global admin needs to opt in for the tenant to create custom classifiers.</span></span>
- <span data-ttu-id="69b75-118">a função de administrador de conformidade ou o administrador de dados de conformidade é necessário para treinar um classificador.</span><span class="sxs-lookup"><span data-stu-id="69b75-118">the Compliance admin role or Compliance Data Administrator is required to train a classifier.</span></span>

<span data-ttu-id="69b75-119">Você precisará de contas com essas permissões para usar classificadores nestes cenários:</span><span class="sxs-lookup"><span data-stu-id="69b75-119">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="69b75-120">Cenário de política de rótulo de retenção: gerenciamento de registros e funções de gerenciamento de retenção</span><span class="sxs-lookup"><span data-stu-id="69b75-120">Retention label policy scenario: Record Management and Retention Management roles</span></span> 
- <span data-ttu-id="69b75-121">Cenário de política de rótulo de confidencialidade: administrador de segurança, administrador de conformidade, administrador de dados de conformidade</span><span class="sxs-lookup"><span data-stu-id="69b75-121">Sensitivity label policy scenario: Security Administrator, Compliance Administrator, Compliance Data Administrator</span></span>
- <span data-ttu-id="69b75-122">Cenário de política de conformidade de comunicação: administração de gerenciamento de risco do Insider, administrador de análise de supervisão</span><span class="sxs-lookup"><span data-stu-id="69b75-122">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="69b75-123">Por padrão, apenas o usuário que cria um classificador personalizado pode treinar e revisar previsões feitas por esse classificador.</span><span class="sxs-lookup"><span data-stu-id="69b75-123">By default, only the user who creates a custom classifier can train and review predictions made by that classifier.</span></span> <span data-ttu-id="69b75-124">Se quiser que outras pessoas possam treinar e revisar previsões de classificador, confira [fornecer aos outros direitos de treinamento e revisão](#give-others-train-and-review-rights).</span><span class="sxs-lookup"><span data-stu-id="69b75-124">If you want others to be able to train and review classifier predictions, see [Give others train and review rights](#give-others-train-and-review-rights).</span></span>

## <a name="prepare-for-a-custom-trainable-classifier"></a><span data-ttu-id="69b75-125">Preparar-se para um classificador treinado personalizado</span><span class="sxs-lookup"><span data-stu-id="69b75-125">Prepare for a custom trainable classifier</span></span> 

<span data-ttu-id="69b75-126">É útil entender o que está envolvido na criação de um classificador treinado personalizado antes de você se aprofundar no.</span><span class="sxs-lookup"><span data-stu-id="69b75-126">It's helpful to understand what's involved in creating a custom trainable classifier before you dive in.</span></span> 

### <a name="timeline"></a><span data-ttu-id="69b75-127">Linha do tempo</span><span class="sxs-lookup"><span data-stu-id="69b75-127">Timeline</span></span>

<span data-ttu-id="69b75-128">Esta linha do tempo reflete um exemplo de implantação de classificadores ferroviárias.</span><span class="sxs-lookup"><span data-stu-id="69b75-128">This timeline reflects a sample deployment of trainable classifiers.</span></span>

![Estagiário-classificador-linha do tempo](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="69b75-130">O consentimento é obrigatório pela primeira vez para os classificadores treináveis.</span><span class="sxs-lookup"><span data-stu-id="69b75-130">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="69b75-131">O Microsoft 365 leva 12 dias para concluir a avaliação da linha de base do conteúdo da sua organização.</span><span class="sxs-lookup"><span data-stu-id="69b75-131">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span> <span data-ttu-id="69b75-132">Entre em contato com seu administrador global para iniciar o processo de consentimento.</span><span class="sxs-lookup"><span data-stu-id="69b75-132">Contact your global administrator to kick off the opt-in process.</span></span>

### <a name="overall-workflow"></a><span data-ttu-id="69b75-133">Fluxo de trabalho geral</span><span class="sxs-lookup"><span data-stu-id="69b75-133">Overall workflow</span></span>

<span data-ttu-id="69b75-134">Para entender mais sobre o fluxo de trabalho geral de criação de classificadores destreinados personalizados, confira o [fluxo de processo para criar os classificadores estagiários do cliente](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).</span><span class="sxs-lookup"><span data-stu-id="69b75-134">To understand more about the overall workflow of creating custom trainable classifiers, see [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).</span></span>

### <a name="seed-content"></a><span data-ttu-id="69b75-135">Conteúdo semente</span><span class="sxs-lookup"><span data-stu-id="69b75-135">Seed content</span></span>

<span data-ttu-id="69b75-136">Quando você quiser um classificador treinado para identificar de forma independente e precisa um item como estando em uma categoria específica de conteúdo, primeiro é preciso apresentá-lo com vários exemplos do tipo de conteúdo que está na categoria.</span><span class="sxs-lookup"><span data-stu-id="69b75-136">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="69b75-137">Esta alimentação de amostras para o classificador treinado é conhecida como *propagação*.</span><span class="sxs-lookup"><span data-stu-id="69b75-137">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="69b75-138">O conteúdo semente é selecionado por uma pessoa e é julgada para representar a categoria do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="69b75-138">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="69b75-139">Você precisa ter pelo menos 50 amostras positivas e até 500.</span><span class="sxs-lookup"><span data-stu-id="69b75-139">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="69b75-140">O classificador treinado será processado até os 500 exemplos criados mais recentes (por data de criação do arquivo/carimbo de hora).</span><span class="sxs-lookup"><span data-stu-id="69b75-140">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="69b75-141">Quanto mais amostras você fornecer, mais precisará das previsões que o classificador fará.</span><span class="sxs-lookup"><span data-stu-id="69b75-141">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

### <a name="testing-content"></a><span data-ttu-id="69b75-142">Testando conteúdo</span><span class="sxs-lookup"><span data-stu-id="69b75-142">Testing content</span></span>

<span data-ttu-id="69b75-143">Depois que o classificador treinado tiver processado exemplos positivos suficientes para criar um modelo de previsão, você precisará testar as previsões feitas para ver se o classificador pode distinguir corretamente os itens que correspondem à categoria e aos itens que não estão.</span><span class="sxs-lookup"><span data-stu-id="69b75-143">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="69b75-144">Para fazer isso, selecione outro, espero maior, um conjunto de conteúdo separado para o homem que consiste em exemplos que devem se enquadrar na categoria e exemplos que não.</span><span class="sxs-lookup"><span data-stu-id="69b75-144">You do this by selecting another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="69b75-145">Você deve testar com dados diferentes dos dados semente iniciais que você forneceu pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="69b75-145">You should test with different data than the initial seed data you first provided.</span></span> <span data-ttu-id="69b75-146">Depois de processá-los, você passará manualmente pelos resultados e verificará se cada previsão está correta, incorreta ou se não tem certeza.</span><span class="sxs-lookup"><span data-stu-id="69b75-146">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="69b75-147">O classificador treinado usa esse feedback para melhorar seu modelo de previsão.</span><span class="sxs-lookup"><span data-stu-id="69b75-147">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="69b75-148">Para obter melhores resultados, tenha pelo menos 200 itens em seu conjunto de amostra de teste com uma distribuição uniforme de correspondências positivas e negativas.</span><span class="sxs-lookup"><span data-stu-id="69b75-148">For best results, have at least 200 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="69b75-149">Como criar um classificador treinado</span><span class="sxs-lookup"><span data-stu-id="69b75-149">How to create a trainable classifier</span></span>

1. <span data-ttu-id="69b75-150">Coleta entre 50-500 itens de conteúdo semente.</span><span class="sxs-lookup"><span data-stu-id="69b75-150">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="69b75-151">Eles devem ser apenas exemplos que representam fortemente o tipo de conteúdo que você deseja que o classificador treinado identifique positivamente como estando na categoria de classificação.</span><span class="sxs-lookup"><span data-stu-id="69b75-151">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="69b75-152">Consulte, [extensões de nome de arquivo rastreado padrão e tipos de arquivo analisados no SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) para os tipos de arquivo com suporte.</span><span class="sxs-lookup"><span data-stu-id="69b75-152">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="69b75-153">Os itens de amostra de propagação e teste não devem ser criptografados e devem estar em inglês.</span><span class="sxs-lookup"><span data-stu-id="69b75-153">The seed and test sample items must not be encrypted and they must be in English.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="69b75-154">Certifique-se de que os itens em seu conjunto de propagação são exemplos **fortes** da categoria.</span><span class="sxs-lookup"><span data-stu-id="69b75-154">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="69b75-155">O classificador treinado inicialmente cria seu modelo com base no que você propaga com ele.</span><span class="sxs-lookup"><span data-stu-id="69b75-155">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="69b75-156">O classificador supõe que todos os exemplos de propagação são positivos fortes e não têm como saber se uma amostra é uma correspondência fraca ou negativa à categoria.</span><span class="sxs-lookup"><span data-stu-id="69b75-156">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="69b75-157">Coloque o conteúdo semente em uma pasta do SharePoint Online que seja dedicada a manter *somente o conteúdo semente*.</span><span class="sxs-lookup"><span data-stu-id="69b75-157">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="69b75-158">Anote o site, a biblioteca e a URL da pasta.</span><span class="sxs-lookup"><span data-stu-id="69b75-158">Make note of the site, library, and folder URL.</span></span>

   > [!TIP]
   > <span data-ttu-id="69b75-159">Se você criar um novo site e pasta para seus dados semente, permita que pelo menos uma hora para esse local seja indexado antes de criar o classificador treinado que usará esses dados de propagação.</span><span class="sxs-lookup"><span data-stu-id="69b75-159">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="69b75-160">Entre no centro de conformidade da Microsoft 365 com administrador de conformidade ou acesso à função de administrador de segurança e abra **o centro de conformidade** da Microsoft 365 ou a classificação de dados **do centro de segurança da Microsoft 365**  >  **Data classification**.</span><span class="sxs-lookup"><span data-stu-id="69b75-160">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**.</span></span>

4. <span data-ttu-id="69b75-161">Escolha a guia **classificadores estagiários** .</span><span class="sxs-lookup"><span data-stu-id="69b75-161">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="69b75-162">Escolha **criar classificador treinado**.</span><span class="sxs-lookup"><span data-stu-id="69b75-162">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="69b75-163">Preencha os valores apropriados para os `Name` `Description` campos e da categoria de itens que você deseja que esse classificador seja identificado.</span><span class="sxs-lookup"><span data-stu-id="69b75-163">Fill in appropriate values for the `Name` and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="69b75-164">Escolha o site, a biblioteca e a URL da pasta do SharePoint Online para o site de conteúdo semente da etapa 2.</span><span class="sxs-lookup"><span data-stu-id="69b75-164">Pick the SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="69b75-165">Escolha `Add` .</span><span class="sxs-lookup"><span data-stu-id="69b75-165">Choose `Add`.</span></span>

8. <span data-ttu-id="69b75-166">Revise as configurações e escolha `Create trainable classifier` .</span><span class="sxs-lookup"><span data-stu-id="69b75-166">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="69b75-167">Dentro de 24 horas, o classificador treinado processará os dados semente e criará um modelo de previsão.</span><span class="sxs-lookup"><span data-stu-id="69b75-167">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="69b75-168">O status do classificador é `In progress` enquanto processa os dados semente.</span><span class="sxs-lookup"><span data-stu-id="69b75-168">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="69b75-169">Quando o classificador terminar o processamento dos dados semente, o status mudará para `Need test items` .</span><span class="sxs-lookup"><span data-stu-id="69b75-169">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="69b75-170">Agora você pode exibir a página de detalhes escolhendo o classificador.</span><span class="sxs-lookup"><span data-stu-id="69b75-170">You can now view the details page by choosing the classifier.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="69b75-171">![classificador de estagiário pronto para teste](../media/classifier-trainable-ready-to-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="69b75-171">![trainable classifier ready for testing](../media/classifier-trainable-ready-to-test-detail.png)</span></span>

11. <span data-ttu-id="69b75-172">Colete pelo menos 200 itens de conteúdo de teste (10.000 máx.) para obter os melhores resultados.</span><span class="sxs-lookup"><span data-stu-id="69b75-172">Collect at least 200 test content items (10,000 max) for best results.</span></span> <span data-ttu-id="69b75-173">Eles devem ser uma mistura de itens que são positivos fortes, negativos fortes e outros que são um pouco menos óbvios em sua natureza.</span><span class="sxs-lookup"><span data-stu-id="69b75-173">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="69b75-174">Consulte, [extensões de nome de arquivo rastreado padrão e tipos de arquivo analisados no SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) para os tipos de arquivo com suporte.</span><span class="sxs-lookup"><span data-stu-id="69b75-174">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="69b75-175">Os itens de exemplo não devem ser criptografados e devem estar em inglês.</span><span class="sxs-lookup"><span data-stu-id="69b75-175">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="69b75-176">Coloque o conteúdo de teste em uma pasta do SharePoint Online que seja dedicada a conter *somente o conteúdo de teste*.</span><span class="sxs-lookup"><span data-stu-id="69b75-176">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="69b75-177">Anote o site, a biblioteca e a URL da pasta do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="69b75-177">Make note of the SharePoint Online site, library, and folder URL.</span></span>

    > [!TIP]
    > <span data-ttu-id="69b75-178">Se você criar um novo site e uma pasta para seus dados de teste, permita que pelo menos uma hora para esse local seja indexado antes de criar o classificador treinado que usará esses dados semente.</span><span class="sxs-lookup"><span data-stu-id="69b75-178">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="69b75-179">Escolha `Add items to test` .</span><span class="sxs-lookup"><span data-stu-id="69b75-179">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="69b75-180">Escolha o site, a biblioteca e a URL da pasta do SharePoint Online para o site de conteúdo de teste na etapa 12.</span><span class="sxs-lookup"><span data-stu-id="69b75-180">Pick the SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="69b75-181">Escolha `Add` .</span><span class="sxs-lookup"><span data-stu-id="69b75-181">Choose `Add`.</span></span>

15. <span data-ttu-id="69b75-182">Finalize o assistente escolhendo `Done` .</span><span class="sxs-lookup"><span data-stu-id="69b75-182">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="69b75-183">Seu classificador treinado levará até uma hora para processar os arquivos de teste.</span><span class="sxs-lookup"><span data-stu-id="69b75-183">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="69b75-184">Quando o classificador treinado termina de processar seus arquivos de teste, o status da página de detalhes será alterado para `Ready to review` .</span><span class="sxs-lookup"><span data-stu-id="69b75-184">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="69b75-185">Se você precisar aumentar o tamanho da amostra de teste, escolha `Add items to test` e permitir que o classificador treinado processe os itens adicionais.</span><span class="sxs-lookup"><span data-stu-id="69b75-185">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="69b75-186">![Pronto para revisar captura de tela](../media/classifier-trainable-ready-to-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="69b75-186">![ready to review screenshot](../media/classifier-trainable-ready-to-review-detail.png)</span></span>

17. <span data-ttu-id="69b75-187">Escolha `Tested items to review` Tab para revisar itens.</span><span class="sxs-lookup"><span data-stu-id="69b75-187">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="69b75-188">A Microsoft 365 apresentará 30 itens por vez.</span><span class="sxs-lookup"><span data-stu-id="69b75-188">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="69b75-189">Examine-os e, na `We predict this item is "Relevant". Do you agree?` caixa, escolha `Yes` ou `No` ou `Not sure, skip to next item` .</span><span class="sxs-lookup"><span data-stu-id="69b75-189">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="69b75-190">A precisão do modelo é atualizada automaticamente após cada 30 itens.</span><span class="sxs-lookup"><span data-stu-id="69b75-190">Model accuracy is automatically updated after every 30 items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="69b75-191">![caixa examinar itens](../media/classifier-trainable-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="69b75-191">![review items box](../media/classifier-trainable-review-detail.png)</span></span>

19. <span data-ttu-id="69b75-192">Revise *pelo menos* 200 itens.</span><span class="sxs-lookup"><span data-stu-id="69b75-192">Review *at least* 200 items.</span></span> <span data-ttu-id="69b75-193">Depois que a pontuação de precisão tiver estabilizado, a opção **publicar** ficará disponível e o status do classificador dirá `Ready to use` .</span><span class="sxs-lookup"><span data-stu-id="69b75-193">Once the accuracy score has stabilized, the **publish** option will become available and the classifier status will say `Ready to use`.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="69b75-194">![Pontuação de precisão e pronto para publicar](../media/classifier-trainable-review-ready-to-publish.png)</span><span class="sxs-lookup"><span data-stu-id="69b75-194">![accuracy score and ready to publish](../media/classifier-trainable-review-ready-to-publish.png)</span></span>

20. <span data-ttu-id="69b75-195">Publicar o classificador.</span><span class="sxs-lookup"><span data-stu-id="69b75-195">Publish the classifier.</span></span>

21. <span data-ttu-id="69b75-196">Depois de publicado, o classificador estará disponível como uma condição na [rotulação automática do Office com rótulos de sensibilidade](apply-sensitivity-label-automatically.md), [aplicar automaticamente a política de rótulo de retenção com base em uma condição](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) e em [conformidade de comunicação](communication-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="69b75-196">Once published your classifier will be available as a condition in [Office auto-labeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [Communication compliance](communication-compliance.md).</span></span>

## <a name="give-others-train-and-review-rights"></a><span data-ttu-id="69b75-197">Fornecer aos outros direitos de treinamento e revisão</span><span class="sxs-lookup"><span data-stu-id="69b75-197">Give others train and review rights</span></span>

<span data-ttu-id="69b75-198">Use este procedimento para dar a outras permissões para treinar, revisar e ajustar seu classificador treinado personalizado.</span><span class="sxs-lookup"><span data-stu-id="69b75-198">Use this procedure to give others permissions to train, review and tune your custom trainable classifier.</span></span>  
 
1. <span data-ttu-id="69b75-199">Como criador do classificador, um administrador global de administração ou descoberta eletrônica conecta-se ao centro de conformidade usando o PowerShell usando os procedimentos em [conectar-se ao PowerShell do centro de conformidade & segurança](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="69b75-199">As the creator of the classifier, a global admin or eDiscovery admin connect to the Compliance center using PowerShell using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps&preserve-view=true).</span></span>

2. <span data-ttu-id="69b75-200">Execute este comando:</span><span class="sxs-lookup"><span data-stu-id="69b75-200">Run this command:</span></span>

   ```powershell
   Add-ComplianceCaseMember -Case "<classifier name>" -Member "<user or role group>"
   ```
   
   <span data-ttu-id="69b75-201">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="69b75-201">For example:</span></span>
   
   `Add-ComplianceCaseMember -Case "Financial Contract Classifier" -Member johnevans@contoso.com`

   <span data-ttu-id="69b75-202">Você pode executar esse comando várias vezes para adicionar vários usuários.</span><span class="sxs-lookup"><span data-stu-id="69b75-202">You can run this command multiple times to add multiple users.</span></span> <span data-ttu-id="69b75-203">Observe que você só pode adicionar grupos de função do Exchange Online Protection (EOP) e não grupos de função do Azure.</span><span class="sxs-lookup"><span data-stu-id="69b75-203">Note that you can only add Exchange Online Protection (EOP) Role Groups and not Azure Role Groups.</span></span>
