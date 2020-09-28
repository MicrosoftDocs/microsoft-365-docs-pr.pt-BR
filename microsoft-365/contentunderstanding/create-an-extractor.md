---
title: Criar um extrator
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
description: Saiba como criar um extrator no Microsoft SharePoint Syntex.
ms.openlocfilehash: 740df6769b3a1675e4e1691f84d164312b15567c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295451"
---
# <a name="create-an-extractor-preview"></a><span data-ttu-id="58c59-103">Criar um extrator (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="58c59-103">Create an extractor (Preview)</span></span>

<span data-ttu-id="58c59-104">O conteúdo deste artigo é para a visualização privada do projeto Cortex.</span><span class="sxs-lookup"><span data-stu-id="58c59-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="58c59-105">[Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="58c59-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="58c59-106">Antes ou depois de criar um modelo de classificador para automatizar a identificação e a classificação de tipos de documento específicos, você pode optar por adicionar extratores ao modelo para extrair informações específicas desses documentos.</span><span class="sxs-lookup"><span data-stu-id="58c59-106">Before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="58c59-107">Por exemplo, você pode querer que seu modelo não apenas identifique todos os documentos de *renovação de contrato* adicionados à sua biblioteca de documentos, mas também para exibir a data de *início do serviço* para cada documento como uma coluna na biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="58c59-107">For example, you may want your model not only to identify all *Contract Renewal* documents added to your document library, but also to display the *Service Start date* for each document as a column in the document library.</span></span>

<span data-ttu-id="58c59-108">Você precisa criar um extrator para cada entidade no documento que você deseja extrair.</span><span class="sxs-lookup"><span data-stu-id="58c59-108">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="58c59-109">No exemplo, você deseja extrair a data de *início do serviço* para cada documento de *renovação de contrato* identificado pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="58c59-109">In the sample, you want to extract the *Service Start Date* for each *Contract Renewal* document that is identified by the model.</span></span> <span data-ttu-id="58c59-110">Isso deve acontecer quando você quiser ver um modo de exibição na biblioteca de documentos de todos os documentos de *renovação de contrato* com uma coluna mostrando o valor de data de início do serviço para cada documento.</span><span class="sxs-lookup"><span data-stu-id="58c59-110">This must happen when you want to see a view in the document library of all the *Contract Renewal* documents with a column showing the Service Start date value for each document.</span></span>

