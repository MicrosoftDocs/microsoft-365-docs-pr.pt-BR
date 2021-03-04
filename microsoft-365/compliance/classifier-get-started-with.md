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
description: Um classificador do Microsoft 365 é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo, dando a ele exemplos para ver. Este artigo mostra como criar e treinar um classificador personalizado e como retreiná-los para aumentar a precisão.
ms.openlocfilehash: a73acd7665cd23f13329bb5db4e890b0f3b0d861
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423290"
---
# <a name="get-started-with-trainable-classifiers"></a><span data-ttu-id="ca7c0-104">Comece com classificadores treináveis</span><span class="sxs-lookup"><span data-stu-id="ca7c0-104">Get started with trainable classifiers</span></span>

<span data-ttu-id="ca7c0-105">Um classificador de treinamento do Microsoft 365 é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo, dando a ele exemplos para ver.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-105">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="ca7c0-106">Depois de treinado, você pode usá-lo para identificar o item para a aplicação de rótulos de sensibilidade do Office, políticas de conformidade de comunicações e políticas de rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-106">Once trained, you can use it to identify item for application of Office sensitivity labels, Communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="ca7c0-107">A criação de um classificador treinável personalizado primeiro envolve dar a ele exemplos que são escolhidos por humanos e que corresponderão positivamente à categoria.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-107">Creating a custom trainable classifier first involves giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="ca7c0-108">Em seguida, depois de processá-los, você testa a capacidade dos classificadores de prever, dando a ele uma mistura de exemplos positivos e negativos.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-108">Then, after it has processed those, you test the classifiers ability to predict by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="ca7c0-109">Este artigo mostra como criar e treinar um classificador personalizado e como melhorar o desempenho de classificadores treinados personalizados e classificadores pré-treinados ao longo da vida através da retreinamento.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-109">This article shows you how to create and train a custom classifier and how to improve the performance of custom trainable classifiers and pre-trained classifiers over their lifetime through retraining.</span></span>

