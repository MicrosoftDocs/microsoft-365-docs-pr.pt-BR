---
title: Crie um extrator
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Aprenda como criar um extrator no Microsoft SharePoint Syntex.
ms.openlocfilehash: e95df00c2601bccc5041f96c745048adc8dfc91f
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222786"
---
# <a name="create-an-extractor-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="27849-103">Criar um extrator no Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="27849-103">Create an extractor in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="27849-104">Antes ou depois de criar um modelo de classificador para automatizar a identificação e classificação de tipos de documentos específicos, você pode optar por adicionar extratores ao seu modelo para extrair informações específicas desses documentos.</span><span class="sxs-lookup"><span data-stu-id="27849-104">Before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="27849-105">Por exemplo, você pode desejar que seu modelo não apenas identifique todos os documentos de *Renovação do Contrato* adicionados à sua biblioteca de documentos, mas também exiba a *Data de Início do Serviço* para cada documento como um valor de coluna em a biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="27849-105">For example, you may want your model not only to identify all *Contract Renewal* documents added to your document library, but also to display the *Service Start date* for each document as a column value in the document library.</span></span>

<span data-ttu-id="27849-106">É necessário criar um extrator para cada entidade no documento que se deseja extrair.</span><span class="sxs-lookup"><span data-stu-id="27849-106">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="27849-107">No nosso exemplo, desejamos extrair a  **Data de Início do Serviço**  para cada documento de  **Renovação de Contrato**  que é identificado pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="27849-107">In our example, we want to extract the **Service Start Date** for each **Contract Renewal** document that is identified by the model.</span></span> <span data-ttu-id="27849-108">Queremos ter uma visão na biblioteca de documentos de todos os documentos de  **Renovação de Contrato** , com uma coluna que mostra o valor da data de **Início do Serviço** de cada documento.</span><span class="sxs-lookup"><span data-stu-id="27849-108">We want to be able to see a view in the document library of all  **Contract Renewal** documents, with a column that shows the **Service Start** date value of each document.</span></span> 

> [!NOTE]
> <span data-ttu-id="27849-109">Para criar um extrator, você utiliza os mesmos arquivos que carregou anteriormente para treinar o classificador.</span><span class="sxs-lookup"><span data-stu-id="27849-109">In order to create an extractor, you use the same files you previously uploaded to train the classifier.</span></span> 

## <a name="name-your-extractor"></a><span data-ttu-id="27849-110">Nomeie seu extrator</span><span class="sxs-lookup"><span data-stu-id="27849-110">Name your extractor</span></span>

1. <span data-ttu-id="27849-111">Na página inicial do modelo, no bloco **Criar e treinar extratores**, clique em **Extrator de treinamento**.</span><span class="sxs-lookup"><span data-stu-id="27849-111">From the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="27849-112">Na tela **Novo extrator de entidade**, digite o nome do seu extrator no campo **Novo nome do extrator**.</span><span class="sxs-lookup"><span data-stu-id="27849-112">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="27849-113">Por exemplo, nomeie a **Data de Início do Serviço** se você quiser extrair a data de início do serviço de cada documento de Renovação do Contrato.</span><span class="sxs-lookup"><span data-stu-id="27849-113">For example, name it **Service Start Date** if you want to extract the service start date from each Contract Renewal document.</span></span> <span data-ttu-id="27849-114">Também é possível optar por reutilizar uma coluna anteriormente criada (por exemplo, uma coluna de metadados gerenciados).</span><span class="sxs-lookup"><span data-stu-id="27849-114">You can also choose to reuse a previously created column (for example, a managed metadata column).</span></span>
> [!NOTE]
> <span data-ttu-id="27849-115">Se você criar um novo extrator, selecione **Novo tipo de coluna** e escolha **Linha única de texto**, com o limite máximo de caracteres de 255.</span><span class="sxs-lookup"><span data-stu-id="27849-115">If you create a new extractor, then select **New column type** and choose **Single line of text**, the maximum character limit is 255.</span></span> <span data-ttu-id="27849-116">Qualquer caractere que você digitar excedendo o limite sairá truncado.</span><span class="sxs-lookup"><span data-stu-id="27849-116">Any characters that you type exceeding the limit get truncated.</span></span> 
3. <span data-ttu-id="27849-117">Quando terminar, clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="27849-117">When you're done, click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="27849-118">Adicione um rótulo</span><span class="sxs-lookup"><span data-stu-id="27849-118">Add a label</span></span>

