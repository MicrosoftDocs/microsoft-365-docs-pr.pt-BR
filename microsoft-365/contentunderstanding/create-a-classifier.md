---
title: Criar um classificador (visualização)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba como criar um classificador
ms.openlocfilehash: 088770ace8914b583b184c78c3ce110d9d68b4c7
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612603"
---
# <a name="create-a-classifier-preview"></a><span data-ttu-id="4cc15-103">Criar um classificador (visualização)</span><span class="sxs-lookup"><span data-stu-id="4cc15-103">Create a classifier (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="4cc15-104">O conteúdo deste artigo é para a visualização privada do Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="4cc15-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="4cc15-105">[Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="4cc15-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="4cc15-106">Um classificador é um tipo de modelo que automatiza a identificação e a classificação de um tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="4cc15-106">A classifier is a type of model that automates identification and classification of a document type.</span></span> <span data-ttu-id="4cc15-107">Por exemplo, talvez você queira identificar todos os documentos de *renovação de contrato* que são adicionados à sua biblioteca de documentos, como o seguinte.</span><span class="sxs-lookup"><span data-stu-id="4cc15-107">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as the following.</span></span>

![Documento de renovação do contrato](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="4cc15-109">A criação de um classificador criará um novo [tipo de conteúdo do SharePoint](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) que será associado ao modelo.</span><span class="sxs-lookup"><span data-stu-id="4cc15-109">Creating a classifier will create a new [SharePoint Content Type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="4cc15-110">Ao criar o classificador, você precisa criar *explicações* que ajudam a definir o modelo, observando dados comuns que você espera localizar de forma consistente para esse tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="4cc15-110">When creating the classifier, you need to create *explanations* that help to define the model by noting common data that you would expect to find consistently for this document type.</span></span> 

<span data-ttu-id="4cc15-111">Você usa exemplos do tipo de documento ("arquivos de exemplo") para ajudar a "treinar" seu modelo para identificar arquivos que possuem o mesmo tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="4cc15-111">You use examples of the document type ("example files") to help "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="4cc15-112">Para criar um classificador, você precisa:</span><span class="sxs-lookup"><span data-stu-id="4cc15-112">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="4cc15-113">Nomear seu modelo</span><span class="sxs-lookup"><span data-stu-id="4cc15-113">Name your model</span></span>
2. <span data-ttu-id="4cc15-114">Adicionar seus arquivos de exemplo</span><span class="sxs-lookup"><span data-stu-id="4cc15-114">Add your example files</span></span>
3. <span data-ttu-id="4cc15-115">Rotular seus arquivos de exemplo</span><span class="sxs-lookup"><span data-stu-id="4cc15-115">Label your example files</span></span>
4. <span data-ttu-id="4cc15-116">Criar uma explicação</span><span class="sxs-lookup"><span data-stu-id="4cc15-116">Create an explanation</span></span>
5. <span data-ttu-id="4cc15-117">Testar seu modelo</span><span class="sxs-lookup"><span data-stu-id="4cc15-117">Test your model</span></span> 

> [!Note]
> <span data-ttu-id="4cc15-118">Embora um classificador seja usado pelo modelo para identificar e classificar tipos de documento, você também pode optar por extrair partes específicas de informações de cada arquivo identificado pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="4cc15-118">While a classifier is used by your model to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="4cc15-119">Você faz isso criando um **extrator** para adicionar ao seu modelo, e isso é descrito em [criar um extrator](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="4cc15-119">You do this by creating an **extractor** to add to your model, and this is described in [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="4cc15-120">Nomear seu modelo</span><span class="sxs-lookup"><span data-stu-id="4cc15-120">Name your model</span></span>

<span data-ttu-id="4cc15-121">A primeira etapa é criar seu modelo no seu centro de conteúdo dando a ele um nome:</span><span class="sxs-lookup"><span data-stu-id="4cc15-121">The first step is to create your model in your Content Center by giving it a name:</span></span>

1. <span data-ttu-id="4cc15-122">No centro de conteúdo, clique em **novo**e em **criar um modelo**.</span><span class="sxs-lookup"><span data-stu-id="4cc15-122">In your Content Center, click **New**, and then click **Create a model**.</span></span>
2. <span data-ttu-id="4cc15-123">No painel **novo documento entendendo o modelo** , no campo **nome** , digite o nome do modelo.</span><span class="sxs-lookup"><span data-stu-id="4cc15-123">In the **New document understanding model** pane, in the **Name** field, type the name of the model.</span></span> <span data-ttu-id="4cc15-124">No nosso exemplo, se quisermos identificar documentos de renovação de contrato, podemos nomear essa *renovação de contrato*de modelo.</span><span class="sxs-lookup"><span data-stu-id="4cc15-124">For our example, if we want to identify contract renewal documents, we might name this model *Contract Renewal*.</span></span>
3. <span data-ttu-id="4cc15-125">Clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="4cc15-125">Click **Create**.</span></span> <span data-ttu-id="4cc15-126">Isso criará uma home page para o modelo.</span><span class="sxs-lookup"><span data-stu-id="4cc15-126">This will create a home page for the model.</span></span></br>

    ![Home Page do modelo do classificador](../media/content-understanding/model-home.png)

<span data-ttu-id="4cc15-128">Ao criar um modelo, você está criando um novo tipo de conteúdo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4cc15-128">When you create a model, you are creating a new SharePoint content type.</span></span> <span data-ttu-id="4cc15-129">Um tipo de conteúdo do SharePoint representa uma categoria de documentos que têm características comuns e compartilham uma coleção de colunas ou propriedades de metadados para esse conteúdo específico.</span><span class="sxs-lookup"><span data-stu-id="4cc15-129">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="4cc15-130">Os tipos de conteúdo do SharePoint são gerenciados por meio da [Galeria de tipos de conteúdo]().</span><span class="sxs-lookup"><span data-stu-id="4cc15-130">SharePoint Content Types are managed through the [Content types gallery]().</span></span> <span data-ttu-id="4cc15-131">No nosso exemplo, quando criamos o modelo, criaremos um novo tipo de conteúdo de *renovação de contrato* .</span><span class="sxs-lookup"><span data-stu-id="4cc15-131">For our example, when we create the model, we will be creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="4cc15-132">Selecione **Configurações avançadas** se quiser mapear esse modelo para um tipo de conteúdo existente na Galeria de tipos de conteúdo do SharePoint para usar seu esquema.</span><span class="sxs-lookup"><span data-stu-id="4cc15-132">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="4cc15-133">Observe que, embora você possa usar um tipo de conteúdo existente para aproveitar o esquema para ajudar com a identificação e a classificação, ainda será necessário treinar o modelo para extrair informações de arquivos que ele identifica.</span><span class="sxs-lookup"><span data-stu-id="4cc15-133">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you will still need to train your model to extract information from files it identifies.</span></span></br>

![Configurações avançadas](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="4cc15-135">Adicionar seus arquivos de exemplo</span><span class="sxs-lookup"><span data-stu-id="4cc15-135">Add your example files</span></span>

<span data-ttu-id="4cc15-136">Na home page do modelo, você pode adicionar seus arquivos de exemplos, será necessário para ajudar a treinar o modelo para identificar o tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="4cc15-136">On the model home page, you can add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!Note]
> <span data-ttu-id="4cc15-137">Os mesmos arquivos devem ser usados para o treinamento de classificador e [extrador](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="4cc15-137">The same files should be used for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="4cc15-138">Você sempre tem a opção de adicionar mais tarde, mas normalmente deve adicionar um conjunto completo de arquivos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="4cc15-138">You always have the option to add more later, but typically you should add a full set of example files.</span></span> <span data-ttu-id="4cc15-139">Você será rotulado algumas para treinar seu modelo e testar os itens não rotulados restantes para avaliar a ADEQÜAÇÃO do modelo.</span><span class="sxs-lookup"><span data-stu-id="4cc15-139">You will label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="4cc15-140">Para seu conjunto de treinamento, você vai querer usar exemplos positivos e exemplos negativos:</span><span class="sxs-lookup"><span data-stu-id="4cc15-140">For your training set, you will want to use both positive examples, and negative examples:</span></span>
- <span data-ttu-id="4cc15-141">Exemplo positivo: documentos que representam o tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="4cc15-141">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="4cc15-142">Eles contêm cadeias de caracteres e informações que sempre serão desse tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="4cc15-142">They contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="4cc15-143">Exemplo negativo: documentos que não representam o tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="4cc15-143">Negative example: Documents that do not represent the document type.</span></span>  <span data-ttu-id="4cc15-144">Estão faltando cadeias de caracteres e informações que precisam estar presentes neste tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="4cc15-144">They are missing strings and information that needs to be present in this type of document.</span></span>

<span data-ttu-id="4cc15-145">Você vai querer usar pelo menos cinco exemplos positivos e um dos exemplos negativos para treinar seu modelo.</span><span class="sxs-lookup"><span data-stu-id="4cc15-145">You will want to use at least five positive examples and one negative examples to train your model.</span></span>  <span data-ttu-id="4cc15-146">Você deverá ter outros para testar seu modelo após o treinamento.</span><span class="sxs-lookup"><span data-stu-id="4cc15-146">You will want to have additional ones to test your model after training.</span></span>

<span data-ttu-id="4cc15-147">Para adicionar arquivos de exemplo:</span><span class="sxs-lookup"><span data-stu-id="4cc15-147">To add sample files:</span></span>

1. <span data-ttu-id="4cc15-148">Na home page do modelo, no bloco **biblioteca de amostra de compilação** , clique em **Adicionar arquivos**.</span><span class="sxs-lookup"><span data-stu-id="4cc15-148">On the model home page, in the **Build sample library** tile, click **Add files**.</span></span>
2. <span data-ttu-id="4cc15-149">Na página **selecionar arquivos de exemplo para o modelo** , selecione seus arquivos de exemplo na biblioteca arquivos de exemplo no centro de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="4cc15-149">On the **Select sample files for your model** page, select your example files from the Sample files library in the Content Center.</span></span> <span data-ttu-id="4cc15-150">Se você ainda não o tiver carregado, poderá optar por carregá-los agora clicando em **carregar** para movê-los para a biblioteca de arquivos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="4cc15-150">If you had not already uploaded them there, you can choose to upload them now by clicking **Upload** to move them the Sample file library.</span></span>
3. <span data-ttu-id="4cc15-151">Depois de selecionar os arquivos de exemplo a serem usados para treinar o modelo, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4cc15-151">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![Selecionar arquivos de exemplo](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="4cc15-153">Rotular seus arquivos de exemplo</span><span class="sxs-lookup"><span data-stu-id="4cc15-153">Label your example files</span></span>

<span data-ttu-id="4cc15-154">Após adicionar seus arquivos de exemplo, você precisa rotulá-los como exemplos positivos ou como exemplos negativos.</span><span class="sxs-lookup"><span data-stu-id="4cc15-154">After adding your example files, you then need to label them as either positive examples or negative examples.</span></span>

1. <span data-ttu-id="4cc15-155">Na home page do modelo, no bloco **classificar arquivos e executar treinamento** , clique em **treinar classificador**.</span><span class="sxs-lookup"><span data-stu-id="4cc15-155">On the model home page, on the **Classify files and run training** tile, click **Train Classifier**.</span></span>
   <span data-ttu-id="4cc15-156">Isso exibirá a página de etiquetas que mostra uma listagem de seus arquivos de exemplo, com o primeiro arquivo visível no visualizador.</span><span class="sxs-lookup"><span data-stu-id="4cc15-156">This will display the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="4cc15-157">No visualizador, na parte superior do primeiro arquivo de exemplo, você verá um texto perguntando se o arquivo é um exemplo do modelo que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="4cc15-157">In the viewer, on the top of the first example file, you will see text asking you if the file is an example of the model you just created.</span></span> <span data-ttu-id="4cc15-158">Se for um exemplo positivo, selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="4cc15-158">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="4cc15-159">Se for um exemplo negativo, selecione **não**.</span><span class="sxs-lookup"><span data-stu-id="4cc15-159">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="4cc15-160">Na lista de **exemplos rotulados** à esquerda, selecione arquivos adicionais que você deseja usar como exemplos e etiquete-os também.</span><span class="sxs-lookup"><span data-stu-id="4cc15-160">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them as well.</span></span> 

    ![Home Page do modelo do classificador](../media/content-understanding/classifier-home-page.png) 


> [!Note]
> <span data-ttu-id="4cc15-162">Rotule pelo menos cinco exemplos positivos e um exemplo negativo.</span><span class="sxs-lookup"><span data-stu-id="4cc15-162">Label at least five positive examples, and one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="4cc15-163">Criar uma explicação</span><span class="sxs-lookup"><span data-stu-id="4cc15-163">Create an explanation</span></span>

<span data-ttu-id="4cc15-164">A próxima etapa é criar uma explicação na página de treinamento.</span><span class="sxs-lookup"><span data-stu-id="4cc15-164">The next step is to create an explanation on the Train page.</span></span>  <span data-ttu-id="4cc15-165">Uma explicação é uma dica ou pista para ajudar o modelo a entender como reconhecer este documento.</span><span class="sxs-lookup"><span data-stu-id="4cc15-165">An explanation is a hint or clue to help the model understand how to recognize this document.</span></span> <span data-ttu-id="4cc15-166">Por exemplo, nossos documentos de renovação de contrato sempre contêm uma *solicitação para uma cadeia de texto de divulgação adicional* .</span><span class="sxs-lookup"><span data-stu-id="4cc15-166">For example, our Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="4cc15-167">Quando usada com extratores, uma explicação é usada para identificar a cadeia de caracteres que você deseja extrair do documento.</span><span class="sxs-lookup"><span data-stu-id="4cc15-167">When used with extractors, an explanation is use to identify the string that you want to extract from the document.</span></span> 

<span data-ttu-id="4cc15-168">Para criar uma explicação:</span><span class="sxs-lookup"><span data-stu-id="4cc15-168">To create an explanation:</span></span>

1. <span data-ttu-id="4cc15-169">Na página inicial do modelo, clique na guia **treinamento** para ir para a página de treinamento.</span><span class="sxs-lookup"><span data-stu-id="4cc15-169">On the model home page, click the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="4cc15-170">Na página treinamento, na seção **arquivos treinados** , você verá uma lista dos arquivos de exemplo que você tinha rotulado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4cc15-170">On the Train page, in the **Trained files** section, you will see a list of the example files that you had labeled previously.</span></span> <span data-ttu-id="4cc15-171">Selecione um dos arquivos positivos da lista e ele será exibido no visualizador.</span><span class="sxs-lookup"><span data-stu-id="4cc15-171">Select one of your positive files from the list, and it will display in the viewer.</span></span>
3. <span data-ttu-id="4cc15-172">Na seção explicação, clique em **novo**e em **em branco**.</span><span class="sxs-lookup"><span data-stu-id="4cc15-172">In the Explanation section, click **New**, then click **Blank**.</span></span>
4. <span data-ttu-id="4cc15-173">Na página **criar uma explicação** :</span><span class="sxs-lookup"><span data-stu-id="4cc15-173">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="4cc15-174">a.</span><span class="sxs-lookup"><span data-stu-id="4cc15-174">a.</span></span> <span data-ttu-id="4cc15-175">Digite o **nome** (por exemplo, "bloqueio de revelação").</span><span class="sxs-lookup"><span data-stu-id="4cc15-175">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="4cc15-176">b.</span><span class="sxs-lookup"><span data-stu-id="4cc15-176">b.</span></span> <span data-ttu-id="4cc15-177">Selecione o **tipo**.</span><span class="sxs-lookup"><span data-stu-id="4cc15-177">Select the **Type**.</span></span> <span data-ttu-id="4cc15-178">No nosso exemplo, selecionaremos a **lista de frases**, já que estamos adicionando uma cadeia de caracteres de texto.</span><span class="sxs-lookup"><span data-stu-id="4cc15-178">For our example, we'll select **Phrase list**, since we are adding a text string.</span></span></br>
    <span data-ttu-id="4cc15-179">c.</span><span class="sxs-lookup"><span data-stu-id="4cc15-179">c.</span></span> <span data-ttu-id="4cc15-180">Na caixa **Digite aqui** , digite a cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="4cc15-180">In the **Type here** box, type the string.</span></span>  <span data-ttu-id="4cc15-181">No nosso exemplo, adicionaremos "solicitação para divulgação adicional".</span><span class="sxs-lookup"><span data-stu-id="4cc15-181">For our example, we'll add "Request for additional disclosure".</span></span> <span data-ttu-id="4cc15-182">Você pode selecionar diferenciar **maiúsculas de minúsculas** se a cadeia de caracteres precisa diferenciar maiúsculas de minúscula.</span><span class="sxs-lookup"><span data-stu-id="4cc15-182">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="4cc15-183">d.</span><span class="sxs-lookup"><span data-stu-id="4cc15-183">d.</span></span> <span data-ttu-id="4cc15-184">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4cc15-184">Click **Save**.</span></span>

    ![Criar explicação](../media/content-understanding/explanation.png) 
    
 
5.  <span data-ttu-id="4cc15-186">O modelo agora verificará se a explicação que você criou era suficientemente boa para identificar seus arquivos de exemplo rotulados remanescentes corretamente como exemplos positivos e negativos.</span><span class="sxs-lookup"><span data-stu-id="4cc15-186">The model will now check to see if the explanation you created was good enough to identify your remaining labeled example files correctly as positive and negative examples.</span></span> <span data-ttu-id="4cc15-187">Na seção arquivos treinados, verifique a coluna **avaliação** após a conclusão do treinamento para ver os resultados.</span><span class="sxs-lookup"><span data-stu-id="4cc15-187">In Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span>  <span data-ttu-id="4cc15-188">Os arquivos mostrarão um valor de **correspondência** se a explicação que você criou for suficiente para coincidir com o que foi rotulado como (positivo ou negativo).</span><span class="sxs-lookup"><span data-stu-id="4cc15-188">The files will show a value of **Match** if the explanation you created was enough to match what you had labeled them as (positive or negative).</span></span>

    ![Criar explicação](../media/content-understanding/match.png) 

<span data-ttu-id="4cc15-190">Se você receber uma **incompatibilidade** nos arquivos rotulados, talvez seja necessário criar uma explicação adicional para fornecer ao modelo mais informações para identificar o tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="4cc15-190">If you receive a **Mismatch** on your labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="4cc15-191">Você pode clicar no arquivo para obter mais informações sobre por que a incompatibilidade ocorreu.</span><span class="sxs-lookup"><span data-stu-id="4cc15-191">You can click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="4cc15-192">Testar seu modelo</span><span class="sxs-lookup"><span data-stu-id="4cc15-192">Test your model</span></span>

<span data-ttu-id="4cc15-193">Se você recebeu uma correspondência em seus arquivos de exemplo rotulados, agora você pode testar seu modelo em seus arquivos de exemplo não rotulados restantes.</span><span class="sxs-lookup"><span data-stu-id="4cc15-193">If you received a match on your labeled example files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="4cc15-194">Na home page do modelo, clique na guia **testar** .  Isso executará o modelo em seus arquivos de exemplo sem rótulo.</span><span class="sxs-lookup"><span data-stu-id="4cc15-194">On the model home page, click the **Test** tab.  This will run the model on your unlabeled example files.</span></span>
2. <span data-ttu-id="4cc15-195">Na lista de **arquivos de teste** , seus arquivos de exemplo serão exibidos e mostrará se o modelo prevê que eles são positivos ou negativos.</span><span class="sxs-lookup"><span data-stu-id="4cc15-195">In the **Test files** list, your example files will display and will show if the model predicted them to be positive or negative examples.</span></span> <span data-ttu-id="4cc15-196">Você pode usar essas informações para ajudar a determinar a eficácia do seu classificador na identificação de seus documentos.</span><span class="sxs-lookup"><span data-stu-id="4cc15-196">You can use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Teste de arquivos sem rótulo](../media/content-understanding/test-on-files.png) 



## <a name="see-also"></a><span data-ttu-id="4cc15-198">Confira também</span><span class="sxs-lookup"><span data-stu-id="4cc15-198">See Also</span></span>
[<span data-ttu-id="4cc15-199">Criar um extrator</span><span class="sxs-lookup"><span data-stu-id="4cc15-199">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="4cc15-200">Visão geral da compreensão do documento</span><span class="sxs-lookup"><span data-stu-id="4cc15-200">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="4cc15-201">Criar um modelo de processamento de formulários</span><span class="sxs-lookup"><span data-stu-id="4cc15-201">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="4cc15-202">Aplicar um modelo</span><span class="sxs-lookup"><span data-stu-id="4cc15-202">Apply a model</span></span>](apply-a-model.md) 