<span data-ttu-id="ca7c0-110">Para saber mais sobre os diferentes tipos de classificadores, consulte [Learn about trainable classifiers](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="ca7c0-110">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

<span data-ttu-id="ca7c0-111">Assista a este vídeo para um resumo rápido da criação de um classificador treinável.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-111">Watch this video for a quick summary of creating a trainable classifier.</span></span> <span data-ttu-id="ca7c0-112">Você ainda precisará ler este artigo completo para obter os detalhes.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-112">You'll still need to read this full article to get the details.</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGL7]


## <a name="prerequisites"></a><span data-ttu-id="ca7c0-113">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="ca7c0-113">Prerequisites</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="ca7c0-114">Requisitos de licença</span><span class="sxs-lookup"><span data-stu-id="ca7c0-114">Licensing requirements</span></span>

<span data-ttu-id="ca7c0-115">Classificadores são um recurso de Conformidade do Microsoft 365 E5 ou E5.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-115">Classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="ca7c0-116">Você deve ter uma dessas assinaturas para usá-las.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-116">You must have one of these subscriptions to make use of them.</span></span>

### <a name="permissions"></a><span data-ttu-id="ca7c0-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="ca7c0-117">Permissions</span></span>

<span data-ttu-id="ca7c0-118">Para acessar classificadores na interface do usuário:</span><span class="sxs-lookup"><span data-stu-id="ca7c0-118">To access classifiers in the UI:</span></span> 

- <span data-ttu-id="ca7c0-119">o administrador global precisa optar pelo locatário para criar classificadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-119">the Global admin needs to opt in for the tenant to create custom classifiers.</span></span>
- <span data-ttu-id="ca7c0-120">A função administrador de conformidade é necessária para treinar um classificador.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-120">Compliance Administrator role is required to train a classifier.</span></span>

<span data-ttu-id="ca7c0-121">Você precisará de contas com essas permissões para usar classificadores nesses cenários:</span><span class="sxs-lookup"><span data-stu-id="ca7c0-121">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="ca7c0-122">Cenário de política de rótulo de retenção: funções de Gerenciamento de Registros e Gerenciamento de Retenção</span><span class="sxs-lookup"><span data-stu-id="ca7c0-122">Retention label policy scenario: Record Management and Retention Management roles</span></span> 
- <span data-ttu-id="ca7c0-123">Cenário de política de rótulo de sensibilidade: Administrador de Segurança, Administrador de Conformidade, Administrador de Dados de Conformidade</span><span class="sxs-lookup"><span data-stu-id="ca7c0-123">Sensitivity label policy scenario: Security Administrator, Compliance Administrator, Compliance Data Administrator</span></span>
- <span data-ttu-id="ca7c0-124">Cenário de política de conformidade de comunicação: Administrador de Gerenciamento de Riscos do Insider, Administrador de Revisão de Supervisão</span><span class="sxs-lookup"><span data-stu-id="ca7c0-124">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="ca7c0-125">Por padrão, somente o usuário que cria um classificador personalizado pode treinar e revisar previsões feitas por esse classificador.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-125">By default, only the user who creates a custom classifier can train and review predictions made by that classifier.</span></span>

## <a name="prepare-for-a-custom-trainable-classifier"></a><span data-ttu-id="ca7c0-126">Preparar para um classificador de treinamento personalizado</span><span class="sxs-lookup"><span data-stu-id="ca7c0-126">Prepare for a custom trainable classifier</span></span> 

<span data-ttu-id="ca7c0-127">É útil entender o que está envolvido na criação de um classificador de treinamento personalizado antes de entrar.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-127">It's helpful to understand what's involved in creating a custom trainable classifier before you dive in.</span></span> 

### <a name="timeline"></a><span data-ttu-id="ca7c0-128">Linha do tempo</span><span class="sxs-lookup"><span data-stu-id="ca7c0-128">Timeline</span></span>

<span data-ttu-id="ca7c0-129">Essa linha do tempo reflete uma implantação de exemplo de classificadores treináveis.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-129">This timeline reflects a sample deployment of trainable classifiers.</span></span>

![trainable-classifier-timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="ca7c0-131">A aceitação é necessária pela primeira vez para classificadores que podem treinar.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-131">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="ca7c0-132">Leva doze dias para o Microsoft 365 concluir uma avaliação de linha de base do conteúdo de suas organizações.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-132">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span> <span data-ttu-id="ca7c0-133">Entre em contato com o administrador global para dar início ao processo de aceitação.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-133">Contact your global administrator to kick off the opt-in process.</span></span>

### <a name="overall-workflow"></a><span data-ttu-id="ca7c0-134">Fluxo de trabalho geral</span><span class="sxs-lookup"><span data-stu-id="ca7c0-134">Overall workflow</span></span>

<span data-ttu-id="ca7c0-135">Para entender mais sobre o fluxo de trabalho geral da criação de classificadores treináveis personalizados, consulte Fluxo de processos para criar classificadores de treinamento [do cliente.](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)</span><span class="sxs-lookup"><span data-stu-id="ca7c0-135">To understand more about the overall workflow of creating custom trainable classifiers, see [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).</span></span>

### <a name="seed-content"></a><span data-ttu-id="ca7c0-136">Conteúdo de sementes</span><span class="sxs-lookup"><span data-stu-id="ca7c0-136">Seed content</span></span>

<span data-ttu-id="ca7c0-137">Quando você deseja que um classificador treinável identifique de forma independente e precisa um item como sendo uma categoria específica de conteúdo, primeiro você precisa apresentá-lo com muitos exemplos do tipo de conteúdo que estão na categoria.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-137">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="ca7c0-138">Essa alimentação de amostras para o classificador treinável é conhecida como *semeamento*.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-138">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="ca7c0-139">O conteúdo de semente é selecionado por um humano e é considerado para representar a categoria de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-139">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="ca7c0-140">Você precisa ter pelo menos 50 amostras positivas e até 500.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-140">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="ca7c0-141">O classificador treinável processará até os 500 exemplos criados mais recentes (por arquivo criado data/carimbo de hora).</span><span class="sxs-lookup"><span data-stu-id="ca7c0-141">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="ca7c0-142">Quanto mais amostras você fornecer, mais precisas serão as previsões que o classificador fará.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-142">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

### <a name="testing-content"></a><span data-ttu-id="ca7c0-143">Testar conteúdo</span><span class="sxs-lookup"><span data-stu-id="ca7c0-143">Testing content</span></span>

<span data-ttu-id="ca7c0-144">Depois que o classificador treinável tiver processado amostras positivas suficientes para criar um modelo de previsão, você precisará testar as previsões que ele faz para ver se o classificador pode distinguir corretamente entre itens que corresponderem à categoria e itens que não são.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-144">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="ca7c0-145">Você faz isso selecionando outro conjunto, com sorte maior, de conteúdo escolhido humano que consiste em amostras que devem se enquadrar na categoria e em exemplos que não.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-145">You do this by selecting another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="ca7c0-146">Você deve testar com dados diferentes dos dados de semente iniciais fornecidos pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-146">You should test with different data than the initial seed data you first provided.</span></span> <span data-ttu-id="ca7c0-147">Depois de processá-los, você passa manualmente pelos resultados e verifica se cada previsão está correta, incorreta ou não.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-147">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="ca7c0-148">O classificador treinável usa esse feedback para melhorar seu modelo de previsão.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-148">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="ca7c0-149">Para melhores resultados, tenha pelo menos 200 itens no conjunto de amostras de teste com uma distribuição uniforme de resultados positivos e negativos.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-149">For best results, have at least 200 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="ca7c0-150">Como criar um classificador treinável</span><span class="sxs-lookup"><span data-stu-id="ca7c0-150">How to create a trainable classifier</span></span>

1. <span data-ttu-id="ca7c0-151">Coletar entre 50 e 500 itens de conteúdo de semente.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-151">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="ca7c0-152">Esses devem ser apenas exemplos que representam fortemente o tipo de conteúdo que você deseja que o classificador treinável identifique positivamente como estando na categoria de classificação.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-152">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="ca7c0-153">Consulte [Extensões de nome de arquivo](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) rastreado padrão e tipos de arquivo analisados no SharePoint Server para os tipos de arquivo com suporte.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-153">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="ca7c0-154">Os itens de amostra de semente e teste não devem ser criptografados e devem estar em inglês.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-154">The seed and test sample items must not be encrypted and they must be in English.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="ca7c0-155">Certifique-se de que os itens no conjunto de sementes sejam **exemplos** fortes da categoria.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-155">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="ca7c0-156">O classificador treinável cria inicialmente seu modelo com base no que você o semeou.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-156">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="ca7c0-157">O classificador supõe que todos os exemplos de semente são positivos fortes e não têm como saber se uma amostra é uma combinação fraca ou negativa com a categoria.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-157">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="ca7c0-158">Coloque o conteúdo de semente em uma pasta do SharePoint Online dedicada a manter o *conteúdo de semente somente*.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-158">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="ca7c0-159">Anote a URL do site, biblioteca e pasta.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-159">Make note of the site, library, and folder URL.</span></span>

   > [!TIP]
   > <span data-ttu-id="ca7c0-160">Se você criar um novo site e pasta para seus dados de semente, permita pelo menos uma hora para que esse local seja indexado antes de criar o classificador treinável que usará esses dados de semente.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-160">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="ca7c0-161">Entre no Centro de conformidade do Microsoft 365 com acesso a funções de administrador de conformidade ou de administrador de segurança e abra o Centro de conformidade do **Microsoft 365** ou a classificação de dados do Centro de Segurança do **Microsoft 365.**  >  </span><span class="sxs-lookup"><span data-stu-id="ca7c0-161">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**.</span></span>

4. <span data-ttu-id="ca7c0-162">Escolha a **guia Classificadores treináveis.**</span><span class="sxs-lookup"><span data-stu-id="ca7c0-162">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="ca7c0-163">Escolha **Criar classificador treinável**.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-163">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="ca7c0-164">Preencha os valores apropriados para os campos e da categoria de itens que você deseja que esse `Name` `Description` classificador treinável identifique.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-164">Fill in appropriate values for the `Name` and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="ca7c0-165">Escolha a URL de site, biblioteca e pasta do SharePoint Online para o site de conteúdo de semente na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-165">Pick the SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="ca7c0-166">Escolha `Add` .</span><span class="sxs-lookup"><span data-stu-id="ca7c0-166">Choose `Add`.</span></span>

8. <span data-ttu-id="ca7c0-167">Revise as configurações e escolha `Create trainable classifier` .</span><span class="sxs-lookup"><span data-stu-id="ca7c0-167">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="ca7c0-168">Dentro de 24 horas, o classificador treinável processará os dados de semente e criará um modelo de previsão.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-168">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="ca7c0-169">O status do classificador é `In progress` enquanto processa os dados de semente.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-169">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="ca7c0-170">Quando o classificador terminar de processar os dados de semente, o status muda para `Need test items` .</span><span class="sxs-lookup"><span data-stu-id="ca7c0-170">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="ca7c0-171">Agora você pode exibir a página de detalhes escolhendo o classificador.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-171">You can now view the details page by choosing the classifier.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca7c0-172">![classificador treinável pronto para teste](../media/classifier-trainable-ready-to-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="ca7c0-172">![trainable classifier ready for testing](../media/classifier-trainable-ready-to-test-detail.png)</span></span>

11. <span data-ttu-id="ca7c0-173">Colete pelo menos 200 itens de conteúdo de teste (10.000 no máximo) para melhores resultados.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-173">Collect at least 200 test content items (10,000 max) for best results.</span></span> <span data-ttu-id="ca7c0-174">Eles devem ser uma mistura de itens que são positivos fortes, negativos fortes e alguns que são um pouco menos óbvios em sua natureza.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-174">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="ca7c0-175">Consulte [Extensões de nome de arquivo](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) rastreado padrão e tipos de arquivo analisados no SharePoint Server para os tipos de arquivo com suporte.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-175">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ca7c0-176">Os itens de exemplo não devem ser criptografados e devem estar em inglês.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-176">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="ca7c0-177">Coloque o conteúdo de teste em uma pasta do SharePoint Online dedicada a manter *o conteúdo de teste somente*.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-177">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="ca7c0-178">Anote a URL de site, biblioteca e pasta do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-178">Make note of the SharePoint Online site, library, and folder URL.</span></span>

    > [!TIP]
    > <span data-ttu-id="ca7c0-179">Se você criar um novo site e uma pasta para seus dados de teste, permita pelo menos uma hora para que esse local seja indexado antes de criar o classificador treinável que usará esses dados de semente.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-179">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="ca7c0-180">Escolha `Add items to test` .</span><span class="sxs-lookup"><span data-stu-id="ca7c0-180">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="ca7c0-181">Escolha a URL de site, biblioteca e pasta do SharePoint Online para o site de conteúdo de teste na etapa 12.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-181">Pick the SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="ca7c0-182">Escolha `Add` .</span><span class="sxs-lookup"><span data-stu-id="ca7c0-182">Choose `Add`.</span></span>

15. <span data-ttu-id="ca7c0-183">Termine o assistente escolhendo `Done` .</span><span class="sxs-lookup"><span data-stu-id="ca7c0-183">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="ca7c0-184">O classificador treinável levará até uma hora para processar os arquivos de teste.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-184">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="ca7c0-185">Quando o classificador treinável terminar de processar seus arquivos de teste, o status na página de detalhes será alterado para `Ready to review` .</span><span class="sxs-lookup"><span data-stu-id="ca7c0-185">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="ca7c0-186">Se você precisar aumentar o tamanho do exemplo de teste, escolha e permita que o classificador treinável `Add items to test` processe os itens adicionais.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-186">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca7c0-187">![pronto para revisar captura de tela](../media/classifier-trainable-ready-to-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="ca7c0-187">![ready to review screenshot](../media/classifier-trainable-ready-to-review-detail.png)</span></span>

17. <span data-ttu-id="ca7c0-188">Escolha `Tested items to review` a guia para revisar itens.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-188">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="ca7c0-189">O Microsoft 365 apresentará 30 itens por vez.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-189">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="ca7c0-190">Revise-os `We predict this item is "Relevant". Do you agree?` e, na caixa, escolha `Yes` um ou ou `No` `Not sure, skip to next item` .</span><span class="sxs-lookup"><span data-stu-id="ca7c0-190">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="ca7c0-191">A precisão do modelo é atualizada automaticamente após cada 30 itens.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-191">Model accuracy is automatically updated after every 30 items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca7c0-192">![caixa de itens de revisão](../media/classifier-trainable-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="ca7c0-192">![review items box](../media/classifier-trainable-review-detail.png)</span></span>

19. <span data-ttu-id="ca7c0-193">Revise *pelo menos* 200 itens.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-193">Review *at least* 200 items.</span></span> <span data-ttu-id="ca7c0-194">Depois que a pontuação de precisão tiver estabilizado, a opção **de** publicação ficará disponível e o status do classificador dirá `Ready to use` .</span><span class="sxs-lookup"><span data-stu-id="ca7c0-194">Once the accuracy score has stabilized, the **publish** option will become available and the classifier status will say `Ready to use`.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca7c0-195">![pontuação de precisão e pronto para publicação](../media/classifier-trainable-review-ready-to-publish.png)</span><span class="sxs-lookup"><span data-stu-id="ca7c0-195">![accuracy score and ready to publish](../media/classifier-trainable-review-ready-to-publish.png)</span></span>

20. <span data-ttu-id="ca7c0-196">Publique o classificador.</span><span class="sxs-lookup"><span data-stu-id="ca7c0-196">Publish the classifier.</span></span>

21. <span data-ttu-id="ca7c0-197">Depois de publicado, o classificador estará disponível como uma condição na rotulagem automática do [Office](apply-sensitivity-label-automatically.md)com rótulos de [sensibilidade,](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) aplicar automaticamente a política de rótulo de retenção com base em uma condição e em Conformidade com [a comunicação.](communication-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="ca7c0-197">Once published your classifier will be available as a condition in [Office auto-labeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [Communication compliance](communication-compliance.md).</span></span>
