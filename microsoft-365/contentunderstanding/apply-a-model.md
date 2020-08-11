---
title: Aplicar um documento entendendo o modelo a uma biblioteca de documentos (visualização)
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
description: Saiba como aplicar um modelo publicado a uma biblioteca de documentos do SharePoint.
ms.openlocfilehash: 0658710704273ed04e9f2067413d1141773ef4aa
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612675"
---
# <a name="apply-a-document-understanding-model-preview"></a><span data-ttu-id="8a92f-103">Aplicar um documento entendendo o modelo (visualização)</span><span class="sxs-lookup"><span data-stu-id="8a92f-103">Apply a document understanding model (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="8a92f-104">O conteúdo deste artigo é para a visualização privada do Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="8a92f-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="8a92f-105">[Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="8a92f-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="8a92f-106">Após publicar seu documento entendendo o modelo, você pode aplicá-lo a uma biblioteca de documentos do SharePoint em seu locatário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8a92f-106">After publishing your document understanding model, you can apply it to a SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!Note]
> <span data-ttu-id="8a92f-107">Você só poderá aplicar o modelo às bibliotecas de documentos às quais você tem acesso.</span><span class="sxs-lookup"><span data-stu-id="8a92f-107">You will only be able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="8a92f-108">Aplique o modelo a uma biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="8a92f-108">Apply your model to a document library.</span></span>

