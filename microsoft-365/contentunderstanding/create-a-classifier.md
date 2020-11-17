---
title: Criar um classificador
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Aprenda a criar um classificador
ms.openlocfilehash: 478b4253f7bb888323c2a873f3ab295cc841e193
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087674"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="0594b-103">Criar um classificador no Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="0594b-103">Create a classifier in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="0594b-104">Um classificador é um tipo de modelo que você pode usar para automatizar a identificação e a classificação de um tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="0594b-104">A classifier is a type of model that you can use to automate identification and classification of a document type.</span></span> <span data-ttu-id="0594b-105">Por exemplo, talvez você queira identificar toda os documentos de *Renovação de Contrato* que são adicionados à biblioteca de documentos, como o é mostrado na ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="0594b-105">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as is shown in the following illustration.</span></span>

![Documento de Renovação de Contrato](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="0594b-107">A criação de um classificador permite criar um novo [tipo de conteúdo do Microsoft Office SharePoint Online](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) que será associado ao modelo.</span><span class="sxs-lookup"><span data-stu-id="0594b-107">Creating a classifier enables you to create a new [SharePoint content type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="0594b-108">Ao criar o classificador, você precisa criar *explicações* para definir o modelo.</span><span class="sxs-lookup"><span data-stu-id="0594b-108">When creating the classifier, you need to create *explanations* to define the model.</span></span> <span data-ttu-id="0594b-109">Isso permite que você observe dados comuns que esperaria encontrar esse tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="0594b-109">This enables you to note common data that you would expect to consistently find this document type.</span></span> 

<span data-ttu-id="0594b-110">Use exemplos do tipo de documento ("arquivos de exemplo") para "treinar" seu modelo para identificar arquivos que têm o mesmo tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="0594b-110">Use examples of the document type ("example files") to "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="0594b-111">Para criar um classificador, você precisa:</span><span class="sxs-lookup"><span data-stu-id="0594b-111">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="0594b-112">Nomear seu modelo.</span><span class="sxs-lookup"><span data-stu-id="0594b-112">Name your model.</span></span>
2. <span data-ttu-id="0594b-113">Adicionar os arquivos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="0594b-113">Add your example files.</span></span>
3. <span data-ttu-id="0594b-114">Rotular os arquivos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="0594b-114">Label your example files.</span></span>
4. <span data-ttu-id="0594b-115">Criar uma explicação.</span><span class="sxs-lookup"><span data-stu-id="0594b-115">Create an explanation.</span></span>
5. <span data-ttu-id="0594b-116">Testar seu modelo.</span><span class="sxs-lookup"><span data-stu-id="0594b-116">Test your model.</span></span>

> [!NOTE]
> <span data-ttu-id="0594b-117">Enquanto o modelo usa um classificador para identificar e classificar os tipos de documento, você também pode optar por extrair informações específicas de cada arquivo identificado pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="0594b-117">While your model uses a classifier to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="0594b-118">Para fazer isso, crie um **extrator** para adicionar ao seu modelo.</span><span class="sxs-lookup"><span data-stu-id="0594b-118">Do this by creating an **extractor** to add to your model.</span></span> <span data-ttu-id="0594b-119">Confira [Criar um extrator](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="0594b-119">See [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="0594b-120">Nomeie seu modelo</span><span class="sxs-lookup"><span data-stu-id="0594b-120">Name your model</span></span>

<span data-ttu-id="0594b-121">A primeira etapa para criar seu modelo é dar um nome a ele:</span><span class="sxs-lookup"><span data-stu-id="0594b-121">The first step to create your model is to give it a name:</span></span>

1. <span data-ttu-id="0594b-122">No centro de conteúdo, selecione **Novo**, e depois **Criar um modelo**.</span><span class="sxs-lookup"><span data-stu-id="0594b-122">From the content center, select **New**, and then **Create a model**.</span></span>
2. <span data-ttu-id="0594b-123">No painel **Novo modelo de compreensão de documentos**, no campo **Nome**, digite o nome do modelo.</span><span class="sxs-lookup"><span data-stu-id="0594b-123">In the **New document understanding model** pane, in the **Name** field type the name of the model.</span></span> <span data-ttu-id="0594b-124">Por exemplo, se você deseja identificar documentos de renovação de contrato, nomeie o modelo como *Renovação de Contrato*.</span><span class="sxs-lookup"><span data-stu-id="0594b-124">For example, if you want to identify contract renewal documents, you could name the model *Contract Renewal*.</span></span>
3. <span data-ttu-id="0594b-125">Escolha **Criar**.</span><span class="sxs-lookup"><span data-stu-id="0594b-125">Choose **Create**.</span></span> <span data-ttu-id="0594b-126">Isso cria uma página inicial para o modelo.</span><span class="sxs-lookup"><span data-stu-id="0594b-126">This creates a home page for the model.</span></span></br>

    ![Home page do modelo de classificação](../media/content-understanding/model-home.png)

<span data-ttu-id="0594b-128">Ao criar um modelo, você também cria um novo tipo de conteúdo de site.</span><span class="sxs-lookup"><span data-stu-id="0594b-128">When you create a model, you are also creating a new site content type.</span></span> <span data-ttu-id="0594b-129">Um tipo de conteúdo representa uma categoria de documentos que tem características comuns e compartilha um conjunto de propriedades de colunas ou metadados para esse conteúdo específico.</span><span class="sxs-lookup"><span data-stu-id="0594b-129">A content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="0594b-130">Os tipos de conteúdo do Microsoft Office SharePoint Online são gerenciados através da [Galeria de tipos de conteúdos](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span><span class="sxs-lookup"><span data-stu-id="0594b-130">SharePoint content types are managed through the [Content types gallery](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span></span> <span data-ttu-id="0594b-131">Neste exemplo, quando você cria o modelo, está criando um novo tipo de conteúdo de *Renovação de Contrato*.</span><span class="sxs-lookup"><span data-stu-id="0594b-131">For this example, when you create the model, you are creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="0594b-132">Selecione **Configurações avançadas** se desejar mapear esse modelo para um tipo de conteúdo empresarial existente na Galeria de Tipos de conteúdo do SharePoint para usar o esquema.</span><span class="sxs-lookup"><span data-stu-id="0594b-132">Select **Advanced settings** if you want to map this model to an existing enterprise content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="0594b-133">Os tipos de conteúdo corporativo são armazenados no Hub de Tipo de Conteúdo no centro de administração do SharePoint e são agregados a todos os sites no locatário.</span><span class="sxs-lookup"><span data-stu-id="0594b-133">Enterprise content types are stored in the Content Type Hub in the SharePoint admin center and are syndicated to all sites in the tenant.</span></span> <span data-ttu-id="0594b-134">Observe que, embora você possa usar um tipo de conteúdo existente para aproveitar o esquema para ajudar na identificação e classificação, ainda é necessário treinar o seu modelo para extrair informações de arquivos que ele identifica.</span><span class="sxs-lookup"><span data-stu-id="0594b-134">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you still need to train your model to extract information from files it identifies.</span></span></br>

![Configurações avançadas](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="0594b-136">Adicionar arquivos de exemplo</span><span class="sxs-lookup"><span data-stu-id="0594b-136">Add your example files</span></span>

<span data-ttu-id="0594b-137">Na página inicial do modelo, adicione os arquivos de exemplo que você precisa para ajudar a treinar o seu tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="0594b-137">On the model home page, add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> <span data-ttu-id="0594b-138">Você deve usar os mesmos arquivos tanto para o classificador quanto para o [ Treinamento do extrator](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="0594b-138">You should use the same files for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="0594b-139">Você tem a opção de adicionar mais tarde, mas normalmente adicionará um conjunto completo de arquivos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="0594b-139">You always have the option to add more later, but typically you add a full set of example files.</span></span> <span data-ttu-id="0594b-140">Rotule alguns para treinar o seu modelo e testar as restantes não-rotulados para avaliar a adequação do modelo.</span><span class="sxs-lookup"><span data-stu-id="0594b-140">Label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="0594b-141">Para seu conjunto de treinamento, você vai querer usar exemplos positivos e negativos:</span><span class="sxs-lookup"><span data-stu-id="0594b-141">For your training set, you want to use both positive and negative examples:</span></span>
- <span data-ttu-id="0594b-142">Exemplo positivo: documentos que representam o tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="0594b-142">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="0594b-143">Eles contêm cadeias de caracteres e informações que estarão sempre neste tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="0594b-143">These contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="0594b-144">Exemplo negativo: qualquer outro documento que não representa o documento que você deseja classificar.</span><span class="sxs-lookup"><span data-stu-id="0594b-144">Negative example: Any other document that does not represent the document you want to classify.</span></span> 

<span data-ttu-id="0594b-145">Use pelo menos cinco exemplos positivos e pelo menos um exemplo negativo para treinar o seu modelo.</span><span class="sxs-lookup"><span data-stu-id="0594b-145">Be sure to use at least five positive examples and at least one negative example to train your model.</span></span>  <span data-ttu-id="0594b-146">Você vai precisar criar outras para testar o seu modelo após o processo de treinamento.</span><span class="sxs-lookup"><span data-stu-id="0594b-146">You want to create additional ones to test your model after the training process.</span></span>

<span data-ttu-id="0594b-147">Para adicionar arquivos de exemplo:</span><span class="sxs-lookup"><span data-stu-id="0594b-147">To add example files:</span></span>

1. <span data-ttu-id="0594b-148">Na página inicial do modelo, no bloco **Adicionar arquivos de exemplo**, clique em **Adicionar arquivos**.</span><span class="sxs-lookup"><span data-stu-id="0594b-148">On the model home page, in the **Add example files** tile, click **Add files**.</span></span>
2. <span data-ttu-id="0594b-149">Na página **selecione arquivos de exemplo para sua página de modelo**, selecione os arquivos de exemplo da biblioteca Arquivos de treinamento no centro de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="0594b-149">On the **Select example files for your model** page, select your example files from the Training files library in the content center.</span></span> <span data-ttu-id="0594b-150">Se você ainda não tiver carregado esses arquivos, clique em **Carregar** para copiá-los para a Biblioteca de arquivos de treinamento.</span><span class="sxs-lookup"><span data-stu-id="0594b-150">If you had not already uploaded them there, choose to upload them now by clicking **Upload** to copy them to the Training files library.</span></span>
3. <span data-ttu-id="0594b-151">Depois de selecionar os arquivos de exemplo que deseja usar para treinar o modelo, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="0594b-151">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![Selecione arquivos de exemplo](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="0594b-153">Rotule os arquivos de exemplo</span><span class="sxs-lookup"><span data-stu-id="0594b-153">Label your example files</span></span>

<span data-ttu-id="0594b-154">Depois de adicionar os arquivos de exemplo, é necessário rotulá-los como exemplos positivos ou negativos.</span><span class="sxs-lookup"><span data-stu-id="0594b-154">After adding your example files, you need to label them as either positive or negative examples.</span></span>

1. <span data-ttu-id="0594b-155">A partir da página inicial do modelo, no bloco **Classificar arquivos e executar treinamento**, clique em **Treinar classificador**.</span><span class="sxs-lookup"><span data-stu-id="0594b-155">From the model home page, on the **Classify files and run training** tile, click **Train classifier**.</span></span>
   <span data-ttu-id="0594b-156">Isso exibe a página de etiquetas que mostra uma lista de arquivos de exemplo, com o primeiro arquivo visível no visualizador.</span><span class="sxs-lookup"><span data-stu-id="0594b-156">This displays the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="0594b-157">No visualizador, na parte superior do primeiro arquivo de exemplo, você deve ver o texto perguntando se o arquivo é um exemplo do modelo que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="0594b-157">In the viewer on the top of the first example file, you should see text asking if the file is an example of the model you just created.</span></span> <span data-ttu-id="0594b-158">Se for um exemplo positivo, selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="0594b-158">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="0594b-159">Se for um exemplo negativo, selecione **Não**.</span><span class="sxs-lookup"><span data-stu-id="0594b-159">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="0594b-160">Na lista de **Exemplos rotulados** à esquerda, selecione arquivos adicionais que você deseja usar como exemplos e etiquete-los.</span><span class="sxs-lookup"><span data-stu-id="0594b-160">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them.</span></span> 

    ![Página inicial do classificador](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> <span data-ttu-id="0594b-162">Rotule pelo menos cinco exemplos positivos.</span><span class="sxs-lookup"><span data-stu-id="0594b-162">Label at least five positive examples.</span></span> <span data-ttu-id="0594b-163">Você também deve rotular pelo menos um exemplo negativo.</span><span class="sxs-lookup"><span data-stu-id="0594b-163">You must also label at least one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="0594b-164">Criar uma explicação</span><span class="sxs-lookup"><span data-stu-id="0594b-164">Create an explanation</span></span>

<span data-ttu-id="0594b-165">A próxima etapa é criar uma explicação na Página de treinamento.</span><span class="sxs-lookup"><span data-stu-id="0594b-165">The next step is for you to create an explanation on the Train page.</span></span> <span data-ttu-id="0594b-166">Uma explicação ajuda o modelo a entender como reconhecer o documento.</span><span class="sxs-lookup"><span data-stu-id="0594b-166">An explanation helps the model understand how to recognize the document.</span></span> <span data-ttu-id="0594b-167">Por exemplo, os documentos de Renovação de Contrato sempre contêm um cadeia de texto de *Solicitação de divulgação*.</span><span class="sxs-lookup"><span data-stu-id="0594b-167">For example, the Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="0594b-168">Quando usado com extratores, uma explicação identifica a cadeia que você deseja extrair do documento.</span><span class="sxs-lookup"><span data-stu-id="0594b-168">When used with extractors, an explanation identifies the string that you want to extract from the document.</span></span> 

<span data-ttu-id="0594b-169">Para criar uma explicação:</span><span class="sxs-lookup"><span data-stu-id="0594b-169">To create an explanation:</span></span>

1. <span data-ttu-id="0594b-170">Na página inicial do modelo, selecione a guia **Treinar** para ir para a página de treinamento.</span><span class="sxs-lookup"><span data-stu-id="0594b-170">From the model home page, select the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="0594b-171">Na página Treinar, na seção **Arquivos treinados**, você verá uma lista dos arquivos de exemplo que você rotulou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="0594b-171">On the Train page, in the **Trained files** section you should see a list of the sample files that you previously labeled.</span></span> <span data-ttu-id="0594b-172">Selecione um dos arquivos positivos na lista, e ele será exibido no visualizador.</span><span class="sxs-lookup"><span data-stu-id="0594b-172">Select one of the positive files from the list, and it displays in the viewer.</span></span>
3. <span data-ttu-id="0594b-173">Na seção Explicação, selecione **Nova** e, em seguida, **Em branco**.</span><span class="sxs-lookup"><span data-stu-id="0594b-173">In the Explanation section, select **New** and then **Blank**.</span></span>
4. <span data-ttu-id="0594b-174">Na página **Criar uma explicação**:</span><span class="sxs-lookup"><span data-stu-id="0594b-174">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="0594b-175">a.</span><span class="sxs-lookup"><span data-stu-id="0594b-175">a.</span></span> <span data-ttu-id="0594b-176">Digite o **Nome** (por exemplo, "Bloqueio de Divulgação").</span><span class="sxs-lookup"><span data-stu-id="0594b-176">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="0594b-177">b.</span><span class="sxs-lookup"><span data-stu-id="0594b-177">b.</span></span> <span data-ttu-id="0594b-178">Selecione o **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="0594b-178">Select the **Type**.</span></span> <span data-ttu-id="0594b-179">Para o exemplo, selecione **Lista de frases**, já que você adiciona uma cadeia de texto.</span><span class="sxs-lookup"><span data-stu-id="0594b-179">For the sample, select **Phrase list**, since you add a text string.</span></span></br>
    <span data-ttu-id="0594b-180">c.</span><span class="sxs-lookup"><span data-stu-id="0594b-180">c.</span></span> <span data-ttu-id="0594b-181">Na caixa **Digite aqui**, digite a cadeia.</span><span class="sxs-lookup"><span data-stu-id="0594b-181">In the **Type here** box, type the string.</span></span> <span data-ttu-id="0594b-182">Para o exemplo, adicione "Solicitar divulgação adicional".</span><span class="sxs-lookup"><span data-stu-id="0594b-182">For the sample, add "Request for additional disclosure".</span></span> <span data-ttu-id="0594b-183">Você pode selecionar **Diferenciar maiúsculas de minúsculas** se a cadeia precisar diferenciar maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0594b-183">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="0594b-184">d.</span><span class="sxs-lookup"><span data-stu-id="0594b-184">d.</span></span> <span data-ttu-id="0594b-185">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0594b-185">Click **Save**.</span></span>

    ![Criar explicação](../media/content-understanding/explanation.png) 
    
5. <span data-ttu-id="0594b-187">O Centro de Conteúdo agora verifica se a explicação que você criou está completa o suficiente para identificar corretamente os demais arquivos de exemplo rotulados, como exemplos positivos e negativos.</span><span class="sxs-lookup"><span data-stu-id="0594b-187">The Content Center now checks to see if the explanation you created is complete enough to identify the remaining labeled example files correctly, as positive and negative examples.</span></span> <span data-ttu-id="0594b-188">Na seção Arquivos Treinados, marque a coluna **Avaliação** após concluir o treinamento para ver os resultados.</span><span class="sxs-lookup"><span data-stu-id="0594b-188">In the Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span> <span data-ttu-id="0594b-189">Os arquivos mostram um valor de **Correspondência**, se as explicações que você criou foram o suficiente para corresponder ao que foi rotulado como positivo ou negativo.</span><span class="sxs-lookup"><span data-stu-id="0594b-189">The files show a value of **Match**, if the explanations you created was enough to match what you labeled as positive or negative.</span></span>

    ![Valor de correspondência](../media/content-understanding/match.png) 

<span data-ttu-id="0594b-191">Se você receber uma **incompatibilidade** nos arquivos rotulados, talvez seja necessário criar uma explicação adicional para fornecer informações sobre o modelo ao tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="0594b-191">If you receive a **Mismatch** on the labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="0594b-192">Se isso acontecer, clique no arquivo para saber mais sobre o motivo pelo qual a incompatibilidade ocorreu.</span><span class="sxs-lookup"><span data-stu-id="0594b-192">If this happens, click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="0594b-193">Testar seu modelo</span><span class="sxs-lookup"><span data-stu-id="0594b-193">Test your model</span></span>

<span data-ttu-id="0594b-194">Se você recebeu uma correspondência em seus arquivos de exemplo rotulados, agora você pode testar seu modelo em seus arquivos de exemplo não rotulados restantes que o modelo não tenha visto anteriormente.</span><span class="sxs-lookup"><span data-stu-id="0594b-194">If you received a match on your labeled sample files, you can now  test your model on your remaining unlabeled example files that the model has not seen before.</span></span>  <span data-ttu-id="0594b-195">Isso é opcional, mas uma etapa útil para avaliar a "adequação" ou prontidão do modelo antes de usá-lo, testando-o em arquivos que o modelo nunca viu antes.</span><span class="sxs-lookup"><span data-stu-id="0594b-195">This is optional, but a useful step to evaluate the “fitness” or readiness of the model before using it, by testing it on files the model hasn’t seen before.</span></span>

1. <span data-ttu-id="0594b-196">Na página inicial do modelo, selecione a guia **Testar**.  Isso executará o modelo em seus arquivos de exemplo não rotulados.</span><span class="sxs-lookup"><span data-stu-id="0594b-196">From the model home page, select the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="0594b-197">Na lista **Arquivos de teste**, os arquivos de exemplo são exibidos e mostram se o modelo os previu como positivos ou negativos.</span><span class="sxs-lookup"><span data-stu-id="0594b-197">In the **Test files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="0594b-198">Use essas informações para ajudá-lo a determinar a eficácia do seu classificador na identificação de seus documentos.</span><span class="sxs-lookup"><span data-stu-id="0594b-198">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Teste de arquivos não-rotulados](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a><span data-ttu-id="0594b-200">Confira também</span><span class="sxs-lookup"><span data-stu-id="0594b-200">See Also</span></span>
[<span data-ttu-id="0594b-201">Criar um extrator</span><span class="sxs-lookup"><span data-stu-id="0594b-201">Create an extractor</span></span>](create-an-extractor.md)

<span data-ttu-id="0594b-202">[Visão geral sobre Compreensão de Documentos](document-understanding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0594b-202">[Document Understanding overview](document-understanding-overview.md)</span></span>

[<span data-ttu-id="0594b-203">Tipos de explicação</span><span class="sxs-lookup"><span data-stu-id="0594b-203">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="0594b-204">Aplicar um modelo</span><span class="sxs-lookup"><span data-stu-id="0594b-204">Apply a model</span></span>](apply-a-model.md) 
