---
title: Criar um classificador
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba como criar um classificador
ms.openlocfilehash: 29b2a4775bec12649c66b4cb4a07fe5f0fc93ae2
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294897"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="7e434-103">Criar um classificador no Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="7e434-103">Create a classifier in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="7e434-104">O conteúdo deste artigo é para a visualização privada do projeto Cortex.</span><span class="sxs-lookup"><span data-stu-id="7e434-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="7e434-105">[Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="7e434-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="7e434-106">Um classificador é um tipo de modelo que você pode usar para automatizar a identificação e a classificação de um tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="7e434-106">A classifier is a type of model that you can use to automate identification and classification of a document type.</span></span> <span data-ttu-id="7e434-107">Por exemplo, talvez você queira identificar todos os documentos de *renovação de contrato* que são adicionados à sua biblioteca de documentos, como é mostrado na ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="7e434-107">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as is shown in the following illustration.</span></span>

![Documento de renovação do contrato](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="7e434-109">A criação de um classificador permite que você crie um novo [tipo de conteúdo do SharePoint](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) que será associado ao modelo.</span><span class="sxs-lookup"><span data-stu-id="7e434-109">Creating a classifier enables you to create a new [SharePoint Content Type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="7e434-110">Ao criar o classificador, você precisa criar *explicações* para definir o modelo.</span><span class="sxs-lookup"><span data-stu-id="7e434-110">When creating the classifier, you need to create *explanations* to define the model.</span></span> <span data-ttu-id="7e434-111">Isso permite que você observe dados comuns que você espera que encontrem consistentemente esse tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="7e434-111">This enables you to note common data that you would expect to consistently find this document type.</span></span> 

<span data-ttu-id="7e434-112">Use exemplos do tipo de documento ("exemplos de arquivos") para "treinar" seu modelo para identificar arquivos que possuem o mesmo tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="7e434-112">Use examples of the document type ("example files") to "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="7e434-113">Para criar um classificador, você precisa:</span><span class="sxs-lookup"><span data-stu-id="7e434-113">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="7e434-114">Nomeie seu modelo.</span><span class="sxs-lookup"><span data-stu-id="7e434-114">Name your model.</span></span>
2. <span data-ttu-id="7e434-115">Adicione seus arquivos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="7e434-115">Add your example files.</span></span>
3. <span data-ttu-id="7e434-116">Rotular seus arquivos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="7e434-116">Label your example files.</span></span>
4. <span data-ttu-id="7e434-117">Criar uma explicação.</span><span class="sxs-lookup"><span data-stu-id="7e434-117">Create an explanation.</span></span>
5. <span data-ttu-id="7e434-118">Teste seu modelo.</span><span class="sxs-lookup"><span data-stu-id="7e434-118">Test your model.</span></span>

> [!NOTE]
> <span data-ttu-id="7e434-119">Enquanto o modelo usa um classificador para identificar e classificar tipos de documento, você também pode optar por extrair partes específicas de informações de cada arquivo identificado pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="7e434-119">While your model uses a classifier to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="7e434-120">Faça isso criando um **extrator** para adicionar ao seu modelo.</span><span class="sxs-lookup"><span data-stu-id="7e434-120">Do this by creating an **extractor** to add to your model.</span></span> <span data-ttu-id="7e434-121">Confira [criar um extrator](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="7e434-121">See [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="7e434-122">Nomear seu modelo</span><span class="sxs-lookup"><span data-stu-id="7e434-122">Name your model</span></span>

<span data-ttu-id="7e434-123">A primeira etapa para criar seu modelo é dar um nome a ele:</span><span class="sxs-lookup"><span data-stu-id="7e434-123">The first step to create your model is to give it a name:</span></span>

1. <span data-ttu-id="7e434-124">No centro de conteúdo, selecione **novo**e, em seguida, **crie um modelo**.</span><span class="sxs-lookup"><span data-stu-id="7e434-124">From the Content Center, select **New**, and then **Create a model**.</span></span>
2. <span data-ttu-id="7e434-125">No painel **novo documento entendendo o modelo** , no campo **nome** , digite o nome do modelo.</span><span class="sxs-lookup"><span data-stu-id="7e434-125">In the **New document understanding model** pane, in the **Name** field type the name of the model.</span></span> <span data-ttu-id="7e434-126">Por exemplo, se você quiser identificar documentos de renovação de contrato, poderá nomear a *renovação do contrato*de modelo.</span><span class="sxs-lookup"><span data-stu-id="7e434-126">For example, if you want to identify contract renewal documents, you could name the model *Contract Renewal*.</span></span>
3. <span data-ttu-id="7e434-127">Escolha **Criar**.</span><span class="sxs-lookup"><span data-stu-id="7e434-127">Choose **Create**.</span></span> <span data-ttu-id="7e434-128">Isso cria uma home page para o modelo.</span><span class="sxs-lookup"><span data-stu-id="7e434-128">This creates a home page for the model.</span></span></br>

    ![Home Page do modelo do classificador](../media/content-understanding/model-home.png)

<span data-ttu-id="7e434-130">Ao criar um modelo, você também cria um novo tipo de conteúdo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7e434-130">When you create a model, you are also creating a new SharePoint content type.</span></span> <span data-ttu-id="7e434-131">Um tipo de conteúdo do SharePoint representa uma categoria de documentos que têm características comuns e compartilham uma coleção de colunas ou propriedades de metadados para esse conteúdo específico.</span><span class="sxs-lookup"><span data-stu-id="7e434-131">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="7e434-132">Os tipos de conteúdo do SharePoint são gerenciados por meio da [Galeria de tipos de conteúdo](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span><span class="sxs-lookup"><span data-stu-id="7e434-132">SharePoint Content Types are managed through the [Content types gallery](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span></span> <span data-ttu-id="7e434-133">Para este exemplo, ao criar o modelo, você está criando um novo tipo de conteúdo de *renovação de contrato* .</span><span class="sxs-lookup"><span data-stu-id="7e434-133">For this example, when you create the model, you are creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="7e434-134">Selecione **Configurações avançadas** se quiser mapear esse modelo para um tipo de conteúdo existente na Galeria de tipos de conteúdo do SharePoint para usar seu esquema.</span><span class="sxs-lookup"><span data-stu-id="7e434-134">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="7e434-135">Observe que, embora você possa usar um tipo de conteúdo existente para aproveitar o esquema para ajudar com a identificação e a classificação, ainda precisará treinar seu modelo para extrair informações de arquivos que ele identifica.</span><span class="sxs-lookup"><span data-stu-id="7e434-135">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you still need to train your model to extract information from files it identifies.</span></span></br>

![Configurações avançadas](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="7e434-137">Adicionar seus arquivos de exemplo</span><span class="sxs-lookup"><span data-stu-id="7e434-137">Add your example files</span></span>

<span data-ttu-id="7e434-138">Na home page do modelo, adicione seus arquivos de exemplos que você precisará para ajudar a treinar o modelo para identificar o tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="7e434-138">On the model home page, add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> <span data-ttu-id="7e434-139">Você deve usar os mesmos arquivos para o treinamento de classificador e [extrador](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="7e434-139">You should use the same files for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="7e434-140">Você sempre tem a opção de adicionar mais tarde, mas normalmente adiciona um conjunto completo de arquivos de amostra.</span><span class="sxs-lookup"><span data-stu-id="7e434-140">You always have the option to add more later, but typically you add a full set of sample files.</span></span> <span data-ttu-id="7e434-141">Rotule alguns para treinar seu modelo e testar os itens não rotulados restantes para avaliar a ADEQÜAÇÃO do modelo.</span><span class="sxs-lookup"><span data-stu-id="7e434-141">Label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="7e434-142">Para o seu conjunto de treinamento, você deseja usar exemplos positivos e negativos:</span><span class="sxs-lookup"><span data-stu-id="7e434-142">For your training set, you want to use both positive and negative examples:</span></span>
- <span data-ttu-id="7e434-143">Exemplo positivo: documentos que representam o tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="7e434-143">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="7e434-144">Eles contêm cadeias de caracteres e informações que sempre serão desse tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="7e434-144">These contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="7e434-145">Exemplo negativo: documentos que não representam o tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="7e434-145">Negative example: Documents that do not represent the document type.</span></span> <span data-ttu-id="7e434-146">Essas são as cadeias de caracteres e informações que precisam estar presentes neste tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="7e434-146">These are missing strings and information that needs to be present in this type of document.</span></span>

<span data-ttu-id="7e434-147">Certifique-se de usar pelo menos cinco exemplos positivos e pelo menos um exemplo negativo para treinar seu modelo.</span><span class="sxs-lookup"><span data-stu-id="7e434-147">Be sure to use at least five positive examples and at least one negative example to train your model.</span></span>  <span data-ttu-id="7e434-148">Você deseja criar outros para testar o modelo após o processo de treinamento.</span><span class="sxs-lookup"><span data-stu-id="7e434-148">You want to create additional ones to test your model after the training process.</span></span>

<span data-ttu-id="7e434-149">Para adicionar arquivos de exemplo:</span><span class="sxs-lookup"><span data-stu-id="7e434-149">To add sample files:</span></span>

1. <span data-ttu-id="7e434-150">Na página inicial do modelo, no bloco **biblioteca de amostra de compilação** , clique em **Adicionar arquivos**.</span><span class="sxs-lookup"><span data-stu-id="7e434-150">From the model home page, in the **Build sample library** tile, click **Add files**.</span></span>
2. <span data-ttu-id="7e434-151">Na página **selecionar arquivos de exemplo para o modelo** , selecione seus arquivos de exemplo na biblioteca arquivos de exemplo no centro de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="7e434-151">On the **Select sample files for your model** page, select your example files from the Sample files library in the Content Center.</span></span> <span data-ttu-id="7e434-152">Se você ainda não o carregou, clique em **carregar** para movê-los para a biblioteca de arquivos de amostra.</span><span class="sxs-lookup"><span data-stu-id="7e434-152">If you had not already uploaded them there, choose to upload them now by clicking **Upload** to move them the Sample file library.</span></span>
3. <span data-ttu-id="7e434-153">Depois de selecionar os arquivos de exemplo a serem usados para treinar o modelo, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="7e434-153">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![Selecionar arquivos de exemplo](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="7e434-155">Rotular seus arquivos de exemplo</span><span class="sxs-lookup"><span data-stu-id="7e434-155">Label your example files</span></span>

<span data-ttu-id="7e434-156">Após adicionar seus arquivos de exemplo, você precisa rotulá-los como exemplos positivos ou negativos.</span><span class="sxs-lookup"><span data-stu-id="7e434-156">After adding your example files, you need to label them as either positive or negative examples.</span></span>

1. <span data-ttu-id="7e434-157">Na página inicial do modelo, no bloco **classificar arquivos e executar treinamento** , clique em **treinar classificador**.</span><span class="sxs-lookup"><span data-stu-id="7e434-157">From the model home page, on the **Classify files and run training** tile, click **Train Classifier**.</span></span>
   <span data-ttu-id="7e434-158">Isso exibe a página de etiquetas que mostra uma listagem de seus arquivos de exemplo, com o primeiro arquivo visível no visualizador.</span><span class="sxs-lookup"><span data-stu-id="7e434-158">This displays the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="7e434-159">No visualizador na parte superior do primeiro arquivo de exemplo, você deve ver o texto perguntando se o arquivo é um exemplo do modelo que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="7e434-159">In the viewer on the top of the first example file, you should see text asking if the file is an example of the model you just created.</span></span> <span data-ttu-id="7e434-160">Se for um exemplo positivo, selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="7e434-160">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="7e434-161">Se for um exemplo negativo, selecione **não**.</span><span class="sxs-lookup"><span data-stu-id="7e434-161">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="7e434-162">Na lista de **exemplos rotulados** à esquerda, selecione arquivos adicionais que você deseja usar como exemplos e etiquete-los.</span><span class="sxs-lookup"><span data-stu-id="7e434-162">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them.</span></span> 

    ![Home Page do classificador](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> <span data-ttu-id="7e434-164">Rotule pelo menos cinco exemplos positivos e um exemplo negativo.</span><span class="sxs-lookup"><span data-stu-id="7e434-164">Label at least five positive examples, and one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="7e434-165">Criar uma explicação</span><span class="sxs-lookup"><span data-stu-id="7e434-165">Create an explanation</span></span>

<span data-ttu-id="7e434-166">A próxima etapa é criar uma explicação na página de treinamento.</span><span class="sxs-lookup"><span data-stu-id="7e434-166">The next step is for you to create an explanation on the Train page.</span></span> <span data-ttu-id="7e434-167">Uma explicação ajuda o modelo a entender como reconhecer o documento.</span><span class="sxs-lookup"><span data-stu-id="7e434-167">An explanation helps the model understand how to recognize the document.</span></span> <span data-ttu-id="7e434-168">Por exemplo, os documentos de renovação de contrato sempre contêm uma *solicitação para uma cadeia de texto de divulgação adicional* .</span><span class="sxs-lookup"><span data-stu-id="7e434-168">For example, the Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="7e434-169">Quando usada com extratores, uma explicação identifica a cadeia de caracteres que você deseja extrair do documento.</span><span class="sxs-lookup"><span data-stu-id="7e434-169">When used with extractors, an explanation identifies the string that you want to extract from the document.</span></span> 

<span data-ttu-id="7e434-170">Para criar uma explicação:</span><span class="sxs-lookup"><span data-stu-id="7e434-170">To create an explanation:</span></span>

1. <span data-ttu-id="7e434-171">Na página inicial do modelo, selecione a guia **treinamento** para ir para a página de treinamento.</span><span class="sxs-lookup"><span data-stu-id="7e434-171">From the model home page, select the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="7e434-172">Na página treinar, na seção **arquivos treinados** , você verá uma lista dos arquivos de exemplo que você nomeou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="7e434-172">On the Train page, in the **Trained files** section you should see a list of the sample files that you previously labeled.</span></span> <span data-ttu-id="7e434-173">Selecione um dos arquivos positivos da lista e exibido no visualizador.</span><span class="sxs-lookup"><span data-stu-id="7e434-173">Select one of the positive files from the list, and it displays in the viewer.</span></span>
3. <span data-ttu-id="7e434-174">Na seção explicação, selecione **novo** e em **branco**.</span><span class="sxs-lookup"><span data-stu-id="7e434-174">In the Explanation section, select **New** and then **Blank**.</span></span>
4. <span data-ttu-id="7e434-175">Na página **criar uma explicação** :</span><span class="sxs-lookup"><span data-stu-id="7e434-175">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="7e434-176">a.</span><span class="sxs-lookup"><span data-stu-id="7e434-176">a.</span></span> <span data-ttu-id="7e434-177">Digite o **nome** (por exemplo, "bloqueio de revelação").</span><span class="sxs-lookup"><span data-stu-id="7e434-177">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="7e434-178">b.</span><span class="sxs-lookup"><span data-stu-id="7e434-178">b.</span></span> <span data-ttu-id="7e434-179">Selecione o **tipo**.</span><span class="sxs-lookup"><span data-stu-id="7e434-179">Select the **Type**.</span></span> <span data-ttu-id="7e434-180">Para o exemplo, selecione **lista de frases**, pois você adiciona uma cadeia de caracteres de texto.</span><span class="sxs-lookup"><span data-stu-id="7e434-180">For the sample, select **Phrase list**, since you add a text string.</span></span></br>
    <span data-ttu-id="7e434-181">c.</span><span class="sxs-lookup"><span data-stu-id="7e434-181">c.</span></span> <span data-ttu-id="7e434-182">Na caixa **Digite aqui** , digite a cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7e434-182">In the **Type here** box, type the string.</span></span> <span data-ttu-id="7e434-183">Para o exemplo, adicione "solicitação para divulgação adicional".</span><span class="sxs-lookup"><span data-stu-id="7e434-183">For the sample, add "Request for additional disclosure".</span></span> <span data-ttu-id="7e434-184">Você pode selecionar diferenciar **maiúsculas de minúsculas** se a cadeia de caracteres precisa diferenciar maiúsculas de minúscula.</span><span class="sxs-lookup"><span data-stu-id="7e434-184">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="7e434-185">d.</span><span class="sxs-lookup"><span data-stu-id="7e434-185">d.</span></span> <span data-ttu-id="7e434-186">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7e434-186">Click **Save**.</span></span>

    ![Criar explicação](../media/content-understanding/explanation.png) 
    
 
5. <span data-ttu-id="7e434-188">O modelo agora verifica se a explicação que você criou era suficientemente boa para identificar os arquivos de exemplo rotulados restantes corretamente, como exemplos positivos e negativos.</span><span class="sxs-lookup"><span data-stu-id="7e434-188">The model now checks to see if the explanation you created was good enough to identify the remaining labeled example files correctly, as positive and negative examples.</span></span> <span data-ttu-id="7e434-189">Na seção arquivos treinados, verifique a coluna **avaliação** após a conclusão do treinamento para ver os resultados.</span><span class="sxs-lookup"><span data-stu-id="7e434-189">In the Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span> <span data-ttu-id="7e434-190">Os arquivos mostrarão um valor de **correspondência**, se as explicações que você criou forem suficientes para coincidir com o que foi rotulado como positivo ou negativo.</span><span class="sxs-lookup"><span data-stu-id="7e434-190">The files show a value of **Match**, if the explanations you created was enough to match what you labeled as positive or negative.</span></span>

    ![Valor de correspondência](../media/content-understanding/match.png) 

<span data-ttu-id="7e434-192">Se você receber uma **incompatibilidade** nos arquivos rotulados, talvez seja necessário criar uma explicação adicional para fornecer ao modelo mais informações para identificar o tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="7e434-192">If you receive a **Mismatch** on the labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="7e434-193">Se isso acontecer, clique no arquivo para obter mais informações sobre por que a incompatibilidade ocorreu.</span><span class="sxs-lookup"><span data-stu-id="7e434-193">If this happens, click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="7e434-194">Testar seu modelo</span><span class="sxs-lookup"><span data-stu-id="7e434-194">Test your model</span></span>

<span data-ttu-id="7e434-195">Se você recebeu uma correspondência em seus arquivos de amostra rotulados, agora você pode testar seu modelo em seus arquivos de exemplo não rotulados restantes.</span><span class="sxs-lookup"><span data-stu-id="7e434-195">If you received a match on your labeled sample files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="7e434-196">Na página inicial do modelo, selecione a guia **teste** .  Isso executa o modelo em seus arquivos de amostra sem rótulo.</span><span class="sxs-lookup"><span data-stu-id="7e434-196">From the model home page, select the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="7e434-197">Na lista **arquivos de teste** , seus arquivos de exemplo são exibidos e mostra se o modelo prevê que eles sejam positivos ou negativos.</span><span class="sxs-lookup"><span data-stu-id="7e434-197">In the **Test files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="7e434-198">Use essas informações para ajudar a determinar a eficácia do seu classificador na identificação de seus documentos.</span><span class="sxs-lookup"><span data-stu-id="7e434-198">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Teste de arquivos sem rótulo](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a><span data-ttu-id="7e434-200">Confira também</span><span class="sxs-lookup"><span data-stu-id="7e434-200">See Also</span></span>
[<span data-ttu-id="7e434-201">Criar um extrator</span><span class="sxs-lookup"><span data-stu-id="7e434-201">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="7e434-202">Visão geral da compreensão do documento</span><span class="sxs-lookup"><span data-stu-id="7e434-202">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="7e434-203">Criar um modelo de processamento de formulários</span><span class="sxs-lookup"><span data-stu-id="7e434-203">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="7e434-204">Aplicar um modelo</span><span class="sxs-lookup"><span data-stu-id="7e434-204">Apply a model</span></span>](apply-a-model.md) 