<span data-ttu-id="8a92f-109">Para aplicar o modelo a uma biblioteca de documentos do SharePoint:</span><span class="sxs-lookup"><span data-stu-id="8a92f-109">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="8a92f-110">Na home page do modelo, no bloco **aplicar modelo para bibliotecas** , selecione **Publicar modelo**.</span><span class="sxs-lookup"><span data-stu-id="8a92f-110">On the model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="8a92f-111">Ou você pode selecionar **+ Adicionar biblioteca** na seção **bibliotecas com este modelo** .</span><span class="sxs-lookup"><span data-stu-id="8a92f-111">Or you can  select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![Adicionar modelo à biblioteca](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="8a92f-113">Em seguida, você pode selecionar o site do SharePoint que contém a biblioteca de documentos à qual você deseja aplicar o modelo.</span><span class="sxs-lookup"><span data-stu-id="8a92f-113">You can then select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="8a92f-114">Se o site não aparecer na lista, use a caixa Pesquisar para encontrá-lo.</span><span class="sxs-lookup"><span data-stu-id="8a92f-114">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![Selecionar um site](../media/content-understanding/site-search.png)</br>

    > [!Note]
    > <span data-ttu-id="8a92f-116">Você deve ter permissões de *lista* ou *Editar* direitos para a biblioteca de documentos à qual você está aplicando o modelo.</span><span class="sxs-lookup"><span data-stu-id="8a92f-116">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="8a92f-117">Depois de selecionar o site, você precisará selecionar a biblioteca de documentos à qual você deseja aplicar o modelo.</span><span class="sxs-lookup"><span data-stu-id="8a92f-117">After selecting the site, you then need to select the document library to which you want to apply the model.</span></span> <span data-ttu-id="8a92f-118">No exemplo, estamos selecionando *a biblioteca de documentos Documents* no site de acompanhamento de *casos da Contoso* .</span><span class="sxs-lookup"><span data-stu-id="8a92f-118">In the example, we are selecting the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![Selecionar uma biblioteca de documentos](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="8a92f-120">Como o modelo é associado a um tipo de conteúdo, quando você o aplica à biblioteca, ele criará um modo de exibição para o tipo de conteúdo com os rótulos que você extraiu mostrando como colunas.</span><span class="sxs-lookup"><span data-stu-id="8a92f-120">Since the model is associated to a content type, when you apply it to the library it will create a view for the content type with the labels you extracted showing as columns.</span></span> <span data-ttu-id="8a92f-121">Este modo de exibição será o modo de exibição padrão da biblioteca por padrão, mas você pode optar por não ser o modo de exibição padrão selecionando **Configurações avançadas** e desmarcando **definir este novo modo de exibição como padrão**.</span><span class="sxs-lookup"><span data-stu-id="8a92f-121">This view will be the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![Exibição de biblioteca](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="8a92f-123">Selecione **Adicionar** para aplicar o modelo à biblioteca.</span><span class="sxs-lookup"><span data-stu-id="8a92f-123">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="8a92f-124">Na página inicial do modelo, na seção **bibliotecas com este modelo** , você verá a URL para o site do SharePoint listado.</span><span class="sxs-lookup"><span data-stu-id="8a92f-124">On the model home page, in the **Libraries with this model** section, you will see the URL to the SharePoint site listed.</span></span></br>

    ![Exibição de biblioteca](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="8a92f-126">Vá para a biblioteca de documentos e verifique se você está no modo de exibição de biblioteca de documentos do modelo.</span><span class="sxs-lookup"><span data-stu-id="8a92f-126">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="8a92f-127">Você verá que, se você selecionar o botão de informações ao lado do nome da biblioteca de documentos, uma mensagem notará que o modelo foi aplicado à biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="8a92f-127">You'll notice that if you select the information button next to the document library name, a message will note that your model has been applied to the document library.</span></span>

    ![Exibição de biblioteca](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="8a92f-129">Depois de aplicar o modelo à biblioteca de documentos, você pode começar a carregar documentos no site e ver os resultados.</span><span class="sxs-lookup"><span data-stu-id="8a92f-129">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="8a92f-130">O modelo identificará todos os arquivos com o tipo de conteúdo associado ao modelo e os listará em seu modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="8a92f-130">The model will identify any files with model’s associated content type and will list them in your view.</span></span> <span data-ttu-id="8a92f-131">Se o modelo tiver quaisquer extratores, o modo de exibição exibirá colunas para os dados que você está extraindo de cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="8a92f-131">If your model has any extractors, the view will display columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="8a92f-132">Aplicar o modelo aos arquivos que já estão na biblioteca de documentos</span><span class="sxs-lookup"><span data-stu-id="8a92f-132">Apply the model to files already in the document library</span></span>

<span data-ttu-id="8a92f-133">Embora um modelo aplicado processe todos os arquivos carregados na biblioteca de documentos após a aplicação, você também pode fazer o seguinte para executar o modelo em arquivos que já existiam na biblioteca de documentos antes do modelo que está sendo aplicado:</span><span class="sxs-lookup"><span data-stu-id="8a92f-133">While an applied model will process all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already existed in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="8a92f-134">Na biblioteca de documentos, selecione os arquivos que você deseja que sejam processados pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="8a92f-134">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="8a92f-135">Depois de selecionar seus arquivos, **classificar e extrair** aparecerão na faixa de opções da biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="8a92f-135">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="8a92f-136">Selecione **classificar e extrair**.</span><span class="sxs-lookup"><span data-stu-id="8a92f-136">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="8a92f-137">Os arquivos selecionados serão adicionados à fila para serem processados.</span><span class="sxs-lookup"><span data-stu-id="8a92f-137">The files you selected will be added to the queue to be processed.</span></span>

      ![Classificar e extrair](../media/content-understanding/extract-classify.png)</br> 





## <a name="see-also"></a><span data-ttu-id="8a92f-139">Confira também</span><span class="sxs-lookup"><span data-stu-id="8a92f-139">See Also</span></span>
[<span data-ttu-id="8a92f-140">Criar um classificador</span><span class="sxs-lookup"><span data-stu-id="8a92f-140">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="8a92f-141">Criar um extrator</span><span class="sxs-lookup"><span data-stu-id="8a92f-141">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="8a92f-142">Visão geral da compreensão do documento</span><span class="sxs-lookup"><span data-stu-id="8a92f-142">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="8a92f-143">Criar um modelo de processamento de formulários</span><span class="sxs-lookup"><span data-stu-id="8a92f-143">Create a form processing model</span></span>](create-a-form-processing-model.md)  