<span data-ttu-id="27849-119">A próxima etapa é rotular a entidade que você deseja extrair nos seus exemplos de arquivos de treinamento.</span><span class="sxs-lookup"><span data-stu-id="27849-119">The next step is to label the entity you want to extract in your example training files.</span></span>

<span data-ttu-id="27849-120">A criação do extrator abre a página do extrator.</span><span class="sxs-lookup"><span data-stu-id="27849-120">Creating the extractor opens the extractor page.</span></span> <span data-ttu-id="27849-121">Aqui você vê uma lista com seus arquivos de amostra, e o primeiro arquivo da lista é exibido no visualizador.</span><span class="sxs-lookup"><span data-stu-id="27849-121">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="27849-122">No visualizador, selecione os dados que deseja extrair dos arquivos.</span><span class="sxs-lookup"><span data-stu-id="27849-122">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="27849-123">Por exemplo, se quiser extrair a *Data de Início do Serviço*, você destaca o valor da data no primeiro arquivo (*Segunda-feira, 14 de outubro de 2019*).</span><span class="sxs-lookup"><span data-stu-id="27849-123">For example, if you want to extract the *Start Service Date*, you highlight the date value in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="27849-124">e depois clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="27849-124">and then click **Save**.</span></span>  <span data-ttu-id="27849-125">Você deve ver a exibição do valor do arquivo na lista de exemplos Rotulados, na coluna **Rótulo**.</span><span class="sxs-lookup"><span data-stu-id="27849-125">You should see the value display from the file in the Labeled examples list, under the **Label** column.</span></span>
2. <span data-ttu-id="27849-126">Selecione o **Próximo arquivo** para salvar automaticamente e abrir o arquivo seguinte da lista no visualizador.</span><span class="sxs-lookup"><span data-stu-id="27849-126">Select **Next file** to auto save and open the next file in the list in the viewer.</span></span> <span data-ttu-id="27849-127">Ou selecione **Salvar** e depois selecione outro arquivo da lista **Exemplos rotulados**.</span><span class="sxs-lookup"><span data-stu-id="27849-127">Or select **Save** and then select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="27849-128">No visualizador, repita as etapas 1 e 2 e, em seguida, repita até salvar o rótulo em todos os cinco arquivos.</span><span class="sxs-lookup"><span data-stu-id="27849-128">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all five files.</span></span>

    ![Configurações avançadas](../media/content-understanding/select-service-start-date.png) 

 
<span data-ttu-id="27849-130">Uma vez rotulados os cinco arquivos, um banner de notificação informa que você deve passar para o treinamento.</span><span class="sxs-lookup"><span data-stu-id="27849-130">Once you labeled five files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="27849-131">É possível escolher entre etiquetar mais documentos ou avançar para o treinamento.</span><span class="sxs-lookup"><span data-stu-id="27849-131">You can choose to more label more documents or advance to training.</span></span> 

### <a name="use-find-to-search-your-file"></a><span data-ttu-id="27849-132">Usar a ferramenta Procurar para pesquisar seu arquivo</span><span class="sxs-lookup"><span data-stu-id="27849-132">Use Find to search your file</span></span>
<span data-ttu-id="27849-133">Você pode usar o recurso <b>Encontrar</b> para procurar uma entidade em seu documento que você deseja rotular.</span><span class="sxs-lookup"><span data-stu-id="27849-133">You can use the <b>Find</b> feature to search for an entity in your document that you want to label.</span></span>

   ![Localizar nos arquivos](../media/content-understanding/find-feature.png) 

<span data-ttu-id="27849-135">O recurso Encontrar é útil se você estiver pesquisando um documento grande ou se houver várias instâncias da entidade no documento.</span><span class="sxs-lookup"><span data-stu-id="27849-135">The Find feature is useful if you are searching a large document or if there are multiple instances of the entity in the document.</span></span> <span data-ttu-id="27849-136">Se você encontrar várias instâncias, poderá selecionar a de que precisa nos resultados da pesquisa para ir até esse local no visualizador para rotulá-la.</span><span class="sxs-lookup"><span data-stu-id="27849-136">If you find multiple instances, you can select the one you need in the search results to go to that location in the viewer to label it.</span></span>


