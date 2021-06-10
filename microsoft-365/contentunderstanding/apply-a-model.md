---
title: Aplicar um modelo de compreensão de documento em uma biblioteca de documentos
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
localization_priority: Normal
description: Saiba como aplicar um modelo publicado a uma biblioteca de documentos do SharePoint
ms.openlocfilehash: cda9de43d0139c52f950527eb75d050602005fd2
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843289"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="eaee7-103">Aplicar um modelo de compreensão de documento no Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="eaee7-103">Apply a document understanding model in Microsoft SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="eaee7-104">Depois de publicar seu modelo de compreensão de documento, você pode aplicá-lo a uma ou mais bibliotecas de documentos do SharePoint no locatário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eaee7-104">After publishing your document understanding model, you can apply it to one or more SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="eaee7-105">Você só pode aplicar o modelo às bibliotecas de documentos às quais tem acesso.</span><span class="sxs-lookup"><span data-stu-id="eaee7-105">You are only able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="eaee7-106">Aplique seu modelo a uma biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="eaee7-106">Apply your model to a document library.</span></span>

<span data-ttu-id="eaee7-107">Para aplicar o modelo a uma biblioteca de documentos do SharePoint:</span><span class="sxs-lookup"><span data-stu-id="eaee7-107">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="eaee7-108">Na página inicial do modelo, no bloco **Aplicar modelo a bibliotecas**, marque **Publicar modelo**.</span><span class="sxs-lookup"><span data-stu-id="eaee7-108">On model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="eaee7-109">Ou você pode selecionar  **+Adicionar Biblioteca** na seção **Bibliotecas com esse modelo**.</span><span class="sxs-lookup"><span data-stu-id="eaee7-109">Or you can select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![Adicionar modelo à biblioteca](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="eaee7-111">Em seguida, você pode selecionar o site do SharePoint que contém a biblioteca de documentos à qual você deseja aplicar o modelo.</span><span class="sxs-lookup"><span data-stu-id="eaee7-111">You can then select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="eaee7-112">Se o site não for mostrado na lista, use a caixa de pesquisa para localizá-lo.</span><span class="sxs-lookup"><span data-stu-id="eaee7-112">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![Selecionar um Site](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > <span data-ttu-id="eaee7-114">Você deve ter permissões de *Gerenciar Lista* ou direitos de *Editar* na biblioteca de documentos para a qual você está aplicando o modelo.</span><span class="sxs-lookup"><span data-stu-id="eaee7-114">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="eaee7-115">Depois de selecionar o site, selecione a biblioteca de documentos à qual você deseja aplicar o modelo.</span><span class="sxs-lookup"><span data-stu-id="eaee7-115">After selecting the site, select the document library to which you want to apply the model.</span></span> <span data-ttu-id="eaee7-116">No exemplo, selecione a biblioteca de documentos do *Documento* do site de *Acompanhamento de Caso da Contoso*. </span><span class="sxs-lookup"><span data-stu-id="eaee7-116">In the sample, select the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![Selecionar uma biblioteca de documentos](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="eaee7-118">Já que o modelo está associado a um tipo de conteúdo, quando for aplicado à biblioteca, ele adicionará o tipo de conteúdo e seu modo de exibição com as etiquetas extraídas mostradas como colunas.</span><span class="sxs-lookup"><span data-stu-id="eaee7-118">Since the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="eaee7-119">Esse modo de exibição é a exibição padrão da biblioteca por padrão, mas você pode optar por não ter essa exibição padrão selecionando **Configurações avançadas** e desmarcando **Definir esse novo modo de exibição como padrão**.</span><span class="sxs-lookup"><span data-stu-id="eaee7-119">This view is the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![Exibição de biblioteca](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="eaee7-121">Selecione **Adicionar** para aplicar o modelo à biblioteca.</span><span class="sxs-lookup"><span data-stu-id="eaee7-121">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="eaee7-122">Na página inicial do modelo, na seção **Bibliotecas com esse modelo**, você deverá ver a URL do site do SharePoint listado.</span><span class="sxs-lookup"><span data-stu-id="eaee7-122">On the model home page, in the **Libraries with this model** section, you should see the URL to the SharePoint site listed.</span></span></br>

    ![Biblioteca selecionada](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="eaee7-124">Vá para a biblioteca de documentos e verifique se você está no modo de exibição de biblioteca de documentos do modelo.</span><span class="sxs-lookup"><span data-stu-id="eaee7-124">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="eaee7-125">Observe que, se você selecionar o botão de informações ao lado do nome da biblioteca de documentos, uma mensagem indicará que o modelo foi aplicado à biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="eaee7-125">Notice that if you select the information button next to the document library name, a message notes that the document library has a model applied to it.</span></span>

    ![Modo de exibição informações](../media/content-understanding/info-du.png)</br> 

    <span data-ttu-id="eaee7-127">Você pode selecionar a opção **Exibir modelos ativos** para ver detalhes sobre todos os modelos aplicados à biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="eaee7-127">You can the select **View active models** to see details about any models that are applied to the document library.</span></span>

8. <span data-ttu-id="eaee7-128">No painel **Modelos ativos**, você pode ver os modelos aplicados à biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="eaee7-128">In the **Active models** pane, you can see the models that are applied to the document library.</span></span> <span data-ttu-id="eaee7-129">Selecione um modelo para ver mais detalhes sobre ele, como uma descrição do modelo, quem publicou o modelo e se ele aplica um rótulo de retenção aos arquivos que ele classifica.</span><span class="sxs-lookup"><span data-stu-id="eaee7-129">Select a model to see more details about it, such as a description of the model, who published the model, and if the model applies a retention label to the files it classifies.</span></span>

    ![Painel Modelos ativos](../media/content-understanding/active-models.png)</br> 

<span data-ttu-id="eaee7-131">Depois de aplicar o modelo à biblioteca de documentos, você pode começar a carregar documentos no site e ver os resultados.</span><span class="sxs-lookup"><span data-stu-id="eaee7-131">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="eaee7-132">O modelo identifica todos os arquivos com o tipo de conteúdo associado do modelo e os lista em seu modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="eaee7-132">The model identifies any files with model’s associated content type and lists them in your view.</span></span> <span data-ttu-id="eaee7-133">Se o modelo tiver os extratores, o modo de exibição exibirá colunas para os dados que você está extraindo de cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="eaee7-133">If your model has any extractors, the view displays columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="eaee7-134">Aplicar o modelo aos arquivos que já estão na biblioteca de documentos</span><span class="sxs-lookup"><span data-stu-id="eaee7-134">Apply the model to files already in the document library</span></span>

<span data-ttu-id="eaee7-135">Enquanto um modelo aplicado processa todos os arquivos carregados na biblioteca de documentos após a aplicação, você também pode fazer o seguinte para executar o modelo em arquivos que já existem na biblioteca de documentos antes do modelo aplicado:</span><span class="sxs-lookup"><span data-stu-id="eaee7-135">While an applied model processes all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already exists in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="eaee7-136">Na biblioteca de documentos, selecione os arquivos que você deseja processar por seu modelo.</span><span class="sxs-lookup"><span data-stu-id="eaee7-136">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="eaee7-137">Depois de selecionar seus arquivos, **Classificar e extrair** aparecerá na faixa de opções da biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="eaee7-137">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="eaee7-138">Selecione **Classificar e extrair**.</span><span class="sxs-lookup"><span data-stu-id="eaee7-138">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="eaee7-139">Os arquivos selecionados serão adicionados à fila a ser processada.</span><span class="sxs-lookup"><span data-stu-id="eaee7-139">The files you selected will be added to the queue to be processed.</span></span>

      ![Classificar e extrair](../media/content-understanding/extract-classify.png)</br> 

> [!NOTE]
> <span data-ttu-id="eaee7-141">Você pode copiar arquivos individuais para uma biblioteca e aplicá-los a um modelo, mas não a pastas.</span><span class="sxs-lookup"><span data-stu-id="eaee7-141">You can copy individual files to a library and apply them to a model, but not folders.</span></span>

### <a name="the-classification-date-field"></a><span data-ttu-id="eaee7-142">O campo Data de Classificação</span><span class="sxs-lookup"><span data-stu-id="eaee7-142">The Classification Date field</span></span>

<span data-ttu-id="eaee7-143">Quando a compreensão de um documento do SharePoint Syntex ou um modelo de processamento de formulário é aplicado a uma biblioteca de documentos, um campo <b>Data de Classificação</b> é incluído no esquema de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="eaee7-143">When a SharePoint Syntex document understanding or form processing model is applied to a document library, a <b> Classification date </b> field is included in the library schema.</span></span> <span data-ttu-id="eaee7-144">Por padrão, esse campo fica vazio, mas quando os documentos são processados e classificados por um modelo, esse campo é atualizado com um carimbo de data e hora de conclusão.</span><span class="sxs-lookup"><span data-stu-id="eaee7-144">By default this field is empty, but when documents are processed and classified by a model, this field is updated with a date-time stamp of completion.</span></span> 

   ![Coluna Data de Classificação](../media/content-understanding/class-date-column.png)</br> 

<span data-ttu-id="eaee7-146">O campo Data de classificação é usado pelo [<b>Quando um arquivo é classificado por um modelo de compreensão de conteúdo</b> aciona o ](/connectors/sharepointonline/#when-a-file-is-classified-by-a-content-understanding-model) para executar um fluxo do Power Automate depois que um modelo de compreensão de conteúdo Syntex terminar de processar um arquivo e atualizar o campo "Data de classificação".</span><span class="sxs-lookup"><span data-stu-id="eaee7-146">The Classification date field is used by the [<b>When a file is classified by a content understanding model</b> trigger](/connectors/sharepointonline/#when-a-file-is-classified-by-a-content-understanding-model) to run a Power Automate flow after a Syntex content understanding model has finished processing a file and updated the "Classification date" field.</span></span>

   ![Gatilho de fluxo](../media/content-understanding/trigger.png)</br>

<span data-ttu-id="eaee7-148">O <b>Quando um arquivo é classificado por um modelo de compreensão de conteúdo</b> acionador pode ser usado para iniciar outro fluxo de trabalho usando qualquer informação extraída do arquivo.</span><span class="sxs-lookup"><span data-stu-id="eaee7-148">The <b>When a file is classified by a content understanding model</b> trigger can then be used to start another workflow using any  extracted information from the file.</span></span>



## <a name="see-also"></a><span data-ttu-id="eaee7-149">Confira também</span><span class="sxs-lookup"><span data-stu-id="eaee7-149">See Also</span></span>
[<span data-ttu-id="eaee7-150">Criar um classificador</span><span class="sxs-lookup"><span data-stu-id="eaee7-150">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="eaee7-151">Criar um extrator</span><span class="sxs-lookup"><span data-stu-id="eaee7-151">Create an extractor</span></span>](create-an-extractor.md)

<span data-ttu-id="eaee7-152">[Visão geral sobre Compreensão de Documentos](document-understanding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="eaee7-152">[Document Understanding overview](document-understanding-overview.md)</span></span>
