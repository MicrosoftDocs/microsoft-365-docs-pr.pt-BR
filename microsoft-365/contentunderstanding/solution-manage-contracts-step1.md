---
title: Etapa 1. Use SharePoint Syntex para identificar arquivos de contrato e extrair dados
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/17/2021
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba como usar o SharePoint Syntex para identificar arquivos de contrato e extrair dados usando uma solução Microsoft 365.
ms.openlocfilehash: f246dd4ed619dd9885d2c45c69d607cfa9c2483f
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538550"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a><span data-ttu-id="63cd8-104">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="63cd8-104">Step 1.</span></span> <span data-ttu-id="63cd8-105">Use SharePoint Syntex para identificar arquivos de contrato e extrair dados</span><span class="sxs-lookup"><span data-stu-id="63cd8-105">Use SharePoint Syntex to identify contract files and extract data</span></span>

<span data-ttu-id="63cd8-106">Sua organização precisa de uma maneira de identificar e classificar todos os documentos de contrato dos muitos arquivos recebidos.</span><span class="sxs-lookup"><span data-stu-id="63cd8-106">Your organization needs a way to identify and classify all contract documents from the many files you receive.</span></span> <span data-ttu-id="63cd8-107">Você também deseja poder exibir rapidamente vários elementos-chave em cada um dos arquivos de contrato identificados (por exemplo, *Cliente,* Prestador de Serviços *e* Valor *da Taxa).*</span><span class="sxs-lookup"><span data-stu-id="63cd8-107">You also want to be able to quickly view several key elements in each of the contract files identified (for example, *Client*, *Contractor*, and *Fee amount*).</span></span> <span data-ttu-id="63cd8-108">Você pode fazer isso usando SharePoint [Syntex](index.md) para criar um modelo de compreensão de documentos e aplica-lo a uma biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="63cd8-108">You can do this by using [SharePoint Syntex](index.md) to create a document understanding model and applying it to a document library.</span></span>

## <a name="overview-of-the-process"></a><span data-ttu-id="63cd8-109">Visão geral do processo</span><span class="sxs-lookup"><span data-stu-id="63cd8-109">Overview of the process</span></span>

<span data-ttu-id="63cd8-110">[A compreensão do](document-understanding-overview.md) documento usa modelos de inteligência artificial (AI) para automatizar a classificação de arquivos e a extração de informações.</span><span class="sxs-lookup"><span data-stu-id="63cd8-110">[Document understanding](document-understanding-overview.md) uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="63cd8-111">Os modelos de compreensão de documentos também são ideais para extrair informações de documentos não estruturados e semiestruturados, onde as informações de que você precisa não estão contidas em tabelas ou formulários, como contratos.</span><span class="sxs-lookup"><span data-stu-id="63cd8-111">Document understanding models are also optimal in extracting information from unstructured and semi-structured documents where the information you need isn't contained in tables or forms, such as contracts.</span></span>

1. <span data-ttu-id="63cd8-112">Primeiro, você precisa encontrar pelo menos cinco arquivos de exemplo que você pode usar para "treinar" o modelo para pesquisar características específicas do tipo de conteúdo que você está tentando identificar (um contrato).</span><span class="sxs-lookup"><span data-stu-id="63cd8-112">First, you need to find at least five example files that you can use to "train" the model to search for characteristics that are specific to the content type you're trying to identify (a contract).</span></span> 