## <a name="add-an-explanation"></a><span data-ttu-id="27849-137">Adicione uma explicação</span><span class="sxs-lookup"><span data-stu-id="27849-137">Add an explanation</span></span>

<span data-ttu-id="27849-138">Para nosso exemplo, vamos criar uma explicação que fornece uma dica sobre o formato da entidade em si e as variações que ela pode ter nos modelos de documentos.</span><span class="sxs-lookup"><span data-stu-id="27849-138">For our example, we are going to create an explanation that provides a hint about the entity format itself and variations it may have in the sample documents.</span></span> <span data-ttu-id="27849-139">Por exemplo, um valor de data pode estar em vários formatos diferentes, como por exemplo:</span><span class="sxs-lookup"><span data-stu-id="27849-139">For example, a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="27849-140">14/10/2019</span><span class="sxs-lookup"><span data-stu-id="27849-140">10/14/2019</span></span>
- <span data-ttu-id="27849-141">14 de outubro de 2019</span><span class="sxs-lookup"><span data-stu-id="27849-141">October 14, 2019</span></span>
- <span data-ttu-id="27849-142">Segunda-feira, 14 de outubro de 2019</span><span class="sxs-lookup"><span data-stu-id="27849-142">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="27849-143">Para ajudar a identificar a *Data de Início do Serviço*, você pode criar uma explicação padrão.</span><span class="sxs-lookup"><span data-stu-id="27849-143">To help identify the *Service Start Date* you can create a pattern explanation.</span></span>

1. <span data-ttu-id="27849-144">Na seção Explicação, selecione **Novo** e digite um nome (por exemplo, *Data*).</span><span class="sxs-lookup"><span data-stu-id="27849-144">In the Explanation section, select **New** and type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="27849-145">Para Tipo, selecione **Lista de padrões**.</span><span class="sxs-lookup"><span data-stu-id="27849-145">For Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="27849-146">Para Valor, forneça a variação de data conforme aparecem nos arquivos de amostra.</span><span class="sxs-lookup"><span data-stu-id="27849-146">For Value, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="27849-147">Por exemplo, se você tem formatos de data que aparecem como 0/00/0000, digite quaisquer variações que aparecem em seus documentos, como por exemplo:</span><span class="sxs-lookup"><span data-stu-id="27849-147">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>
    - <span data-ttu-id="27849-148">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="27849-148">0/0/0000</span></span>
    - <span data-ttu-id="27849-149">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="27849-149">0/00/0000</span></span>
    - <span data-ttu-id="27849-150">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="27849-150">00/0/0000</span></span>
    - <span data-ttu-id="27849-151">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="27849-151">00/00/0000</span></span>
4. <span data-ttu-id="27849-152">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="27849-152">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="27849-153">Para obter mais informações sobre os tipos de explicação, consulte [Tipos de explicação](./explanation-types-overview.md).</span><span class="sxs-lookup"><span data-stu-id="27849-153">For more learn more about explanation types, see [Explanation types](./explanation-types-overview.md).</span></span>  


### <a name="use-the-explanation-library"></a><span data-ttu-id="27849-154">Utilize a biblioteca de explicações</span><span class="sxs-lookup"><span data-stu-id="27849-154">Use the Explanation library</span></span>

<span data-ttu-id="27849-155">Para criar explicações para itens como datas, é mais fácil [utilizar a biblioteca de explicações ](./explanation-types-overview.md) do que inserir manualmente todas as variações.</span><span class="sxs-lookup"><span data-stu-id="27849-155">For creating explanations for items such as dates, it is easier to [use the explanation library](./explanation-types-overview.md) than to manually enter all variations.</span></span> <span data-ttu-id="27849-156">A biblioteca de explicação é um conjunto de frases predefinidas e explicações de padrões.</span><span class="sxs-lookup"><span data-stu-id="27849-156">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="27849-157">A biblioteca busca fornecer todos os formatos de frases comuns ou listas de padrões, como datas, números de telefone, CEPs e muitos outros.</span><span class="sxs-lookup"><span data-stu-id="27849-157">The library tries to provides all formats for common phrase or pattern lists, such as dates, phone numbers, zip codes, and many others.</span></span> 

