---
title: Criar um extrator (versão prévia)
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
description: Saiba como criar um extrator
ms.openlocfilehash: 64dede9f6613da82c65ca12c6c335a25301f5b9e
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612757"
---
# <a name="create-an-extractor-preview"></a><span data-ttu-id="e51d9-103">Criar um extrator (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="e51d9-103">Create an extractor (Preview)</span></span>
> [!Note] 
> <span data-ttu-id="e51d9-104">O conteúdo deste artigo é para a visualização privada do Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="e51d9-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="e51d9-105">[Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="e51d9-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="e51d9-106">Antes ou depois de criar um modelo de classificador para automatizar a identificação e a classificação de tipos de documento específicos, você pode optar por adicionar extratores ao modelo para extrair informações específicas desses documentos.</span><span class="sxs-lookup"><span data-stu-id="e51d9-106">Either before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="e51d9-107">Por exemplo, você pode querer que seu modelo não apenas identifique todos os documentos de *renovação de contrato* que são adicionados à sua biblioteca de documentos, mas também para exibir a data de *início do serviço* para cada documento como uma coluna na biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="e51d9-107">For example, you may want your model not only to identify all *Contract Renewal* documents that are added to your document library, but to also display the *Service Start date* for each document as a column in the document library.</span></span>

<span data-ttu-id="e51d9-108">Você precisa criar um extrator para cada entidade no documento que você deseja extrair.</span><span class="sxs-lookup"><span data-stu-id="e51d9-108">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="e51d9-109">No nosso exemplo, queremos extrair a data de *início do serviço* para cada documento de *renovação de contrato* identificado pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="e51d9-109">In our example, we want to extract the *Service Start Date* for each *Contract Renewal* document that is identified by the model.</span></span> <span data-ttu-id="e51d9-110">Queremos ver um modo de exibição na biblioteca de documentos de todos os documentos de *renovação de contrato* , com uma coluna que mostra o valor da data de início do serviço de cada documento.</span><span class="sxs-lookup"><span data-stu-id="e51d9-110">We want to be able to see a view in the document library of all *Contract Renewal* documents, with a column that shows the Service Start date value of each document.</span></span>

> [!Note]
> <span data-ttu-id="e51d9-111">Antes de criar um extrator, você precisa [adicionar os arquivos de exemplo](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) necessários para ajudar a treinar o modelo para identificar as informações que você deseja extrair.</span><span class="sxs-lookup"><span data-stu-id="e51d9-111">Before creating an extractor, you need to [add your example files](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) you will need to help train the model to identify the information you want to extract.</span></span> <span data-ttu-id="e51d9-112">Use os mesmos arquivos de exemplo usados para criar seu classificador.</span><span class="sxs-lookup"><span data-stu-id="e51d9-112">Use the same example files you used to create your classifier.</span></span>


## <a name="name-your-extractor"></a><span data-ttu-id="e51d9-113">Nomear seu extrator</span><span class="sxs-lookup"><span data-stu-id="e51d9-113">Name your extractor</span></span>

1. <span data-ttu-id="e51d9-114">Na home page do modelo, no bloco **criar e treinar extratores** , clique em **treinar extrator**.</span><span class="sxs-lookup"><span data-stu-id="e51d9-114">On the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="e51d9-115">Na tela **novo extrator de entidade** , digite o nome do extrator no campo **nome do novo extrator** .</span><span class="sxs-lookup"><span data-stu-id="e51d9-115">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="e51d9-116">Por exemplo, podemos nomear a **data de início do serviço** de ti se quisermos extrair a data de início do serviço de cada documento de renovação de contrato.</span><span class="sxs-lookup"><span data-stu-id="e51d9-116">For example, we can name it **Service Start Date** if we want to extract the service start date from each Contract Renewal document.</span></span>
3. <span data-ttu-id="e51d9-117">Clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="e51d9-117">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="e51d9-118">Adicionar um rótulo</span><span class="sxs-lookup"><span data-stu-id="e51d9-118">Add a label</span></span>

