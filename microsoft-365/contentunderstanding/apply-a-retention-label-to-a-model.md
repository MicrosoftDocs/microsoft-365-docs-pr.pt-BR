---
title: Aplicar um rótulo de retenção a um documento entendendo o modelo
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Este artigo descreve como aplicar um rótulo de retenção a um documento entendendo o modelo
ms.openlocfilehash: 26ad64906c0e2a311d8b244e8e1596a8b975cc15
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294909"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="6d5e1-103">Aplicar um rótulo de retenção a um documento entendendo o modelo</span><span class="sxs-lookup"><span data-stu-id="6d5e1-103">Apply a retention label to a document understanding model</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="6d5e1-104">Você pode facilmente aplicar um [rótulo de retenção](https://docs.microsoft.com/microsoft-365/compliance/retention) a um documento entendendo o modelo no Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="6d5e1-104">You can easily apply a [retention label](https://docs.microsoft.com/microsoft-365/compliance/retention) to a document understanding model in Microsoft SharePoint Syntex.</span></span>

<span data-ttu-id="6d5e1-105">Os rótulos de retenção permitem que você aplique as configurações de retenção aos documentos que o documento entende modelos Identify.</span><span class="sxs-lookup"><span data-stu-id="6d5e1-105">Retention labels let you apply retention settings to the documents that your document understanding models identify.</span></span>  <span data-ttu-id="6d5e1-106">Por exemplo, você deseja que seu modelo não apenas identifique os documentos de *aviso de seguros* que são carregados para sua biblioteca de documentos, mas também para aplicar uma marca de retenção de *negócios* a eles, para que esses documentos não possam ser excluídos da biblioteca de documentos para o período de tempo especificado (os próximos cinco meses, por exemplo).</span><span class="sxs-lookup"><span data-stu-id="6d5e1-106">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="6d5e1-107">Você pode aplicar um rótulo de retenção pré-existente ao documento entendendo o modelo por meio de suas configurações de modelo na home page do seu modelo.</span><span class="sxs-lookup"><span data-stu-id="6d5e1-107">You can apply a pre-existing retention label to your document understanding model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="6d5e1-108">Para que os rótulos de retenção estejam disponíveis para aplicar ao modelo de compreensão do conteúdo, eles precisam ser [criados e publicados no centro de conformidade da Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="6d5e1-108">For retention labels to be available to apply to your content understanding model, they need to be [created and published in the Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="6d5e1-109">Para adicionar um rótulo de retenção a um documento entendendo o modelo</span><span class="sxs-lookup"><span data-stu-id="6d5e1-109">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="6d5e1-110">Na página inicial do modelo, selecione **configurações de modelo**.</span><span class="sxs-lookup"><span data-stu-id="6d5e1-110">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="6d5e1-111">Em **configurações de modelo**, na seção **segurança e conformidade** , selecione o menu **rótulo de retenção** para ver uma lista de rótulos de retenção que estão disponíveis para seu para se aplicar ao modelo.</span><span class="sxs-lookup"><span data-stu-id="6d5e1-111">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="6d5e1-112">![Menu rótulo de retenção](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="6d5e1-112">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="6d5e1-113">Selecione o rótulo de retenção que você deseja aplicar ao modelo e, em seguida, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="6d5e1-113">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="6d5e1-114">Depois de aplicar o rótulo de retenção ao modelo, você poderá aplicá-lo a:</span><span class="sxs-lookup"><span data-stu-id="6d5e1-114">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="6d5e1-115">Nova biblioteca de documentos</span><span class="sxs-lookup"><span data-stu-id="6d5e1-115">New document library</span></span>
- <span data-ttu-id="6d5e1-116">Biblioteca de documentos para a qual o modelo já está aplicado</span><span class="sxs-lookup"><span data-stu-id="6d5e1-116">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="6d5e1-117">Aplicar o rótulo de retenção a uma biblioteca de documentos à qual o modelo já está aplicado</span><span class="sxs-lookup"><span data-stu-id="6d5e1-117">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="6d5e1-118">Se o documento que entende o modelo já tiver sido aplicado a uma biblioteca de documentos, você poderá fazer o seguinte para sincronizar sua atualização de etiqueta de retenção para aplicá-la à biblioteca de documentos:</span><span class="sxs-lookup"><span data-stu-id="6d5e1-118">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="6d5e1-119">Na home page do modelo, na seção **bibliotecas com este modelo** , selecione a biblioteca de documentos à qual você deseja aplicar a atualização do rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="6d5e1-119">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="6d5e1-120">Selecione **sincronizar**.</span><span class="sxs-lookup"><span data-stu-id="6d5e1-120">Select **Sync**.</span></span> </br>
 <span data-ttu-id="6d5e1-121">![Modelo de sincronização](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="6d5e1-121">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="6d5e1-122">Depois de aplicar a atualização e sincronizá-la ao seu modelo, você pode confirmar se ela foi aplicada fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6d5e1-122">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="6d5e1-123">No centro de conteúdo, na seção **bibliotecas com este modelo** , clique na biblioteca à qual o modelo atualizado foi aplicado.</span><span class="sxs-lookup"><span data-stu-id="6d5e1-123">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="6d5e1-124">No modo de exibição de biblioteca de documentos, selecione o ícone de informações para verificar as propriedades do modelo.</span><span class="sxs-lookup"><span data-stu-id="6d5e1-124">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="6d5e1-125">Na lista de **modelos ativos** , selecione o modelo atualizado.</span><span class="sxs-lookup"><span data-stu-id="6d5e1-125">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="6d5e1-126">Na seção **rótulo de retenção** , você verá o nome do rótulo de retenção aplicado.</span><span class="sxs-lookup"><span data-stu-id="6d5e1-126">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="6d5e1-127">Na página de exibição do seu modelo na biblioteca de documentos, uma nova coluna de **rótulo de retenção** será exibida.</span><span class="sxs-lookup"><span data-stu-id="6d5e1-127">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="6d5e1-128">À medida que o modelo classifica arquivos que ele identifica como pertencente ao tipo de conteúdo e o lista no modo de exibição de biblioteca, a coluna rótulo de retenção também exibirá o nome do rótulo de retenção que foi aplicado a ele por meio do modelo.</span><span class="sxs-lookup"><span data-stu-id="6d5e1-128">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="6d5e1-129">Por exemplo, todos os documentos de *aviso de seguro* que seu modelo identifica também terão o rótulo de retenção de *negócios* aplicado a eles, impedindo que eles sejam excluídos da biblioteca de documentos por cinco meses.</span><span class="sxs-lookup"><span data-stu-id="6d5e1-129">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="6d5e1-130">Se for feita uma tentativa de excluir o arquivo da biblioteca de documentos, um erro será exibido dizendo que não é permitido por causa do rótulo de retenção aplicado.</span><span class="sxs-lookup"><span data-stu-id="6d5e1-130">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d5e1-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="6d5e1-131">See Also</span></span>
[<span data-ttu-id="6d5e1-132">Criar um classificador</span><span class="sxs-lookup"><span data-stu-id="6d5e1-132">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="6d5e1-133">Criar um extrator</span><span class="sxs-lookup"><span data-stu-id="6d5e1-133">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="6d5e1-134">Visão geral da compreensão do documento</span><span class="sxs-lookup"><span data-stu-id="6d5e1-134">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="6d5e1-135">Criar um modelo de processamento de formulários</span><span class="sxs-lookup"><span data-stu-id="6d5e1-135">Create a form processing model</span></span>](create-a-form-processing-model.md)  