<span data-ttu-id="27849-158">Para o exemplo de *Data de Início do Serviço*, é mais eficiente usar a explicação predefinida para *Data* na biblioteca de explicações:</span><span class="sxs-lookup"><span data-stu-id="27849-158">For the *Service Start Date* sample, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="27849-159">Na seção **Explicação**, selecione **Novo**, e então selecione **Na biblioteca de explicações**.</span><span class="sxs-lookup"><span data-stu-id="27849-159">In the **Explanation section**, select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="27849-160">Na biblioteca de explicações, selecione **Data**.</span><span class="sxs-lookup"><span data-stu-id="27849-160">From the explanation library, select **Date**.</span></span> <span data-ttu-id="27849-161">Você pode ver todas as variações de data que são reconhecidas.</span><span class="sxs-lookup"><span data-stu-id="27849-161">You can view all variations of date that are recognized.</span></span>
3. <span data-ttu-id="27849-162">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="27849-162">Select **Add**.</span></span></br>

    ![Biblioteca de explicações](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="27849-164">Na página **Criar uma explicação**, a informação *Data* da biblioteca de explicações preenche automaticamente os campos.</span><span class="sxs-lookup"><span data-stu-id="27849-164">On the **Create an explanation** page, the *Date* information from the explanation library auto fills the fields.</span></span> <span data-ttu-id="27849-165">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="27849-165">Select **Save**.</span></span></br>

    ![Data](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a><span data-ttu-id="27849-167">Treine o modelo</span><span class="sxs-lookup"><span data-stu-id="27849-167">Train the model</span></span> 

<span data-ttu-id="27849-168">Salvando sua explicação, inicie o treinamento.</span><span class="sxs-lookup"><span data-stu-id="27849-168">Saving your explanation start the training.</span></span> <span data-ttu-id="27849-169">Se o seu modelo tiver informações suficientes para extrair os dados dos seus arquivos de amostra rotulados, você verá cada arquivo rotulado com **Compatível**.</span><span class="sxs-lookup"><span data-stu-id="27849-169">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![Compatível](../media/content-understanding/match2.png) 

<span data-ttu-id="27849-171">Se a explicação não contém informações suficientes para localizar os dados que você deseja extrair, cada arquivo será rotulado com **Incompatível**.</span><span class="sxs-lookup"><span data-stu-id="27849-171">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="27849-172">Você pode clicar nos arquivos **Incompatíveis** para ver mais informações sobre o motivo da incompatibilidade.</span><span class="sxs-lookup"><span data-stu-id="27849-172">You can click on the **Mismatched** files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="27849-173">Adicione outra explicação</span><span class="sxs-lookup"><span data-stu-id="27849-173">Add another explanation</span></span>

<span data-ttu-id="27849-174">Muitas vezes, a incompatibilidade é uma indicação de que a explicação que fornecemos não proporcionou informações suficientes para extrair o valor da data de início do serviço para corresponder aos nossos arquivos rotulados.</span><span class="sxs-lookup"><span data-stu-id="27849-174">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="27849-175">Você pode precisar editá-lo ou acrescentar outra explicação.</span><span class="sxs-lookup"><span data-stu-id="27849-175">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="27849-176">Para nosso exemplo, observe que o texto *data de Início do Serviço de* sempre precede o valor real.</span><span class="sxs-lookup"><span data-stu-id="27849-176">For our example, notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="27849-177">Para ajudar a identificar a Data de Início do Serviço, você precisa criar uma explicação de frase.</span><span class="sxs-lookup"><span data-stu-id="27849-177">To help identify the Service Start Date, you need to create a phrase explanation.</span></span>

1. <span data-ttu-id="27849-178">Na seção Explicação, selecione **Novo**, e então digite um nome (por exemplo, *Sequencia de Prefixo*).</span><span class="sxs-lookup"><span data-stu-id="27849-178">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="27849-179">Para o Tipo, selecione **Lista de frases**.</span><span class="sxs-lookup"><span data-stu-id="27849-179">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="27849-180">Utilize a *Data de Início do Serviço* como o valor.</span><span class="sxs-lookup"><span data-stu-id="27849-180">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="27849-181">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="27849-181">Select **Save**.</span></span>

    ![Sequencia de Prefixo](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a><span data-ttu-id="27849-183">Treine novamente o modelo</span><span class="sxs-lookup"><span data-stu-id="27849-183">Train the model again</span></span>

<span data-ttu-id="27849-184">Salvar a explicação inicia o treinamento novamente, desta vez usando as duas explicações do exemplo.</span><span class="sxs-lookup"><span data-stu-id="27849-184">Saving the explanation starts the training again, this time using both explanations in the example.</span></span> <span data-ttu-id="27849-185">Se o seu modelo tiver informações suficientes para extrair os dados dos arquivos de amostra rotulados, você verá cada arquivo rotulado com **Compatível**.</span><span class="sxs-lookup"><span data-stu-id="27849-185">If your model has enough information to extract the data from the labeled example files, you see each file labeled with **Match**.</span></span> 

<span data-ttu-id="27849-186">Se você receber novamente um **Incompatível** em seus arquivos rotulados, provavelmente precisará criar outra explicação para fornecer ao modelo mais informações para identificar o tipo de documento ou considerar fazer alterações nos existentes.</span><span class="sxs-lookup"><span data-stu-id="27849-186">If you again receive a **Mismatch** on your labeled files, you likely need to create another explanation to provide the model more information to identify the document type, or consider making changes to your existing ones.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="27849-187">Teste o seu modelo</span><span class="sxs-lookup"><span data-stu-id="27849-187">Test your model</span></span>

<span data-ttu-id="27849-188">Se você receber uma compatibilidade em seus arquivos de amostra rotulados, agora você pode testar seu modelo no restante dos arquivos de amostra não rotulados.</span><span class="sxs-lookup"><span data-stu-id="27849-188">If you receive a match on your labeled sample files, you can now test your model on the remaining unlabeled example files.</span></span> <span data-ttu-id="27849-189">Isso é opcional, mas uma etapa útil para avaliar a "adequação" ou prontidão do modelo antes de usá-lo, testando-o em arquivos que o modelo nunca viu antes.</span><span class="sxs-lookup"><span data-stu-id="27849-189">This is optional, but a useful step to evaluate the “fitness” or readiness of the model before using it, by testing it on files the model hasn’t seen before.</span></span>

1. <span data-ttu-id="27849-190">Na página inicial do modelo, clique na guia **Teste**. Isso executa o modelo em seus arquivos de amostra não rotulados.</span><span class="sxs-lookup"><span data-stu-id="27849-190">From the model home page, click the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="27849-191">Na lista **Arquivos de teste**, seus arquivos de exemplo são exibidos para mostrar se o modelo é capaz de extrair as informações de que você precisa.</span><span class="sxs-lookup"><span data-stu-id="27849-191">In the **Test files** list, your example files display to show if the model is able to extract the information you need.</span></span> <span data-ttu-id="27849-192">Utilize essas informações para ajudar a determinar a eficácia do seu classificador na identificação dos seus documentos.</span><span class="sxs-lookup"><span data-stu-id="27849-192">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Teste nos seus arquivos](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a><span data-ttu-id="27849-194">Confira também</span><span class="sxs-lookup"><span data-stu-id="27849-194">See Also</span></span>
[<span data-ttu-id="27849-195">Criar um classificador</span><span class="sxs-lookup"><span data-stu-id="27849-195">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="27849-196">Tipos de explicação</span><span class="sxs-lookup"><span data-stu-id="27849-196">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="27849-197">Aproveitar a taxonomia do repositório de termos ao criar um extrator</span><span class="sxs-lookup"><span data-stu-id="27849-197">Leverage term store taxonomy when creating an extractor</span></span>](leverage-term-store-taxonomy.md)

<span data-ttu-id="27849-198">[Visão geral sobre Compreensão de Documentos](document-understanding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="27849-198">[Document Understanding overview](document-understanding-overview.md)</span></span>

[<span data-ttu-id="27849-199">Aplicar um modelo</span><span class="sxs-lookup"><span data-stu-id="27849-199">Apply a model</span></span>](apply-a-model.md) 

[<span data-ttu-id="27849-200">Modo de Acessibilidade do SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="27849-200">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)