<span data-ttu-id="e51d9-119">A próxima etapa é identificar as informações que você deseja extrair nos seus arquivos de treinamento de exemplo.</span><span class="sxs-lookup"><span data-stu-id="e51d9-119">The next step is to label the information you want to extract in your example training files.</span></span>

<span data-ttu-id="e51d9-120">A criação do extrator abrirá a página do extrator em que você verá uma lista de seus arquivos de exemplo, com o primeiro arquivo na lista exibido no visualizador.</span><span class="sxs-lookup"><span data-stu-id="e51d9-120">Creating the extractor will open the extractor page in which you will see a list of your example files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="e51d9-121">No visualizador, selecione os dados que você deseja extrair dos arquivos.</span><span class="sxs-lookup"><span data-stu-id="e51d9-121">In the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="e51d9-122">Por exemplo, se quiser extrair a data de *início do serviço*, você irá destacar o valor de data dele no primeiro arquivo (*segunda-feira, 14 de outubro de 2019*).</span><span class="sxs-lookup"><span data-stu-id="e51d9-122">For example, if you want to extract the *Start Service Date*, you will highlight the date value for it in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="e51d9-123">Em seguida, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e51d9-123">Then click **Save**.</span></span>  <span data-ttu-id="e51d9-124">Você verá a exibição do valor para o arquivo na lista de exemplos rotulados abaixo da coluna **rótulo** .</span><span class="sxs-lookup"><span data-stu-id="e51d9-124">You will see the value display for the file in the Labeled examples list under the **Label** column.</span></span>
2. <span data-ttu-id="e51d9-125">Selecione **próximo arquivo** para salvamento automático e abra o próximo arquivo na lista no visualizador ou selecione **salvar** e selecione outro arquivo na lista **exemplos rotulados** .</span><span class="sxs-lookup"><span data-stu-id="e51d9-125">Select **Next file** to autosave and open the next file in the list in the viewer, or you can select **Save** and select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="e51d9-126">No visualizador, repita as etapas 1 e 2 e faça isso até salvar o rótulo em cinco arquivos.</span><span class="sxs-lookup"><span data-stu-id="e51d9-126">In the viewer, repeat steps 1 and 2, and do this until you have saved the label in five files.</span></span>

    ![Configurações avançadas](../media/content-understanding/select-service-start-date.png) 


### <a name="add-a-negative-example"></a><span data-ttu-id="e51d9-128">Adicionar um exemplo negativo</span><span class="sxs-lookup"><span data-stu-id="e51d9-128">Add a negative example</span></span>

<span data-ttu-id="e51d9-129">Semelhante à forma como você adicionaria um arquivo de exemplo negativo ao criar um classificador, precisa adicionar um exemplo negativo para o extrator.</span><span class="sxs-lookup"><span data-stu-id="e51d9-129">Similar to how you would add a negative example file when creating a classifier, you need to add a negative example for the extractor.</span></span> <span data-ttu-id="e51d9-130">Para o nosso exemplo, ele deve ser um arquivo que não contém um valor de data de início do serviço.</span><span class="sxs-lookup"><span data-stu-id="e51d9-130">For our example, it should be a file that does not contain a Service Start Date value.</span></span>

1. <span data-ttu-id="e51d9-131">Na lista **exemplos rotulados** , selecione um exemplo negativo.</span><span class="sxs-lookup"><span data-stu-id="e51d9-131">From the **Labeled examples** list, select a negative example.</span></span>
2. <span data-ttu-id="e51d9-132">No visualizador, na parte superior do artigo, selecione **nenhum rótulo presente**.</span><span class="sxs-lookup"><span data-stu-id="e51d9-132">In the viewer, on the top of the article, select **No label present**.</span></span>
3. <span data-ttu-id="e51d9-133">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e51d9-133">Click **Save**.</span></span>
 