2. <span data-ttu-id="63cd8-113">Usando SharePoint Syntex, crie um novo modelo de compreensão de documentos.</span><span class="sxs-lookup"><span data-stu-id="63cd8-113">Using SharePoint Syntex, create a new document understanding model.</span></span> <span data-ttu-id="63cd8-114">Usando seus arquivos de exemplo, você precisa [criar um classificador](create-a-classifier.md).</span><span class="sxs-lookup"><span data-stu-id="63cd8-114">Using your example files, you need to [create a classifier](create-a-classifier.md).</span></span> <span data-ttu-id="63cd8-115">Ao treinar o classificador com seus arquivos de exemplo, você o ensina a pesquisar características específicas do que você verá nos contratos da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="63cd8-115">By training the classifier with your example files, you teach it to search for characteristics that are specific to what you would see in your company's contracts.</span></span> <span data-ttu-id="63cd8-116">Por exemplo, crie uma ["explicação"](create-a-classifier.md#create-an-explanation) que procure cadeias de caracteres específicas que estão em seus contratos, como Contrato de *Serviço,* Termos de Contrato *e* *Compensação.*</span><span class="sxs-lookup"><span data-stu-id="63cd8-116">For example, [create an "explanation"](create-a-classifier.md#create-an-explanation) that searches for specific strings that are in your contracts, such as *Service Agreement*, *Terms of Agreement*, and *Compensation*.</span></span> <span data-ttu-id="63cd8-117">Você pode até mesmo treinar sua explicação para procurar essas cadeias de caracteres em seções específicas do documento ou localizadas ao lado de outras cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="63cd8-117">You can even train your explanation to look for these strings in specific sections of the document, or located next to other strings.</span></span> <span data-ttu-id="63cd8-118">Quando você acha que treinou seu classificador com as informações necessárias, você pode testar seu modelo em um conjunto de exemplos de arquivos para ver o quão eficiente ele é.</span><span class="sxs-lookup"><span data-stu-id="63cd8-118">When you think you have trained your classifier with the information it needs, you can test your model on a sample set of example files to see how efficient it is.</span></span> <span data-ttu-id="63cd8-119">Após o teste, se necessário, você pode optar por fazer alterações em suas explicações para torná-las mais eficientes.</span><span class="sxs-lookup"><span data-stu-id="63cd8-119">After testing, if needed you can choose to make changes to your explanations to make them more efficient.</span></span> 

3. <span data-ttu-id="63cd8-120">Em seu modelo, você pode [criar um extrator](create-an-extractor.md) para extrair partes específicas de dados de cada contrato.</span><span class="sxs-lookup"><span data-stu-id="63cd8-120">In your model, you can [create an extractor](create-an-extractor.md) to pull out specific pieces of data from each contract.</span></span> <span data-ttu-id="63cd8-121">Por exemplo, para cada contrato, as informações que você mais se preocupa são quem é o cliente, o nome do prestador de serviços e o custo total.</span><span class="sxs-lookup"><span data-stu-id="63cd8-121">For example, for each contract, the information you're most concerned about is who the client is, the name of the contractor, and the total cost.</span></span>

4. <span data-ttu-id="63cd8-122">Depois de criar seu modelo com êxito, [aplique-o a](apply-a-model.md)uma SharePoint de documentos.</span><span class="sxs-lookup"><span data-stu-id="63cd8-122">After you successfully create your model, [apply it to a SharePoint document library](apply-a-model.md).</span></span> <span data-ttu-id="63cd8-123">À medida que você carrega documentos na biblioteca de documentos, seu modelo de compreensão de documentos será executado e identificará e classificará todos os arquivos que corresponderem ao tipo de conteúdo de contratos definido em seu modelo.</span><span class="sxs-lookup"><span data-stu-id="63cd8-123">As you upload documents to the document library, your document understanding model will run and will identify and classify all files that match the contracts content type you defined in your model.</span></span> <span data-ttu-id="63cd8-124">Todos os arquivos classificados como contratos serão exibidos em um exibição de biblioteca personalizado.</span><span class="sxs-lookup"><span data-stu-id="63cd8-124">All files that are classified as contracts will display in a custom library view.</span></span> <span data-ttu-id="63cd8-125">Os arquivos também exibirão os valores de cada contrato que você definiu em seu extrator.</span><span class="sxs-lookup"><span data-stu-id="63cd8-125">The files will also display the values from each contract that you defined in your extractor.</span></span>

   ![Contratos na biblioteca de documentos](../media/content-understanding/doc-lib-solution.png)

5. <span data-ttu-id="63cd8-127">Se você tiver requisitos de retenção para seus [](apply-a-retention-label-to-a-model.md) contratos, também poderá usar seu modelo para aplicar um rótulo de retenção que impedirá que seus contratos sejam excluídos por um período de tempo especificado.</span><span class="sxs-lookup"><span data-stu-id="63cd8-127">If you have retention requirements for your contracts, you can also use your model to [apply a retention label](apply-a-retention-label-to-a-model.md) that will prevent your contracts from being deleted for a specified period of time.</span></span>

## <a name="steps-to-create-and-train-your-model"></a><span data-ttu-id="63cd8-128">Etapas para criar e treinar seu modelo</span><span class="sxs-lookup"><span data-stu-id="63cd8-128">Steps to create and train your model</span></span>