> [!NOTE]
> <span data-ttu-id="58c59-111">Antes de criar um extrator, você precisa [adicionar seus arquivos de exemplo](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier#add-your-example-files) para ajudar a treinar o modelo para identificar as informações que você deseja extrair.</span><span class="sxs-lookup"><span data-stu-id="58c59-111">Before creating an extractor, you need to [add your example files](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier#add-your-example-files) to help train the model to identify the information you want to extract.</span></span> <span data-ttu-id="58c59-112">Use os mesmos arquivos de exemplo usados para criar seu classificador.</span><span class="sxs-lookup"><span data-stu-id="58c59-112">Use the same sample files you used to create your classifier.</span></span>

## <a name="name-your-extractor"></a><span data-ttu-id="58c59-113">Nomear seu extrator</span><span class="sxs-lookup"><span data-stu-id="58c59-113">Name your extractor</span></span>

1. <span data-ttu-id="58c59-114">Na página inicial do modelo, no bloco **criar e treinar extratores** , clique em **treinar extrator**.</span><span class="sxs-lookup"><span data-stu-id="58c59-114">From the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="58c59-115">Na tela **novo extrator de entidade** , digite o nome do extrator no campo **nome do novo extrator** .</span><span class="sxs-lookup"><span data-stu-id="58c59-115">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="58c59-116">Por exemplo, nomeie a **data de início do serviço** , se você quiser extrair a data de início do serviço de cada documento de renovação de contrato.</span><span class="sxs-lookup"><span data-stu-id="58c59-116">For example, name it **Service Start Date** if you want to extract the service start date from each Contract Renewal document.</span></span>
3. <span data-ttu-id="58c59-117">Clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="58c59-117">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="58c59-118">Adicionar um rótulo</span><span class="sxs-lookup"><span data-stu-id="58c59-118">Add a label</span></span>

<span data-ttu-id="58c59-119">A próxima etapa é rotular as informações que você deseja extrair em seus arquivos de treinamento de amostra.</span><span class="sxs-lookup"><span data-stu-id="58c59-119">The next step is to label the information you want to extract in your sample training files.</span></span>

<span data-ttu-id="58c59-120">A criação do extrator abre a página do extrator.</span><span class="sxs-lookup"><span data-stu-id="58c59-120">Creating the extractor opens the extractor page.</span></span> <span data-ttu-id="58c59-121">Veja aqui uma lista de seus arquivos de exemplo, com o primeiro arquivo na lista exibida no visualizador.</span><span class="sxs-lookup"><span data-stu-id="58c59-121">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="58c59-122">No visualizador, selecione os dados que você deseja extrair dos arquivos.</span><span class="sxs-lookup"><span data-stu-id="58c59-122">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="58c59-123">Por exemplo, se você quiser extrair a *data de início do serviço*, destaque o valor de data no primeiro arquivo (*segunda-feira, 14 de outubro de 2019*).</span><span class="sxs-lookup"><span data-stu-id="58c59-123">For example, if you want to extract the *Start Service Date*, you highlight the date value in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="58c59-124">e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="58c59-124">and then click **Save**.</span></span>  <span data-ttu-id="58c59-125">Você deve ver o valor exibir do arquivo na lista de exemplos rotulados, abaixo da coluna **rótulo** .</span><span class="sxs-lookup"><span data-stu-id="58c59-125">You should see the value display from the file in the Labeled examples list, under the **Label** column.</span></span>
2. <span data-ttu-id="58c59-126">Selecione **Avançar arquivo** para salvar automaticamente e abra o próximo arquivo na lista no visualizador.</span><span class="sxs-lookup"><span data-stu-id="58c59-126">Select **Next file** to auto save and open the next file in the list in the viewer.</span></span> <span data-ttu-id="58c59-127">Ou selecione **salvar** e, em seguida, selecione outro arquivo na lista **exemplos rotulados** .</span><span class="sxs-lookup"><span data-stu-id="58c59-127">Or select **Save** and then select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="58c59-128">No visualizador, repita as etapas 1 e 2 e, em seguida, repita até salvar o rótulo em todos os cinco arquivos.</span><span class="sxs-lookup"><span data-stu-id="58c59-128">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all five files.</span></span>

    ![Configurações avançadas](../media/content-understanding/select-service-start-date.png) 

### <a name="add-a-negative-example"></a><span data-ttu-id="58c59-130">Adicionar um exemplo negativo</span><span class="sxs-lookup"><span data-stu-id="58c59-130">Add a negative example</span></span>

<span data-ttu-id="58c59-131">Semelhante à forma como você adiciona um arquivo de amostra negativo ao criar um classificador, você precisa adicionar uma amostra negativa para o extrator.</span><span class="sxs-lookup"><span data-stu-id="58c59-131">Similar to how you add a negative sample file when creating a classifier, you need to add a negative sample for the extractor.</span></span> <span data-ttu-id="58c59-132">Deve ser um arquivo que não contenha um valor de data de "início de serviço".</span><span class="sxs-lookup"><span data-stu-id="58c59-132">It should be a file that does not contain a "Service Start" date value.</span></span>

1. <span data-ttu-id="58c59-133">Na lista **exemplos rotulados** , selecione um exemplo negativo.</span><span class="sxs-lookup"><span data-stu-id="58c59-133">From the **Labeled examples** list, select a negative example.</span></span>
2. <span data-ttu-id="58c59-134">No visualizador na parte superior do artigo, selecione **nenhum rótulo presente**.</span><span class="sxs-lookup"><span data-stu-id="58c59-134">In the viewer on the top of the article, select **No label present**.</span></span>
3. <span data-ttu-id="58c59-135">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="58c59-135">Click **Save**.</span></span>
 
<span data-ttu-id="58c59-136">Depois de rotular cinco arquivos, uma faixa de notificação é exibida informando que você vá para o treinamento.</span><span class="sxs-lookup"><span data-stu-id="58c59-136">Once you labeled five files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="58c59-137">Você pode optar por mais documentos ou avançar no treinamento.</span><span class="sxs-lookup"><span data-stu-id="58c59-137">You can choose to more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="58c59-138">Adicionar uma explicação</span><span class="sxs-lookup"><span data-stu-id="58c59-138">Add an explanation</span></span>

<span data-ttu-id="58c59-139">Para o exemplo, você cria uma explicação que fornece uma dica sobre o próprio formato de entidade e variações que ela pode ter nos documentos de amostra.</span><span class="sxs-lookup"><span data-stu-id="58c59-139">For the example, you create an explanation that provides a hint about the entity format itself and variations it may have in the sample documents.</span></span> <span data-ttu-id="58c59-140">Por exemplo, um valor de data pode estar em vários formatos diferentes, como:</span><span class="sxs-lookup"><span data-stu-id="58c59-140">For example, a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="58c59-141">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="58c59-141">10/14/2019</span></span>
- <span data-ttu-id="58c59-142">14 de outubro de 2019</span><span class="sxs-lookup"><span data-stu-id="58c59-142">October 14, 2019</span></span>
- <span data-ttu-id="58c59-143">Segunda-feira, 14 de outubro de 2019</span><span class="sxs-lookup"><span data-stu-id="58c59-143">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="58c59-144">Para ajudar a identificar a *data de início do serviço* , você cria uma explicação de padrão.</span><span class="sxs-lookup"><span data-stu-id="58c59-144">To help identify the *Service Start Date* you create a pattern explanation.</span></span>

1. <span data-ttu-id="58c59-145">Na seção explicação, selecione **novo** e digite um nome (por exemplo, *Data*).</span><span class="sxs-lookup"><span data-stu-id="58c59-145">In the Explanation section, select **New** and type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="58c59-146">Em tipo, selecione **lista padrão**.</span><span class="sxs-lookup"><span data-stu-id="58c59-146">For Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="58c59-147">Para o valor, forneça a variação de data, conforme aparecem nos arquivos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="58c59-147">For Value, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="58c59-148">Por exemplo, se você tiver formatos de data que aparecem como 0/00/0000, você insere qualquer variação que aparece em seus documentos, como:</span><span class="sxs-lookup"><span data-stu-id="58c59-148">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>
    - <span data-ttu-id="58c59-149">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="58c59-149">0/0/0000</span></span>
    - <span data-ttu-id="58c59-150">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="58c59-150">0/00/0000</span></span>
    - <span data-ttu-id="58c59-151">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="58c59-151">00/0/0000</span></span>
    - <span data-ttu-id="58c59-152">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="58c59-152">00/00/0000</span></span>
4. <span data-ttu-id="58c59-153">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="58c59-153">Select **Save**.</span></span>

### <a name="use-the-explanation-library"></a><span data-ttu-id="58c59-154">Usar a biblioteca de explicação</span><span class="sxs-lookup"><span data-stu-id="58c59-154">Use the Explanation library</span></span>

<span data-ttu-id="58c59-155">Para criar explicações para itens como datas, é mais fácil usar a biblioteca de explicação do que inserir manualmente todas as variações.</span><span class="sxs-lookup"><span data-stu-id="58c59-155">For creating explanations for items such as dates, it is easier to use the explanation library than to manually enter all variations.</span></span> <span data-ttu-id="58c59-156">A biblioteca de explicação é um conjunto de explicações predefinidas de frases e padrões.</span><span class="sxs-lookup"><span data-stu-id="58c59-156">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="58c59-157">A biblioteca fornece todos os formatos para frases comuns ou listas de padrões, como datas, números de telefone, CEP, etc.</span><span class="sxs-lookup"><span data-stu-id="58c59-157">The library provides all formats for common phrase or pattern lists, such as dates, phone numbers, zip code, etc.</span></span> 

<span data-ttu-id="58c59-158">Para o exemplo de *data de início do serviço* , é mais eficiente usar a explicação previamente criada para *Data* na biblioteca de explicação:</span><span class="sxs-lookup"><span data-stu-id="58c59-158">For the *Service Start Date* sample, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="58c59-159">Na **seção explicação**, selecione **novo**e selecione **na biblioteca explicação**.</span><span class="sxs-lookup"><span data-stu-id="58c59-159">In the **Explanation section**, select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="58c59-160">Na biblioteca explicação, selecione **Data**.</span><span class="sxs-lookup"><span data-stu-id="58c59-160">From the explanation library, select **Date**.</span></span> <span data-ttu-id="58c59-161">Você pode exibir todas as variações de data que são reconhecidas.</span><span class="sxs-lookup"><span data-stu-id="58c59-161">You can view all variations of date that are recognized.</span></span>
3. <span data-ttu-id="58c59-162">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="58c59-162">Select **Add**.</span></span></br>

    ![Biblioteca de explicação](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="58c59-164">Na página **criar uma explicação** , as informações de *Data* da biblioteca explicação automática preencherão os campos.</span><span class="sxs-lookup"><span data-stu-id="58c59-164">On the **Create an explanation** page, the *Date* information from the explanation library auto fills the fields.</span></span> <span data-ttu-id="58c59-165">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="58c59-165">Select **Save**.</span></span></br>

    ![Data](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a><span data-ttu-id="58c59-167">Treinar o modelo</span><span class="sxs-lookup"><span data-stu-id="58c59-167">Train the model</span></span> 

<span data-ttu-id="58c59-168">Salvando sua explicação inicie o treinamento.</span><span class="sxs-lookup"><span data-stu-id="58c59-168">Saving your explanation start the training.</span></span> <span data-ttu-id="58c59-169">Se o modelo tiver informações suficientes para extrair os dados dos arquivos de exemplo rotulados, você verá cada arquivo rotulado com **correspondência**.</span><span class="sxs-lookup"><span data-stu-id="58c59-169">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![Match](../media/content-understanding/match2.png) 

<span data-ttu-id="58c59-171">Se a explicação não tiver informações suficientes para localizar os dados que você deseja extrair, cada arquivo será rotulado com **incompatibilidade**.</span><span class="sxs-lookup"><span data-stu-id="58c59-171">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="58c59-172">Você pode clicar nos arquivos **incompatíveis** para ver mais informações sobre o motivo pelo qual houve uma incompatibilidade.</span><span class="sxs-lookup"><span data-stu-id="58c59-172">You can click on the **Mismatched** files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="58c59-173">Adicionar outra explicação</span><span class="sxs-lookup"><span data-stu-id="58c59-173">Add another explanation</span></span>

<span data-ttu-id="58c59-174">Em geral, a incompatibilidade é uma indicação de que a explicação fornecida não forneceu informações suficientes para extrair o valor de data de início do serviço para corresponder aos nossos arquivos rotulados.</span><span class="sxs-lookup"><span data-stu-id="58c59-174">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="58c59-175">Talvez seja necessário editá-lo ou adicionar outra explicação.</span><span class="sxs-lookup"><span data-stu-id="58c59-175">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="58c59-176">Para o exemplo, observe que a *data de início do serviço de sequência de texto de* sempre precede o valor real.</span><span class="sxs-lookup"><span data-stu-id="58c59-176">For the sample, notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="58c59-177">Para ajudar a identificar a data de início do serviço, você precisa de OT criar uma explicação de frase.</span><span class="sxs-lookup"><span data-stu-id="58c59-177">To help identify the Service Start Date, you need ot create a phrase explanation.</span></span>

1. <span data-ttu-id="58c59-178">Na seção explicação, selecione **novo**e digite um nome (por exemplo, *cadeia de caracteres de prefixo*).</span><span class="sxs-lookup"><span data-stu-id="58c59-178">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="58c59-179">Para o tipo, selecione **lista de frases**.</span><span class="sxs-lookup"><span data-stu-id="58c59-179">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="58c59-180">Use a *data de início do serviço* como o valor.</span><span class="sxs-lookup"><span data-stu-id="58c59-180">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="58c59-181">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="58c59-181">Select **Save**.</span></span>

    ![Cadeia de caracteres de prefixo](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a><span data-ttu-id="58c59-183">Treine o modelo novamente</span><span class="sxs-lookup"><span data-stu-id="58c59-183">Train the model again</span></span>

<span data-ttu-id="58c59-184">Salvar a explicação inicia o treinamento novamente, desta vez usando as duas explicações no exemplo.</span><span class="sxs-lookup"><span data-stu-id="58c59-184">Saving the explanation starts the training again, this time using both explanations in the sample.</span></span> <span data-ttu-id="58c59-185">Se o modelo tiver informações suficientes para extrair os dados dos arquivos de amostra rotulados, você verá cada arquivo rotulado com **correspondência**.</span><span class="sxs-lookup"><span data-stu-id="58c59-185">If your model has enough information to extract the data from the labeled sample files, you see each file labeled with **Match**.</span></span> 

<span data-ttu-id="58c59-186">Se você receber **incompatibilidades** novamente em seus arquivos rotulados, provavelmente precisará criar outra explicação para fornecer o modelo mais informações para identificar o tipo de documento ou considere fazer alterações no modelo de amostra.</span><span class="sxs-lookup"><span data-stu-id="58c59-186">If you again receive a **Mismatch** on your labeled files, you likely need to create another explanation to provide the model more information to identify the document type, or consider making changes to your sample model.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="58c59-187">Testar seu modelo</span><span class="sxs-lookup"><span data-stu-id="58c59-187">Test your model</span></span>

<span data-ttu-id="58c59-188">Se você receber uma correspondência em seus arquivos de amostra rotulados, agora você pode testar o modelo nos arquivos de amostra não rotulados restantes.</span><span class="sxs-lookup"><span data-stu-id="58c59-188">If you receive a match on your labeled sample files, you can now test your model on the remaining unlabeled sample files.</span></span>

1. <span data-ttu-id="58c59-189">Na página inicial do modelo, clique na guia **testar** .  Isso executa o modelo em seus arquivos de amostra sem rótulo.</span><span class="sxs-lookup"><span data-stu-id="58c59-189">From the model home page, click the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="58c59-190">Na lista **testar arquivos** , seus arquivos de exemplo são exibidos para mostrar se o modelo é capaz de extrair as informações necessárias.</span><span class="sxs-lookup"><span data-stu-id="58c59-190">In the **Test files** list, your example files display to show if the model is able to extract the information you need.</span></span> <span data-ttu-id="58c59-191">Use essas informações para ajudar a determinar a eficácia do seu classificador na identificação de seus documentos.</span><span class="sxs-lookup"><span data-stu-id="58c59-191">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Teste em seus arquivos](../media/content-understanding/test-filies-extractor.png) 