<span data-ttu-id="e51d9-134">Depois de rotular cinco arquivos, uma faixa de notificação será exibida informando que você vai para o treinamento.</span><span class="sxs-lookup"><span data-stu-id="e51d9-134">Once you have labeled five files, a notification banner will display informing you to move to training.</span></span> <span data-ttu-id="e51d9-135">Você pode optar por mais documentos ou avançar no treinamento.</span><span class="sxs-lookup"><span data-stu-id="e51d9-135">You can choose to more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="e51d9-136">Adicionar uma explicação</span><span class="sxs-lookup"><span data-stu-id="e51d9-136">Add an explanation</span></span>

<span data-ttu-id="e51d9-137">Para nosso exemplo, vamos criar uma explicação que forneça uma dica sobre o próprio formato de entidade e variações que ela pode ter nos documentos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="e51d9-137">For our example, we are going to create an explanation that provides a hint about the entity format itself and variations it may have in the example documents.</span></span> <span data-ttu-id="e51d9-138">Por exemplo, um valor de data pode estar em vários formatos diferentes, como:</span><span class="sxs-lookup"><span data-stu-id="e51d9-138">For example,a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="e51d9-139">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="e51d9-139">10/14/2019</span></span>
- <span data-ttu-id="e51d9-140">14 de outubro de 2019</span><span class="sxs-lookup"><span data-stu-id="e51d9-140">October 14, 2019</span></span>
- <span data-ttu-id="e51d9-141">Segunda-feira, 14 de outubro de 2019</span><span class="sxs-lookup"><span data-stu-id="e51d9-141">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="e51d9-142">Para ajudar a identificar a *data de início do serviço* , você pode criar uma explicação de padrão.</span><span class="sxs-lookup"><span data-stu-id="e51d9-142">To help identify the *Service Start Date* you can create a pattern explanation.</span></span>

1. <span data-ttu-id="e51d9-143">Na seção explicação, selecione **novo**e digite um nome (por exemplo, *Data*).</span><span class="sxs-lookup"><span data-stu-id="e51d9-143">In the Explanation section, select **New**, and then type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="e51d9-144">Para o tipo, selecione **lista padrão**.</span><span class="sxs-lookup"><span data-stu-id="e51d9-144">For the Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="e51d9-145">Para o valor, você precisa fornecer a variação de data, conforme aparecem nos arquivos de amostra.</span><span class="sxs-lookup"><span data-stu-id="e51d9-145">For the value, you need to provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="e51d9-146">Por exemplo, se você tiver formatos de data que aparecem como 0/00/0000, você inseriria qualquer variação que possa aparecer em seus documentos, como:</span><span class="sxs-lookup"><span data-stu-id="e51d9-146">For example, if you have date formats that appear as 0/00/0000, you would enter any variations that might appear in your documents, such as:</span></span>
    - <span data-ttu-id="e51d9-147">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="e51d9-147">0/0/0000</span></span>
    - <span data-ttu-id="e51d9-148">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="e51d9-148">0/00/0000</span></span>
    - <span data-ttu-id="e51d9-149">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="e51d9-149">00/0/0000</span></span>
    - <span data-ttu-id="e51d9-150">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="e51d9-150">00/00/0000</span></span>
4. <span data-ttu-id="e51d9-151">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e51d9-151">Select **Save**.</span></span>


### <a name="use-the-explanation-library"></a><span data-ttu-id="e51d9-152">Usar a biblioteca de explicação</span><span class="sxs-lookup"><span data-stu-id="e51d9-152">Use the Explanation library</span></span>