> [!NOTE]
> <span data-ttu-id="63cd8-129">Para essas etapas, você pode usar os arquivos de exemplo no repositório de Exemplos SharePoint [Syntex da Microsoft.](https://github.com/pnp/syntex-samples)</span><span class="sxs-lookup"><span data-stu-id="63cd8-129">For these steps, you can use the example files in the [Microsoft SharePoint Syntex Samples repository](https://github.com/pnp/syntex-samples).</span></span> <span data-ttu-id="63cd8-130">Os exemplos neste repositório contêm os arquivos de modelo de compreensão do documento e os arquivos usados para treinar o modelo.</span><span class="sxs-lookup"><span data-stu-id="63cd8-130">The samples in this repository contain both the document understanding model files and the files used to train the model.</span></span>

### <a name="create-a-contract-model"></a><span data-ttu-id="63cd8-131">Criar um modelo de contrato</span><span class="sxs-lookup"><span data-stu-id="63cd8-131">Create a Contract model</span></span>

<span data-ttu-id="63cd8-132">A primeira etapa é criar seu modelo de contrato.</span><span class="sxs-lookup"><span data-stu-id="63cd8-132">The first step is to create your Contract model.</span></span>

1. <span data-ttu-id="63cd8-133">No centro de conteúdo, selecione **Novo**, e depois **Criar um modelo**.</span><span class="sxs-lookup"><span data-stu-id="63cd8-133">From the content center, select **New**, and then **Create a model**.</span></span>

2. <span data-ttu-id="63cd8-134">No painel **Novo modelo de compreensão de** documento, no campo **Nome,** digite o nome do modelo.</span><span class="sxs-lookup"><span data-stu-id="63cd8-134">On the **New document understanding model** pane, in the **Name** field, type the name of the model.</span></span> <span data-ttu-id="63cd8-135">Para essa solução de gerenciamento de contrato, você pode nomear o modelo *Contract*.</span><span class="sxs-lookup"><span data-stu-id="63cd8-135">For this contract management solution, you can name the model *Contract*.</span></span>

4. <span data-ttu-id="63cd8-136">Escolha **Criar**.</span><span class="sxs-lookup"><span data-stu-id="63cd8-136">Choose **Create**.</span></span> <span data-ttu-id="63cd8-137">Isso cria uma página inicial para o modelo.</span><span class="sxs-lookup"><span data-stu-id="63cd8-137">This creates a home page for the model.</span></span></br>

    ![Captura de tela da home page Do contrato.](../media/content-understanding/models-contract-home-page.png)


### <a name="train-your-model-to-classify-a-type-of-file"></a><span data-ttu-id="63cd8-139">Treine seu modelo para classificar um tipo de arquivo</span><span class="sxs-lookup"><span data-stu-id="63cd8-139">Train your model to classify a type of file</span></span>

#### <a name="add-example-files-for-your-model"></a><span data-ttu-id="63cd8-140">Adicionar arquivos de exemplo para seu modelo</span><span class="sxs-lookup"><span data-stu-id="63cd8-140">Add example files for your model</span></span>

<span data-ttu-id="63cd8-141">Você precisa adicionar pelo menos cinco arquivos de exemplo que são documentos de contrato e um arquivo de exemplo que não seja um documento de contrato (por exemplo, uma instrução de trabalho).</span><span class="sxs-lookup"><span data-stu-id="63cd8-141">You need to add at least five example files that are contract documents, and one example file that's not a contract document (for example, a statement of work).</span></span> 

1. <span data-ttu-id="63cd8-142">Na página **Modelos > Contrato,** em **Ações principais** Adicionar arquivos  >  **de exemplo,** selecione Adicionar **arquivos**.</span><span class="sxs-lookup"><span data-stu-id="63cd8-142">On the **Models > Contract** page, under **Key actions** > **Add example files**, select **Add files**.</span></span>

   ![Captura de tela mostrando a página Contratos com a opção Adicionar arquivos de exemplo realçada.](../media/content-understanding/key-actions-add-example-files.png)

2. <span data-ttu-id="63cd8-144">Na página **Selecionar arquivos de exemplo para seu modelo,** abra a pasta Contrato, selecione arquivos que deseja usar e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="63cd8-144">On the **Select example files for your model** page, open the Contract folder, select files you want to use, and then select **Add**.</span></span> <span data-ttu-id="63cd8-145">Se você não tiver arquivos de exemplo, selecione **Upload** adicioná-los.</span><span class="sxs-lookup"><span data-stu-id="63cd8-145">If you don't have example files there, select **Upload** to add them.</span></span>

#### <a name="label-the-files-as-positive-or-negative-examples"></a><span data-ttu-id="63cd8-146">Rotular os arquivos como exemplos positivos ou negativos</span><span class="sxs-lookup"><span data-stu-id="63cd8-146">Label the files as positive or negative examples</span></span>

1. <span data-ttu-id="63cd8-147">Na página **Modelos > Contrato,** em **Ações** principais Classificar arquivos e executar  >  treinamento, selecione **Classificador de trem**.</span><span class="sxs-lookup"><span data-stu-id="63cd8-147">On the **Models > Contract** page, under **Key actions** > **Classify files and run training**, select **Train classifier**.</span></span>

   ![Captura de tela mostrando a página Contratos com Classificar arquivos e executar a opção de treinamento realçada.](../media/content-understanding/key-actions-classify-files.png)

2. <span data-ttu-id="63cd8-149">Na página Modelos > Classificador de Contrato **>,** no visualizador na parte superior do primeiro arquivo de exemplo, você verá texto perguntando se o arquivo é um exemplo do modelo de contrato que você criou.</span><span class="sxs-lookup"><span data-stu-id="63cd8-149">On the **Models > Contract > Contract classifier** page, in the viewer on the top of the first example file, you'll see text asking if the file is an example of the Contract model you created.</span></span> <span data-ttu-id="63cd8-150">Se for um exemplo positivo, selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="63cd8-150">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="63cd8-151">Se for um exemplo negativo, selecione **Não**.</span><span class="sxs-lookup"><span data-stu-id="63cd8-151">If it is a negative example, select **No**.</span></span>

3. <span data-ttu-id="63cd8-152">Na lista **Exemplos rotulados** à esquerda, selecione outros arquivos que você deseja usar como exemplos e rotule-os.</span><span class="sxs-lookup"><span data-stu-id="63cd8-152">From the **Labeled examples** list on the left, select other files that you want to use as examples, and label them.</span></span> 

    ![Página inicial do classificador](../media/content-understanding/models-contract-classifier.png) 

#### <a name="add-at-least-one-explanation-to-train-the-classifier&quot;></a><span data-ttu-id=&quot;63cd8-154&quot;>Adicionar pelo menos uma explicação para treinar o classificador</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;63cd8-154&quot;>Add at least one explanation to train the classifier</span></span> 

1. <span data-ttu-id=&quot;63cd8-155&quot;>Na página **Modelos > contrato > classificador de** contrato, selecione a **guia** Trem.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;63cd8-155&quot;>On the **Models > Contract > Contract classifier** page, select the **Train** tab.</span></span>

2. <span data-ttu-id=&quot;63cd8-156&quot;>Na seção **Arquivos treinados,** você verá uma lista dos arquivos de exemplo que você rotulou anteriormente.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;63cd8-156&quot;>In the **Trained files** section, you'll see a list of the example files that you previously labeled.</span></span> <span data-ttu-id=&quot;63cd8-157&quot;>Selecione um dos arquivos positivos da lista para exibi-lo no visualizador.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;63cd8-157&quot;>Select one of the positive files from the list to display it in the viewer.</span></span>

3. <span data-ttu-id=&quot;63cd8-158&quot;>Na seção **Explicações,** selecione **Novo** e, em **seguida, Em Branco**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;63cd8-158&quot;>In the **Explanations** section, select **New** and then **Blank**.</span></span>

4. <span data-ttu-id=&quot;63cd8-159&quot;>Na página **Criar uma explicação**:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;63cd8-159&quot;>On the **Create an explanation** page:</span></span>

    <span data-ttu-id=&quot;63cd8-160&quot;>a.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;63cd8-160&quot;>a.</span></span> <span data-ttu-id=&quot;63cd8-161&quot;>No campo **Nome,** digite o nome da explicação (como &quot;Contrato").</span><span class="sxs-lookup"><span data-stu-id="63cd8-161">In the **Name** field, type the name of the explanation (such as "Agreement").</span></span>

    <span data-ttu-id="63cd8-162">b.</span><span class="sxs-lookup"><span data-stu-id="63cd8-162">b.</span></span> <span data-ttu-id="63cd8-163">No campo **Tipo de explicação,** selecione **Lista de** frases , porque você adiciona uma cadeia de caracteres de texto.</span><span class="sxs-lookup"><span data-stu-id="63cd8-163">In the **Explanation type** field, select **Phrase list**, because you add a text string.</span></span>

    <span data-ttu-id="63cd8-164">c.</span><span class="sxs-lookup"><span data-stu-id="63cd8-164">c.</span></span> <span data-ttu-id="63cd8-165">Na caixa **de listagem Frase,** digite a cadeia de caracteres (como "AGREEMENT").</span><span class="sxs-lookup"><span data-stu-id="63cd8-165">In the **Phrase list** box, type the string (such as "AGREEMENT").</span></span> <span data-ttu-id="63cd8-166">Você pode selecionar **Case sensitive** se a cadeia de caracteres precisar ser sensível a minúsculas.</span><span class="sxs-lookup"><span data-stu-id="63cd8-166">You can select **Case sensitive** if the string needs to be case-sensitive.</span></span>

    <span data-ttu-id="63cd8-167">d.</span><span class="sxs-lookup"><span data-stu-id="63cd8-167">d.</span></span> <span data-ttu-id="63cd8-168">Selecione **Salvar e treinar**.</span><span class="sxs-lookup"><span data-stu-id="63cd8-168">Select **Save and train**.</span></span>

    ![Captura de tela do painel Criar uma explicação.](../media/content-understanding/contract-classifier-create-explanation.png) 

#### <a name="test-your-model"></a><span data-ttu-id="63cd8-170">Testar seu modelo</span><span class="sxs-lookup"><span data-stu-id="63cd8-170">Test your model</span></span>

<span data-ttu-id="63cd8-171">Você pode testar seu modelo de contrato em arquivos de exemplo que ele não viu antes.</span><span class="sxs-lookup"><span data-stu-id="63cd8-171">You can test your Contract model on example files it hasn’t seen before.</span></span> <span data-ttu-id="63cd8-172">Isso é opcional, mas pode ser uma prática útil.</span><span class="sxs-lookup"><span data-stu-id="63cd8-172">This is optional, but it can be a useful best practice.</span></span>

1. <span data-ttu-id="63cd8-173">Na página **Modelos > contrato > classificador de** contrato, selecione a **guia** Testar. Isso executa o modelo em seus arquivos de exemplo não rotulados.</span><span class="sxs-lookup"><span data-stu-id="63cd8-173">On the **Models > Contract > Contract classifier** page, select the **Test** tab. This runs the model on your unlabeled example files.</span></span>

2. <span data-ttu-id="63cd8-174">Na lista **Arquivos de Teste,** seus arquivos de exemplo são exibidos e mostram se o modelo previu que eles sejam positivos ou negativos.</span><span class="sxs-lookup"><span data-stu-id="63cd8-174">In the **Test Files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="63cd8-175">Use essas informações para ajudá-lo a determinar a eficácia do seu classificador na identificação de seus documentos.</span><span class="sxs-lookup"><span data-stu-id="63cd8-175">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Captura de tela dos arquivos não rotulados na lista Arquivos de Texto](../media/content-understanding/test-on-files.png) 

3. <span data-ttu-id="63cd8-177">Quando terminar, selecione **Exit Training**.</span><span class="sxs-lookup"><span data-stu-id="63cd8-177">When done, select **Exit Training**.</span></span>

### <a name="create-and-train-an-extractor"></a><span data-ttu-id="63cd8-178">Criar e treinar um extrator</span><span class="sxs-lookup"><span data-stu-id="63cd8-178">Create and train an extractor</span></span>

1. <span data-ttu-id="63cd8-179">Na página **Modelos > Contrato,** em **Principais** ações Criar e  >  **treinar** extratores, selecione **Criar extrator**.</span><span class="sxs-lookup"><span data-stu-id="63cd8-179">On the **Models > Contract** page, under **Key actions** > **Create and train extractors**, select **Create extractor**.</span></span>

   ![Captura de tela mostrando a página Contratos com a opção Criar e treinar extratores realçadas.](../media/content-understanding/key-actions-create-extractors.png)

2. <span data-ttu-id="63cd8-181">No painel **Novo extrator de entidade,** no campo **Novo** nome, digite o nome do seu extrator.</span><span class="sxs-lookup"><span data-stu-id="63cd8-181">On the **New entity extractor** panel, in the **New name** field, type the name of your extractor.</span></span> <span data-ttu-id="63cd8-182">Por exemplo, *nomeia-o Cliente* se você quiser extrair o nome do cliente de cada contrato.</span><span class="sxs-lookup"><span data-stu-id="63cd8-182">For example, name it *Client* if you want to extract the name of the client from each contract.</span></span>

3. <span data-ttu-id="63cd8-183">Quando terminar, selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="63cd8-183">When you're done, select **Create**.</span></span>

#### <a name="label-the-entity-you-want-to-extract"></a><span data-ttu-id="63cd8-184">Rotular a entidade que você deseja extrair</span><span class="sxs-lookup"><span data-stu-id="63cd8-184">Label the entity you want to extract</span></span>

<span data-ttu-id="63cd8-185">Quando você cria o extrator, a página do extrator é aberta.</span><span class="sxs-lookup"><span data-stu-id="63cd8-185">When you create the extractor, the extractor page opens.</span></span> <span data-ttu-id="63cd8-186">Aqui você vê uma lista com seus arquivos de amostra, e o primeiro arquivo da lista é exibido no visualizador.</span><span class="sxs-lookup"><span data-stu-id="63cd8-186">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

![Captura de tela da página Exemplos rotulados do extrator de cliente.](../media/content-understanding/client-extractor-labeled-examples.png) 

<span data-ttu-id="63cd8-188">Para rotular a entidade:</span><span class="sxs-lookup"><span data-stu-id="63cd8-188">To label the entity:</span></span>

1. <span data-ttu-id="63cd8-189">No visualizador, selecione os dados que deseja extrair dos arquivos.</span><span class="sxs-lookup"><span data-stu-id="63cd8-189">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="63cd8-190">Por exemplo, se você quiser extrair o *Cliente*, realça o valor do cliente no primeiro arquivo (neste exemplo, *Best For You Organics*) e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="63cd8-190">For example, if you want to extract the *Client*, you highlight the client value in the first file (in this example, *Best For You Organics*), and then select **Save**.</span></span> <span data-ttu-id="63cd8-191">Você verá o valor exibido do arquivo na **lista Exemplos** rotulados, na **coluna Rótulo.**</span><span class="sxs-lookup"><span data-stu-id="63cd8-191">You'll see the value display from the file in the **Labeled examples** list, under the **Label** column.</span></span>

2. <span data-ttu-id="63cd8-192">Selecione **Próximo arquivo** para salvar automaticamente e abrir o próximo arquivo na lista no visualizador.</span><span class="sxs-lookup"><span data-stu-id="63cd8-192">Select **Next file** to autosave and open the next file in the list in the viewer.</span></span> <span data-ttu-id="63cd8-193">Ou selecione **Salvar** e selecione outro arquivo na **lista Exemplos rotulados.**</span><span class="sxs-lookup"><span data-stu-id="63cd8-193">Or select **Save**, and then select another file from the **Labeled examples** list.</span></span>

3. <span data-ttu-id="63cd8-194">No visualizador, repita as etapas 1 e 2 e repita até salvar o rótulo em todos os arquivos.</span><span class="sxs-lookup"><span data-stu-id="63cd8-194">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all the files.</span></span>

<span data-ttu-id="63cd8-195">Depois de rotular os arquivos, um banner de notificação será exibido informando que você deve passar para o treinamento.</span><span class="sxs-lookup"><span data-stu-id="63cd8-195">After you've labeled the files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="63cd8-196">Você pode optar por rotular mais documentos ou avançar para o treinamento.</span><span class="sxs-lookup"><span data-stu-id="63cd8-196">You can choose to label more documents or advance to training.</span></span>

#### <a name="add-an-explanation"></a><span data-ttu-id="63cd8-197">Adicione uma explicação</span><span class="sxs-lookup"><span data-stu-id="63cd8-197">Add an explanation</span></span>

<span data-ttu-id="63cd8-198">Você pode criar uma explicação que fornece uma dica sobre o formato da entidade em si e as variações que ele pode ter nos arquivos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="63cd8-198">You can create an explanation that provides a hint about the entity format itself and variations it might have in the example files.</span></span> <span data-ttu-id="63cd8-199">Por exemplo, um valor de data pode estar em vários formatos diferentes, como:</span><span class="sxs-lookup"><span data-stu-id="63cd8-199">For example, a date value can be in many different formats, such as:</span></span>

- <span data-ttu-id="63cd8-200">14/10/2019</span><span class="sxs-lookup"><span data-stu-id="63cd8-200">10/14/2019</span></span>
- <span data-ttu-id="63cd8-201">14 de outubro de 2019</span><span class="sxs-lookup"><span data-stu-id="63cd8-201">October 14, 2019</span></span>
- <span data-ttu-id="63cd8-202">Segunda-feira, 14 de outubro de 2019</span><span class="sxs-lookup"><span data-stu-id="63cd8-202">Monday, October 14, 2019</span></span>

<span data-ttu-id="63cd8-203">Para ajudar a identificar *a Data de* Início do Contrato, você pode criar uma explicação de padrão.</span><span class="sxs-lookup"><span data-stu-id="63cd8-203">To help identify the *Contract Start Date*, you can create a pattern explanation.</span></span>

1. <span data-ttu-id="63cd8-204">Na seção **Explicações,** selecione **Novo** e, em **seguida, Em Branco**.</span><span class="sxs-lookup"><span data-stu-id="63cd8-204">In the **Explanations** section, select **New** and then **Blank**.</span></span>

2. <span data-ttu-id="63cd8-205">Na página **Criar uma explicação**:</span><span class="sxs-lookup"><span data-stu-id="63cd8-205">On the **Create an explanation** page:</span></span>

    <span data-ttu-id="63cd8-206">a.</span><span class="sxs-lookup"><span data-stu-id="63cd8-206">a.</span></span> <span data-ttu-id="63cd8-207">No campo **Nome,** digite o nome da explicação (como *Data*).</span><span class="sxs-lookup"><span data-stu-id="63cd8-207">In the **Name** field, type the name of the explanation (such as *Date*).</span></span>

    <span data-ttu-id="63cd8-208">b.</span><span class="sxs-lookup"><span data-stu-id="63cd8-208">b.</span></span> <span data-ttu-id="63cd8-209">No campo **Tipo de explicação,** selecione **Lista de padrões**.</span><span class="sxs-lookup"><span data-stu-id="63cd8-209">In the **Explanation type** field, select **Pattern list**.</span></span>

    <span data-ttu-id="63cd8-210">c.</span><span class="sxs-lookup"><span data-stu-id="63cd8-210">c.</span></span> <span data-ttu-id="63cd8-211">No campo **Valor,** forneça a variação de data conforme aparecem nos arquivos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="63cd8-211">In the **Value** field, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="63cd8-212">Por exemplo, se você tem formatos de data que aparecem como 0/00/0000, digite quaisquer variações que aparecem em seus documentos, como por exemplo:</span><span class="sxs-lookup"><span data-stu-id="63cd8-212">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>

    - <span data-ttu-id="63cd8-213">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="63cd8-213">0/0/0000</span></span>
    - <span data-ttu-id="63cd8-214">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="63cd8-214">0/00/0000</span></span>
    - <span data-ttu-id="63cd8-215">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="63cd8-215">00/0/0000</span></span>
    - <span data-ttu-id="63cd8-216">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="63cd8-216">00/00/0000</span></span>

4. <span data-ttu-id="63cd8-217">Selecione **Salvar e treinar**.</span><span class="sxs-lookup"><span data-stu-id="63cd8-217">Select **Save and train**.</span></span>

#### <a name="test-your-model-again"></a><span data-ttu-id="63cd8-218">Testar seu modelo novamente</span><span class="sxs-lookup"><span data-stu-id="63cd8-218">Test your model again</span></span>

<span data-ttu-id="63cd8-219">Você pode testar seu modelo de contrato em arquivos de exemplo que ele não viu antes.</span><span class="sxs-lookup"><span data-stu-id="63cd8-219">You can test your Contract model on example files it hasn’t seen before.</span></span> <span data-ttu-id="63cd8-220">Isso é opcional, mas pode ser uma prática útil.</span><span class="sxs-lookup"><span data-stu-id="63cd8-220">This is optional, but it can be a useful best practice.</span></span>

1. <span data-ttu-id="63cd8-221">Na página **Modelos > contrato > classificador de** contrato, selecione a **guia** Testar. Isso executa o modelo em seus arquivos de exemplo não rotulados.</span><span class="sxs-lookup"><span data-stu-id="63cd8-221">On the **Models > Contract > Contract classifier** page, select the **Test** tab. This runs the model on your unlabeled example files.</span></span>

2. <span data-ttu-id="63cd8-222">Na lista **Arquivos de teste,** seus arquivos de exemplo são exibidos e mostram se o modelo é capaz de extrair as informações necessárias.</span><span class="sxs-lookup"><span data-stu-id="63cd8-222">In the **Test files** list, your example files display and shows if the model is able to extract the information you need.</span></span> <span data-ttu-id="63cd8-223">Use essas informações para ajudá-lo a determinar a eficácia do seu classificador na identificação de seus documentos.</span><span class="sxs-lookup"><span data-stu-id="63cd8-223">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

3. <span data-ttu-id="63cd8-224">Quando terminar, selecione **Exit Training**.</span><span class="sxs-lookup"><span data-stu-id="63cd8-224">When done, select **Exit Training**.</span></span>

### <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="63cd8-225">Aplicar seu modelo a uma biblioteca de documentos</span><span class="sxs-lookup"><span data-stu-id="63cd8-225">Apply your model to a document library</span></span>

<span data-ttu-id="63cd8-226">Para aplicar seu modelo a uma biblioteca SharePoint de documentos:</span><span class="sxs-lookup"><span data-stu-id="63cd8-226">To apply your model to a SharePoint document library:</span></span>

1. <span data-ttu-id="63cd8-227">Na página **Modelos > Contrato,** em **Principais** ações Aplicar modelo a  >  **bibliotecas,** selecione Aplicar **modelo**.</span><span class="sxs-lookup"><span data-stu-id="63cd8-227">On the **Models > Contract** page, under **Key actions** > **Apply model to libraries**, select **Apply model**.</span></span>

   ![Captura de tela mostrando a página Contratos com a opção Aplicar modelo a bibliotecas realçada.](../media/content-understanding/key-actions-apply-model.png)

2. <span data-ttu-id="63cd8-229">No painel **Adicionar Contrato,** selecione o site SharePoint que contém a biblioteca de documentos à qual você deseja aplicar o modelo.</span><span class="sxs-lookup"><span data-stu-id="63cd8-229">On the **Add Contract** panel, select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="63cd8-230">Se o site não for mostrado na lista, use a caixa de pesquisa para localizá-lo.</span><span class="sxs-lookup"><span data-stu-id="63cd8-230">If the site does not show in the list, use the search box to find it.</span></span> <span data-ttu-id="63cd8-231">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="63cd8-231">Select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="63cd8-232">Você deve ter permissões de *Gerenciar Lista* ou direitos de *Editar* na biblioteca de documentos para a qual você está aplicando o modelo.</span><span class="sxs-lookup"><span data-stu-id="63cd8-232">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span>

3. <span data-ttu-id="63cd8-233">Depois de selecionar o site, selecione a biblioteca de documentos à qual deseja aplicar o modelo.</span><span class="sxs-lookup"><span data-stu-id="63cd8-233">After you select the site, select the document library to which you want to apply the model.</span></span>

4. <span data-ttu-id="63cd8-234">Como o modelo está associado a um tipo de conteúdo, ao aplicá-lo à biblioteca, ele adicionará o tipo de conteúdo e sua exibição com os rótulos que você extraiu mostrando como colunas.</span><span class="sxs-lookup"><span data-stu-id="63cd8-234">Because the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="63cd8-235">Esse modo de exibição é o modo de exibição padrão da biblioteca por padrão, mas você  pode optar por não ser o modo de exibição padrão selecionando Configurações avançadas e **des** marcando a caixa de seleção Definir esse novo modo de exibição como padrão.</span><span class="sxs-lookup"><span data-stu-id="63cd8-235">This view is the library's default view by default, but you can optionally choose to have it not be the default view by selecting **Advanced settings** and clearing the **Set this new view as default** check box.</span></span>

5. <span data-ttu-id="63cd8-236">Selecione **Adicionar** para aplicar o modelo à biblioteca.</span><span class="sxs-lookup"><span data-stu-id="63cd8-236">Select **Add** to apply the model to the library.</span></span>

6. <span data-ttu-id="63cd8-237">Na página **Modelos > Contrato,** na seção **Bibliotecas** com este modelo, você verá a URL do site SharePoint listada.</span><span class="sxs-lookup"><span data-stu-id="63cd8-237">On the **Models > Contract** page, in the **Libraries with this model** section, you'll see the URL to the SharePoint site listed.</span></span>

    ![Captura de tela da home page Contrato mostrando a seção Bibliotecas com este modelo.](../media/content-understanding/contract-libraries-with-this-model.png)

<span data-ttu-id="63cd8-239">Depois de aplicar o modelo à biblioteca de documentos, você pode começar a carregar documentos no site e ver os resultados.</span><span class="sxs-lookup"><span data-stu-id="63cd8-239">After you apply the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

## <a name="next-step"></a><span data-ttu-id="63cd8-240">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="63cd8-240">Next step</span></span>

[<span data-ttu-id="63cd8-241">Etapa 2. Use Microsoft Teams para criar seu canal de gerenciamento de contratos</span><span class="sxs-lookup"><span data-stu-id="63cd8-241">Step 2. Use Microsoft Teams to create your contract management channel</span></span>](solution-manage-contracts-step2.md)