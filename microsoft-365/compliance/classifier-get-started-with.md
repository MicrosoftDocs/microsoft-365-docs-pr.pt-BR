---
title: Comece com classificadores treináveis
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
description: Um classificador do Microsoft 365 é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo, dando a ele exemplos para olhar. Este artigo mostra como criar e treinar um classificador personalizado e como restringi-los para aumentar a precisão.
ms.openlocfilehash: bca1de5edc3efd38f943b02091c3f47d832e6a19
ms.sourcegitcommit: 54d1a2f363b2d5b63aae258c3cec0573a08f2866
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49752655"
---
# <a name="get-started-with-trainable-classifiers"></a><span data-ttu-id="d5ad1-104">Comece com classificadores treináveis</span><span class="sxs-lookup"><span data-stu-id="d5ad1-104">Get started with trainable classifiers</span></span>

<span data-ttu-id="d5ad1-105">Um classificador de treinamento do Microsoft 365 é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo, dando a ele exemplos para olhar.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-105">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="d5ad1-106">Depois de treinado, você pode usá-lo para identificar o item para a aplicação de rótulos de sensibilidade do Office, políticas de conformidade de comunicações e políticas de rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-106">Once trained, you can use it to identify item for application of Office sensitivity labels, Communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="d5ad1-107">A criação de um classificador de treinamento personalizado primeiro envolve dar a ele amostras que são escolhidas por humanos e que são positivas se igualam à categoria.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-107">Creating a custom trainable classifier first involves giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="d5ad1-108">Em seguida, depois de processá-los, teste a capacidade dos classificadores de prever, dando a ele uma mistura de amostras positivas e negativas.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-108">Then, after it has processed those, you test the classifiers ability to predict by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="d5ad1-109">Este artigo mostra como criar e treinar um classificador personalizado e como melhorar o desempenho de classificadores de treinamento personalizados e classificadores previamente treinados durante sua vida útil por meio de treinamento.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-109">This article shows you how to create and train a custom classifier and how to improve the performance of custom trainable classifiers and pre-trained classifiers over their lifetime through retraining.</span></span>

<span data-ttu-id="d5ad1-110">Para saber mais sobre os diferentes tipos de classificadores, consulte Saiba mais [sobre classificadores de](classifier-learn-about.md)treinamento.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-110">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d5ad1-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d5ad1-111">Prerequisites</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="d5ad1-112">Requisitos de licença</span><span class="sxs-lookup"><span data-stu-id="d5ad1-112">Licensing requirements</span></span>

<span data-ttu-id="d5ad1-113">Classificadores são um recurso de Conformidade do Microsoft 365 E5 ou E5.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-113">Classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="d5ad1-114">Você deve ter uma dessas assinaturas para usá-las.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-114">You must have one of these subscriptions to make use of them.</span></span>

### <a name="permissions"></a><span data-ttu-id="d5ad1-115">Permissions</span><span class="sxs-lookup"><span data-stu-id="d5ad1-115">Permissions</span></span>

<span data-ttu-id="d5ad1-116">Para acessar classificadores na interface do usuário:</span><span class="sxs-lookup"><span data-stu-id="d5ad1-116">To access classifiers in the UI:</span></span> 

- <span data-ttu-id="d5ad1-117">o administrador global precisa optar pelo locatário para criar classificadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-117">the Global admin needs to opt in for the tenant to create custom classifiers.</span></span>
- <span data-ttu-id="d5ad1-118">A função administrador de conformidade é necessária para treinar um classificador.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-118">Compliance Administrator role is required to train a classifier.</span></span>

<span data-ttu-id="d5ad1-119">Você precisará de contas com essas permissões para usar classificadores nestes cenários:</span><span class="sxs-lookup"><span data-stu-id="d5ad1-119">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="d5ad1-120">Cenário de política de rótulo de retenção: funções de Gerenciamento de Registros e Gerenciamento de Retenção</span><span class="sxs-lookup"><span data-stu-id="d5ad1-120">Retention label policy scenario: Record Management and Retention Management roles</span></span> 
- <span data-ttu-id="d5ad1-121">Cenário de política de rótulo de sensibilidade: Administrador de Segurança, Administrador de Conformidade, Administrador de Dados de Conformidade</span><span class="sxs-lookup"><span data-stu-id="d5ad1-121">Sensitivity label policy scenario: Security Administrator, Compliance Administrator, Compliance Data Administrator</span></span>
- <span data-ttu-id="d5ad1-122">Cenário de política de conformidade de comunicação: Administrador de Gerenciamento de Riscos Insider, Administrador de Revisão de Supervisão</span><span class="sxs-lookup"><span data-stu-id="d5ad1-122">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d5ad1-123">Por padrão, somente o usuário que cria um classificador personalizado pode treinar e revisar as previsões feitas por esse classificador.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-123">By default, only the user who creates a custom classifier can train and review predictions made by that classifier.</span></span>