<span data-ttu-id="e51d9-153">Para criar explicações para coisas como datas, é muito mais fácil usar a biblioteca de explicação do que inserir manualmente todas as variações.</span><span class="sxs-lookup"><span data-stu-id="e51d9-153">For creating explanations for things such as dates, it is much easier to use the explanation library than to manually enter all variations.</span></span> <span data-ttu-id="e51d9-154">A biblioteca de explicação é um conjunto de explicações predefinidas de frases e padrões.</span><span class="sxs-lookup"><span data-stu-id="e51d9-154">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="e51d9-155">A biblioteca tenta fornecer todos os formatos de frases comuns ou listas de padrões, como datas, números de telefone, CEP e muitas outras.</span><span class="sxs-lookup"><span data-stu-id="e51d9-155">The library tries to provide all formats for common phrase or pattern lists, such as dates, phone numbers, zip code, and many others.</span></span> 

<span data-ttu-id="e51d9-156">Para nosso exemplo de *data de início do serviço* , é mais eficiente usar a explicação previamente criada para *Data* na biblioteca de explicação:</span><span class="sxs-lookup"><span data-stu-id="e51d9-156">For our *Service Start Date* example, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="e51d9-157">Na **seção explicação**, \* \* selecione **novo**e selecione **na biblioteca explicação**.</span><span class="sxs-lookup"><span data-stu-id="e51d9-157">In the **Explanation section**,\*\* select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="e51d9-158">Na biblioteca explicação, selecione **Data**.</span><span class="sxs-lookup"><span data-stu-id="e51d9-158">From the explanation library, select **Date**.</span></span> <span data-ttu-id="e51d9-159">Você pode exibir todas as variações de data que serão reconhecidas.</span><span class="sxs-lookup"><span data-stu-id="e51d9-159">You can view all variations of date that will be recognized.</span></span>
3. <span data-ttu-id="e51d9-160">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e51d9-160">Select **Add**.</span></span></br>

    ![Biblioteca de explicação](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="e51d9-162">Na página **criar uma explicação** , as informações de *Data* da biblioteca explicação farão preenchimento automático dos campos.</span><span class="sxs-lookup"><span data-stu-id="e51d9-162">On the **Create an explanation** page, the *Date* information from the explanation library will autofill the fields.</span></span> <span data-ttu-id="e51d9-163">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e51d9-163">Select **Save**.</span></span></br>

    ![Biblioteca de explicação](../media/content-understanding/date-explanation-library.png) 

 
## <a name="train-the-model"></a><span data-ttu-id="e51d9-165">Treinar o modelo</span><span class="sxs-lookup"><span data-stu-id="e51d9-165">Train the model</span></span> 

<span data-ttu-id="e51d9-166">Salvar sua explicação começará o treinamento.</span><span class="sxs-lookup"><span data-stu-id="e51d9-166">Saving your explanation will start the training.</span></span> <span data-ttu-id="e51d9-167">Se o modelo tiver informações suficientes para extrair os dados dos arquivos de exemplo rotulados, você verá cada arquivo rotulado com **correspondência**.</span><span class="sxs-lookup"><span data-stu-id="e51d9-167">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![Biblioteca de explicação](../media/content-understanding/match2.png) 

<span data-ttu-id="e51d9-169">Se a explicação não tiver informações suficientes para localizar os dados que você deseja extrair, cada arquivo será rotulado com **incompatibilidade**.</span><span class="sxs-lookup"><span data-stu-id="e51d9-169">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="e51d9-170">Você pode clicar nos arquivos incompatíveis para ver mais informações sobre o motivo pelo qual houve uma incompatibilidade.</span><span class="sxs-lookup"><span data-stu-id="e51d9-170">You can click on the Mismatched files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="e51d9-171">Adicionar outra explicação</span><span class="sxs-lookup"><span data-stu-id="e51d9-171">Add another explanation</span></span>

<span data-ttu-id="e51d9-172">Em geral, a incompatibilidade é uma indicação de que a explicação fornecida não forneceu informações suficientes para extrair o valor de data de início do serviço para corresponder aos nossos arquivos rotulados.</span><span class="sxs-lookup"><span data-stu-id="e51d9-172">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="e51d9-173">Talvez seja necessário editá-lo ou adicionar outra explicação.</span><span class="sxs-lookup"><span data-stu-id="e51d9-173">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="e51d9-174">Para o nosso exemplo, percebemos que a *data de início do serviço de sequência de texto de* sempre precede o valor real.</span><span class="sxs-lookup"><span data-stu-id="e51d9-174">For our example, we notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="e51d9-175">Para ajudar a identificar a data de início do serviço, podemos criar uma explicação de frase.</span><span class="sxs-lookup"><span data-stu-id="e51d9-175">To help identify the Service Start Date we can create a phrase explanation.</span></span>

1. <span data-ttu-id="e51d9-176">Na seção explicação, selecione **novo**e digite um nome (por exemplo, *cadeia de caracteres de prefixo*).</span><span class="sxs-lookup"><span data-stu-id="e51d9-176">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="e51d9-177">Para o tipo, selecione **lista de frases**.</span><span class="sxs-lookup"><span data-stu-id="e51d9-177">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="e51d9-178">Use a *data de início do serviço* como o valor.</span><span class="sxs-lookup"><span data-stu-id="e51d9-178">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="e51d9-179">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e51d9-179">Select **Save**.</span></span>

    ![Biblioteca de explicação](../media/content-understanding/prefix-string.png) 


## <a name="train-the-model"></a><span data-ttu-id="e51d9-181">Treinar o modelo</span><span class="sxs-lookup"><span data-stu-id="e51d9-181">Train the model</span></span>

<span data-ttu-id="e51d9-182">Salvar sua explicação iniciará o treinamento novamente, desta vez usando as duas explicações em nosso exemplo.</span><span class="sxs-lookup"><span data-stu-id="e51d9-182">Saving your explanation will start the training again, this time using both explanations in our example.</span></span> <span data-ttu-id="e51d9-183">Se o modelo tiver informações suficientes para extrair os dados dos arquivos de exemplo rotulados, você verá cada arquivo rotulado com **correspondência**.</span><span class="sxs-lookup"><span data-stu-id="e51d9-183">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span> 

<span data-ttu-id="e51d9-184">Se você receber **incompatibilidades** novamente em seus arquivos rotulados, talvez seja necessário criar outra explicação para fornecer o modelo mais informações para identificar o tipo de documento ou Confira como fazer alterações nos existentes.</span><span class="sxs-lookup"><span data-stu-id="e51d9-184">If you again receive a **Mismatch** on your labeled files, you may need to create another explanation to provide the model more information to identify the document type, or look at making changes to your existing ones.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="e51d9-185">Testar seu modelo</span><span class="sxs-lookup"><span data-stu-id="e51d9-185">Test your model</span></span>

<span data-ttu-id="e51d9-186">Se você recebeu uma correspondência em seus arquivos de exemplo rotulados, agora você pode testar seu modelo em seus arquivos de exemplo não rotulados restantes.</span><span class="sxs-lookup"><span data-stu-id="e51d9-186">If you received a match on your labeled example files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="e51d9-187">Na home page do modelo, clique na guia **testar** .  Isso executará o modelo em seus arquivos de exemplo sem rótulo.</span><span class="sxs-lookup"><span data-stu-id="e51d9-187">On the model home page, click the **Test** tab.  This will run the model on your unlabeled example files.</span></span>
2. <span data-ttu-id="e51d9-188">Na lista de **arquivos de teste** , seus arquivos de exemplo serão exibidos e mostrarão se o modelo é capaz de extrair as informações necessárias.</span><span class="sxs-lookup"><span data-stu-id="e51d9-188">In the **Test files** list, your example files will display and will show if the model is able to extract the information you need from them.</span></span> <span data-ttu-id="e51d9-189">Você pode usar essas informações para ajudar a determinar a eficácia do seu classificador na identificação de seus documentos.</span><span class="sxs-lookup"><span data-stu-id="e51d9-189">You can use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Teste em seus arquivos](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a><span data-ttu-id="e51d9-191">Confira também</span><span class="sxs-lookup"><span data-stu-id="e51d9-191">See Also</span></span>
  




