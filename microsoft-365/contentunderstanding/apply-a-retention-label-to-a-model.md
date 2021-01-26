---
title: Aplicar um rótulo de retenção a um modelo de compreensão de documentos
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
description: Este artigo discute a aplicação de um rótulo de retenção a um modelo de compreensão de documentos
ms.openlocfilehash: 6dcd81b580b7bf0801641bbd019e1b99ecfe7338
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976550"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="13179-103">Aplicar um rótulo de retenção a um modelo de compreensão de documentos</span><span class="sxs-lookup"><span data-stu-id="13179-103">Apply a retention label to a document understanding model</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


<span data-ttu-id="13179-104">Você pode aplicar facilmente um [rótulo de retenção](https://docs.microsoft.com/microsoft-365/compliance/retention) a um modelo de compreensão de documentos no Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="13179-104">You can easily apply a [retention label](https://docs.microsoft.com/microsoft-365/compliance/retention) to a document understanding model in Microsoft SharePoint Syntex.</span></span>

<span data-ttu-id="13179-105">Os rótulos de retenção permitem aplicar as configurações de retenção aos documentos que o modelo de compreensão de documentos identifica.</span><span class="sxs-lookup"><span data-stu-id="13179-105">Retention labels let you apply retention settings to the documents that your document understanding models identify.</span></span>  <span data-ttu-id="13179-106">Por exemplo, você deseja que o seu modelo não só identifique todos os documentos de *Aviso de seguro* que são carregados na biblioteca de documentos, mas também aplique uma marca de retenção de *Negócios* a eles para que esses documentos não possam ser excluídos da biblioteca de documentos no período de tempo especificado (os próximos cinco meses, por exemplo).</span><span class="sxs-lookup"><span data-stu-id="13179-106">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="13179-107">Você pode aplicar um rótulo de retenção preexistente ao seu modelo de compreensão de documentos por meio das configurações de modelo na página inicial do seu modelo.</span><span class="sxs-lookup"><span data-stu-id="13179-107">You can apply a pre-existing retention label to your document understanding model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="13179-108">Para que os rótulos de retenção estejam disponíveis para se aplicar ao seu modelo de compreensão de conteúdo, eles precisam ser [criados e publicados no Centro de Conformidade do Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="13179-108">For retention labels to be available to apply to your content understanding model, they need to be [created and published in the Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="13179-109">Para adicionar um rótulo de retenção a um modelo de compreensão de documentos</span><span class="sxs-lookup"><span data-stu-id="13179-109">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="13179-110">Na página inicial do modelo, selecione **Configurações de modelo**.</span><span class="sxs-lookup"><span data-stu-id="13179-110">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="13179-111">Em **Configurações de modelo**, na seção **Segurança e conformidade**, selecione o menu **Rótulo de retenção** para ver uma lista de rótulos de retenção que estão disponíveis para serem aplicados ao modelo.</span><span class="sxs-lookup"><span data-stu-id="13179-111">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="13179-112">![Menu rótulo de retenção](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="13179-112">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="13179-113">Selecione o rótulo de retenção que você deseja aplicar ao modulo e, em seguida, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="13179-113">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="13179-114">Depois de aplicar o rótulo de retenção ao seu modelo, você pode aplicá-lo a:</span><span class="sxs-lookup"><span data-stu-id="13179-114">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="13179-115">Nova biblioteca de documentos</span><span class="sxs-lookup"><span data-stu-id="13179-115">New document library</span></span>
- <span data-ttu-id="13179-116">Biblioteca de documentos para a qual o modelo já foi aplicado</span><span class="sxs-lookup"><span data-stu-id="13179-116">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="13179-117">Aplicar o rótulo de retenção a uma biblioteca de documentos para a qual o modelo já foi aplicado</span><span class="sxs-lookup"><span data-stu-id="13179-117">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="13179-118">Se seu modelo de compreensão de documentos já foi aplicado a uma biblioteca de documentos, você pode fazer o seguinte para sincronizar sua atualização de rótulo de retenção para aplicá-la à biblioteca de documentos:</span><span class="sxs-lookup"><span data-stu-id="13179-118">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="13179-119">Na página inicial do seu modelo, na seção **Bibliotecas com esse modelo**, selecione a biblioteca de documentos à qual você deseja aplicar a atualização de rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="13179-119">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="13179-120">Selecione **Sincronizar**.</span><span class="sxs-lookup"><span data-stu-id="13179-120">Select **Sync**.</span></span> </br>
 <span data-ttu-id="13179-121">![Modelo de sincronização](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="13179-121">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="13179-122">Depois de aplicar a atualização e sincronizá-la com o seu modelo, você pode confirmar se ela foi aplicada da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="13179-122">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="13179-123">No centro de conteúdo, na seção **Bibliotecas com esse modelo**, clique na biblioteca à qual o modelo atualizado foi aplicado.</span><span class="sxs-lookup"><span data-stu-id="13179-123">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="13179-124">No modo de exibição da biblioteca de documentos, selecione o ícone de informações para verificar as propriedades do modelo.</span><span class="sxs-lookup"><span data-stu-id="13179-124">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="13179-125">Na lista **Modelos ativos**, selecione o modelo atualizado.</span><span class="sxs-lookup"><span data-stu-id="13179-125">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="13179-126">Na seção **Rótulo de retenção**, você verá o nome do rótulo de retenção aplicado.</span><span class="sxs-lookup"><span data-stu-id="13179-126">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="13179-127">Na página de exibição do seu modelo na biblioteca de documentos, uma nova coluna do **Rótulo de retenção** será exibida.</span><span class="sxs-lookup"><span data-stu-id="13179-127">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="13179-128">Conforme seu modelo classifica os arquivos, eles os identifica como pertencentes ao seu tipo de conteúdo e os lista no modo de exibição de biblioteca, a coluna rótulo de retenção também exibirá o nome do rótulo de retenção que foi aplicado a ela por meio do modelo.</span><span class="sxs-lookup"><span data-stu-id="13179-128">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="13179-129">Por exemplo, todos os documentos de *Aviso de seguro* identificados pelo seu modelo também têm o rótulo de retenção *Negócios* aplicado a eles, impedindo que eles sejam excluídos da biblioteca de documentos por cinco meses.</span><span class="sxs-lookup"><span data-stu-id="13179-129">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="13179-130">Se você tentar excluir o arquivo da biblioteca de documentos, o programa exibirá um erro informando que isso não é permitido por causa do rótulo de retenção aplicado.</span><span class="sxs-lookup"><span data-stu-id="13179-130">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="see-also"></a><span data-ttu-id="13179-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="13179-131">See Also</span></span>
[<span data-ttu-id="13179-132">Criar um classificador</span><span class="sxs-lookup"><span data-stu-id="13179-132">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="13179-133">Criar um extrator</span><span class="sxs-lookup"><span data-stu-id="13179-133">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="13179-134">Visão geral da Compreensão de Documentos</span><span class="sxs-lookup"><span data-stu-id="13179-134">Document Understanding overview</span></span>](document-understanding-overview.md)


