---
title: Aplicar um modelo de compreensão de documento em uma biblioteca de documentos
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Saiba como aplicar um modelo publicado a uma biblioteca de documentos do SharePoint
ms.openlocfilehash: 771b0f451d404c6e90f62091ca466bfaf34bae39
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338668"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="01242-103">Aplicar um modelo de compreensão de documento no Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="01242-103">Apply a document understanding model in Microsoft SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="01242-104">Depois de publicar seu modelo de compreensão de documento, você pode aplicá-lo a uma ou mais bibliotecas de documentos do SharePoint no locatário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="01242-104">After publishing your document understanding model, you can apply it to one or more SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="01242-105">Você só pode aplicar o modelo às bibliotecas de documentos às quais tem acesso.</span><span class="sxs-lookup"><span data-stu-id="01242-105">You are only able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="01242-106">Aplique seu modelo a uma biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="01242-106">Apply your model to a document library.</span></span>

<span data-ttu-id="01242-107">Para aplicar o modelo a uma biblioteca de documentos do SharePoint:</span><span class="sxs-lookup"><span data-stu-id="01242-107">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="01242-108">Na página inicial do modelo, no bloco **Aplicar modelo a bibliotecas**, marque **Publicar modelo**.</span><span class="sxs-lookup"><span data-stu-id="01242-108">On model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="01242-109">Ou você pode selecionar  **+Adicionar Biblioteca** na seção **Bibliotecas com esse modelo**.</span><span class="sxs-lookup"><span data-stu-id="01242-109">Or you can select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![Adicionar modelo à biblioteca](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="01242-111">Em seguida, você pode selecionar o site do SharePoint que contém a biblioteca de documentos à qual você deseja aplicar o modelo.</span><span class="sxs-lookup"><span data-stu-id="01242-111">You can then select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="01242-112">Se o site não for mostrado na lista, use a caixa de pesquisa para localizá-lo.</span><span class="sxs-lookup"><span data-stu-id="01242-112">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![Selecionar um Site](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > <span data-ttu-id="01242-114">Você deve ter permissões de *Gerenciar Lista \* ou direitos de*Editar\* na biblioteca de documentos para a qual você está aplicando o modelo.</span><span class="sxs-lookup"><span data-stu-id="01242-114">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="01242-115">Depois de selecionar o site, selecione a biblioteca de documentos à qual você deseja aplicar o modelo.</span><span class="sxs-lookup"><span data-stu-id="01242-115">After selecting the site, select the document library to which you want to apply the model.</span></span> <span data-ttu-id="01242-116">No exemplo, selecione a biblioteca de documentos do*Documento* do site de*Acompanhamento de Caso da Contoso*. </span><span class="sxs-lookup"><span data-stu-id="01242-116">In the sample, select the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![Selecionar uma biblioteca de documentos](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="01242-118">Já que o modelo está associado a um tipo de conteúdo, quando for aplicado à biblioteca, ele adicionará o tipo de conteúdo e seu modo de exibição com as etiquetas extraídas mostradas como colunas.</span><span class="sxs-lookup"><span data-stu-id="01242-118">Since the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="01242-119">Esse modo de exibição é a exibição padrão da biblioteca por padrão, mas você pode optar por não ter essa exibição padrão selecionando **Configurações avançadas** e desmarcando **Definir esse novo modo de exibição como padrão**.</span><span class="sxs-lookup"><span data-stu-id="01242-119">This view is the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![Exibição de biblioteca](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="01242-121">Selecione **Adicionar** para aplicar o modelo à biblioteca.</span><span class="sxs-lookup"><span data-stu-id="01242-121">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="01242-122">Na página inicial do modelo, na seção **Bibliotecas com esse modelo**, você deverá ver a URL do site do SharePoint listado.</span><span class="sxs-lookup"><span data-stu-id="01242-122">On the model home page, in the **Libraries with this model** section, you should see the URL to the SharePoint site listed.</span></span></br>

    ![Biblioteca selecionada](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="01242-124">Vá para a biblioteca de documentos e verifique se você está no modo de exibição de biblioteca de documentos do modelo.</span><span class="sxs-lookup"><span data-stu-id="01242-124">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="01242-125">Observe que, se você selecionar o botão de informações ao lado do nome da biblioteca de documentos, uma mensagem indicará que o modelo foi aplicado à biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="01242-125">Notice that if you select the information button next to the document library name, a message notes that your model has been applied to the document library.</span></span>

    ![Modo de exibição informações](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="01242-127">Depois de aplicar o modelo à biblioteca de documentos, você pode começar a carregar documentos no site e ver os resultados.</span><span class="sxs-lookup"><span data-stu-id="01242-127">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="01242-128">O modelo identifica todos os arquivos com o tipo de conteúdo associado do modelo e os lista em seu modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="01242-128">The model identifies any files with model’s associated content type and lists them in your view.</span></span> <span data-ttu-id="01242-129">Se o modelo tiver os extratores, o modo de exibição exibirá colunas para os dados que você está extraindo de cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="01242-129">If your model has any extractors, the view displays columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="01242-130">Aplicar o modelo aos arquivos que já estão na biblioteca de documentos</span><span class="sxs-lookup"><span data-stu-id="01242-130">Apply the model to files already in the document library</span></span>

<span data-ttu-id="01242-131">Enquanto um modelo aplicado processa todos os arquivos carregados na biblioteca de documentos após a aplicação, você também pode fazer o seguinte para executar o modelo em arquivos que já existem na biblioteca de documentos antes do modelo aplicado:</span><span class="sxs-lookup"><span data-stu-id="01242-131">While an applied model processes all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already exists in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="01242-132">Na biblioteca de documentos, selecione os arquivos que você deseja processar por seu modelo.</span><span class="sxs-lookup"><span data-stu-id="01242-132">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="01242-133">Depois de selecionar seus arquivos, **Classificar e extrair**aparecerá na faixa de opções da biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="01242-133">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="01242-134">Selecione **Classificar e extrair**.</span><span class="sxs-lookup"><span data-stu-id="01242-134">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="01242-135">Os arquivos selecionados serão adicionados à fila a ser processada.</span><span class="sxs-lookup"><span data-stu-id="01242-135">The files you selected will be added to the queue to be processed.</span></span>

      ![Classificar e extrair](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a><span data-ttu-id="01242-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="01242-137">See Also</span></span>
[<span data-ttu-id="01242-138">Criar um classificador</span><span class="sxs-lookup"><span data-stu-id="01242-138">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="01242-139">Criar um extrator</span><span class="sxs-lookup"><span data-stu-id="01242-139">Create an extractor</span></span>](create-an-extractor.md)

<span data-ttu-id="01242-140">[Visão geral sobre Compreensão de Documentos](document-understanding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="01242-140">[Document Understanding overview](document-understanding-overview.md)</span></span>