## <a name="prepare-for-a-custom-trainable-classifier"></a><span data-ttu-id="d5ad1-124">Preparar para um classificador de treinamento personalizado</span><span class="sxs-lookup"><span data-stu-id="d5ad1-124">Prepare for a custom trainable classifier</span></span> 

<span data-ttu-id="d5ad1-125">É útil entender o que está envolvido na criação de um classificador de treinamento personalizado antes de entrar.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-125">It's helpful to understand what's involved in creating a custom trainable classifier before you dive in.</span></span> 

### <a name="timeline"></a><span data-ttu-id="d5ad1-126">Linha do tempo</span><span class="sxs-lookup"><span data-stu-id="d5ad1-126">Timeline</span></span>

<span data-ttu-id="d5ad1-127">Essa linha do tempo reflete uma implantação de exemplo de classificadores de treinamento.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-127">This timeline reflects a sample deployment of trainable classifiers.</span></span>

![trainable-classifier-timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="d5ad1-129">A aceitação é necessária pela primeira vez para classificadores de treinamento.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-129">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="d5ad1-130">O Microsoft 365 leva doze dias para concluir uma avaliação de linha de base do conteúdo de suas organizações.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-130">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span> <span data-ttu-id="d5ad1-131">Entre em contato com seu administrador global para dar início ao processo de aceitação.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-131">Contact your global administrator to kick off the opt-in process.</span></span>

### <a name="overall-workflow"></a><span data-ttu-id="d5ad1-132">Fluxo de trabalho geral</span><span class="sxs-lookup"><span data-stu-id="d5ad1-132">Overall workflow</span></span>

<span data-ttu-id="d5ad1-133">Para entender mais sobre o fluxo de trabalho geral de criação de classificadores de treinamento personalizados, consulte o fluxo de processo para criar classificadores de treinamento [do cliente.](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)</span><span class="sxs-lookup"><span data-stu-id="d5ad1-133">To understand more about the overall workflow of creating custom trainable classifiers, see [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).</span></span>

### <a name="seed-content"></a><span data-ttu-id="d5ad1-134">Conteúdo da semente</span><span class="sxs-lookup"><span data-stu-id="d5ad1-134">Seed content</span></span>

<span data-ttu-id="d5ad1-135">Quando você quiser que um classificador de treinamento identifique de forma independente e precisa um item como estando em uma categoria específica de conteúdo, primeiro você precisa apresentá-lo com muitos exemplos do tipo de conteúdo que está na categoria.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-135">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="d5ad1-136">Essa alimentação de amostras para o classificador de treinamento é conhecida *como a semeação.*</span><span class="sxs-lookup"><span data-stu-id="d5ad1-136">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="d5ad1-137">O conteúdo da semente é selecionado por um humano e é destruído a representar a categoria de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-137">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="d5ad1-138">Você precisa ter pelo menos 50 amostras positivas e até 500.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-138">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="d5ad1-139">O classificador de treinamento processará até os 500 exemplos criados mais recentes (por carimbo de data/hora criado pelo arquivo).</span><span class="sxs-lookup"><span data-stu-id="d5ad1-139">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="d5ad1-140">Quanto mais amostras você fornecer, mais precisa será a previsão que o classificador fará.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-140">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

### <a name="testing-content"></a><span data-ttu-id="d5ad1-141">Testando conteúdo</span><span class="sxs-lookup"><span data-stu-id="d5ad1-141">Testing content</span></span>

<span data-ttu-id="d5ad1-142">Depois que o classificador de treinamento tiver processado amostras positivas suficientes para criar um modelo de previsão, você precisará testar as previsões que ele faz para ver se o classificador pode distinguir corretamente entre itens que corresponderem à categoria e itens que não fazem isso.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-142">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="d5ad1-143">Você pode fazer isso selecionando outro conjunto maior, com certeza, de conteúdo escolhido por humanos que consiste em exemplos que devem se enquadrar na categoria e em amostras que não se enquadram.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-143">You do this by selecting another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="d5ad1-144">Você deve testar com dados diferentes dos dados de pesquisa iniciais fornecidos pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-144">You should test with different data than the initial seed data you first provided.</span></span> <span data-ttu-id="d5ad1-145">Depois de processá-los, você passa manualmente pelos resultados e verifica se cada previsão está correta, incorreta ou se não tem certeza.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-145">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="d5ad1-146">O classificador de treinamento usa esse feedback para melhorar seu modelo de previsão.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-146">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="d5ad1-147">Para melhores resultados, tenha pelo menos 200 itens no conjunto de amostras de teste com uma distribuição uniforme de resultados positivos e negativos.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-147">For best results, have at least 200 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="d5ad1-148">Como criar um classificador de treinamento</span><span class="sxs-lookup"><span data-stu-id="d5ad1-148">How to create a trainable classifier</span></span>

1. <span data-ttu-id="d5ad1-149">Coletar entre 50 e 500 itens de conteúdo de semente.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-149">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="d5ad1-150">Esses devem ser apenas exemplos que representam fortemente o tipo de conteúdo que você deseja que o classificador de treinamento identifique positivamente como estando na categoria de classificação.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-150">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="d5ad1-151">Consulte [extensões de nome de arquivo rastreado padrão](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) e tipos de arquivo analisados no SharePoint Server para os tipos de arquivo com suporte.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-151">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="d5ad1-152">Os itens de exemplo de teste e de semente não devem ser criptografados e devem estar em inglês.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-152">The seed and test sample items must not be encrypted and they must be in English.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="d5ad1-153">Certifique-se de que os itens em seu conjunto de dados **sejam exemplos** fortes da categoria.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-153">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="d5ad1-154">O classificador inicializável cria seu modelo com base no que você o comou.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-154">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="d5ad1-155">O classificador supõe que todas as amostras de semente são fortes positivos e não tem como saber se uma amostra é uma combinação fraca ou negativa com a categoria.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-155">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="d5ad1-156">Coloque o conteúdo de semente em uma pasta do SharePoint Online que seja dedicada a manter o *conteúdo somente de dados.*</span><span class="sxs-lookup"><span data-stu-id="d5ad1-156">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="d5ad1-157">Anote o site, a biblioteca e a URL da pasta.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-157">Make note of the site, library, and folder URL.</span></span>

   > [!TIP]
   > <span data-ttu-id="d5ad1-158">Se você criar um novo site e pasta para os dados de sua pesquisa, permita que, pelo menos, uma hora para esse local seja indexado antes de criar o classificador de treinamento que usará esses dados de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-158">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="d5ad1-159">Entre no Centro de conformidade do Microsoft 365 com acesso à função de administrador de conformidade ou administrador de segurança e abra o Centro de conformidade do **Microsoft 365** ou centro de segurança do **Microsoft 365** Classificação de  >  **dados.**</span><span class="sxs-lookup"><span data-stu-id="d5ad1-159">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**.</span></span>

4. <span data-ttu-id="d5ad1-160">Escolha a **guia Classificadores De treinamento.**</span><span class="sxs-lookup"><span data-stu-id="d5ad1-160">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="d5ad1-161">Choose **Create trainable classifier**.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-161">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="d5ad1-162">Preencha os valores apropriados para os campos e a categoria de itens que você deseja que esse classificador de treinamento `Name` `Description` identifique.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-162">Fill in appropriate values for the `Name` and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="d5ad1-163">Escolha o site, a biblioteca e a URL da pasta do SharePoint Online para o site de conteúdo de dados de dados na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-163">Pick the SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="d5ad1-164">Escolha `Add` .</span><span class="sxs-lookup"><span data-stu-id="d5ad1-164">Choose `Add`.</span></span>

8. <span data-ttu-id="d5ad1-165">Revise as configurações e escolha `Create trainable classifier` .</span><span class="sxs-lookup"><span data-stu-id="d5ad1-165">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="d5ad1-166">Dentro de 24 horas, o classificador de treinamento processará os dados de pesquisa e criará um modelo de previsão.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-166">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="d5ad1-167">O status do classificador é `In progress` enquanto ele processa os dados de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-167">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="d5ad1-168">Quando o classificador terminar de processar os dados de semente, o status muda para `Need test items` .</span><span class="sxs-lookup"><span data-stu-id="d5ad1-168">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="d5ad1-169">Agora você pode exibir a página de detalhes escolhendo o classificador.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-169">You can now view the details page by choosing the classifier.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d5ad1-170">![classificador de treinamento pronto para teste](../media/classifier-trainable-ready-to-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="d5ad1-170">![trainable classifier ready for testing](../media/classifier-trainable-ready-to-test-detail.png)</span></span>

11. <span data-ttu-id="d5ad1-171">Coletar pelo menos 200 itens de conteúdo de teste (10.000 máx. ) para melhores resultados.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-171">Collect at least 200 test content items (10,000 max) for best results.</span></span> <span data-ttu-id="d5ad1-172">Eles devem ser uma mistura de itens que são fortes positivos, negativos fortes e alguns que são um pouco menos óbvios em sua natureza.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-172">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="d5ad1-173">Consulte [extensões de nome de arquivo rastreado padrão](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) e tipos de arquivo analisados no SharePoint Server para os tipos de arquivo com suporte.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-173">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d5ad1-174">Os itens de exemplo não devem ser criptografados e devem estar em inglês.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-174">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="d5ad1-175">Coloque o conteúdo de teste em uma pasta do SharePoint Online dedicada a manter *somente o conteúdo de teste.*</span><span class="sxs-lookup"><span data-stu-id="d5ad1-175">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="d5ad1-176">Anote o site, a biblioteca e a URL da pasta do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-176">Make note of the SharePoint Online site, library, and folder URL.</span></span>

    > [!TIP]
    > <span data-ttu-id="d5ad1-177">Se você criar um novo site e uma pasta para seus dados de teste, permita que pelo menos uma hora para esse local seja indexado antes de criar o classificador de treinamento que usará esses dados de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-177">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="d5ad1-178">Escolha `Add items to test` .</span><span class="sxs-lookup"><span data-stu-id="d5ad1-178">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="d5ad1-179">Escolha o site, a biblioteca e a URL da pasta do SharePoint Online para o site de conteúdo de teste na etapa 12.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-179">Pick the SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="d5ad1-180">Escolha `Add` .</span><span class="sxs-lookup"><span data-stu-id="d5ad1-180">Choose `Add`.</span></span>

15. <span data-ttu-id="d5ad1-181">Termine o assistente escolhendo `Done` .</span><span class="sxs-lookup"><span data-stu-id="d5ad1-181">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="d5ad1-182">O classificador de treinamento levará até uma hora para processar os arquivos de teste.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-182">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="d5ad1-183">Quando o classificador de treinamento terminar de processar seus arquivos de teste, o status na página de detalhes mudará para `Ready to review` .</span><span class="sxs-lookup"><span data-stu-id="d5ad1-183">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="d5ad1-184">Se você precisar aumentar o tamanho da amostra de teste, escolha e permita que o classificador de treinamento `Add items to test` processe os itens adicionais.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-184">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d5ad1-185">![pronto para revisar a captura de tela](../media/classifier-trainable-ready-to-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="d5ad1-185">![ready to review screenshot](../media/classifier-trainable-ready-to-review-detail.png)</span></span>

17. <span data-ttu-id="d5ad1-186">Escolha `Tested items to review` a guia para revisar itens.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-186">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="d5ad1-187">O Microsoft 365 apresentará 30 itens por vez.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-187">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="d5ad1-188">Revise-os e na `We predict this item is "Relevant". Do you agree?` caixa escolha um ou ou `Yes` `No` `Not sure, skip to next item` .</span><span class="sxs-lookup"><span data-stu-id="d5ad1-188">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="d5ad1-189">A precisão do modelo é atualizada automaticamente após cada 30 itens.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-189">Model accuracy is automatically updated after every 30 items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d5ad1-190">![review items box](../media/classifier-trainable-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="d5ad1-190">![review items box](../media/classifier-trainable-review-detail.png)</span></span>

19. <span data-ttu-id="d5ad1-191">Revise *pelo menos* 200 itens.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-191">Review *at least* 200 items.</span></span> <span data-ttu-id="d5ad1-192">Depois que a pontuação de precisão está estabilizada, a opção **de** publicação se tornará disponível e o status do classificador dirá `Ready to use` .</span><span class="sxs-lookup"><span data-stu-id="d5ad1-192">Once the accuracy score has stabilized, the **publish** option will become available and the classifier status will say `Ready to use`.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d5ad1-193">![pontuação de precisão e pronto para publicação](../media/classifier-trainable-review-ready-to-publish.png)</span><span class="sxs-lookup"><span data-stu-id="d5ad1-193">![accuracy score and ready to publish](../media/classifier-trainable-review-ready-to-publish.png)</span></span>

20. <span data-ttu-id="d5ad1-194">Publique o classificador.</span><span class="sxs-lookup"><span data-stu-id="d5ad1-194">Publish the classifier.</span></span>

21. <span data-ttu-id="d5ad1-195">Depois de publicado, o classificador estará disponível como uma condição na rotulagem automática do [Office](apply-sensitivity-label-automatically.md)com rótulos de [sensibilidade,](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) aplicar automaticamente a política de rótulo de retenção com base em uma condição e na conformidade [de comunicação.](communication-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="d5ad1-195">Once published your classifier will be available as a condition in [Office auto-labeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [Communication compliance](communication-compliance.md).</span></span>
