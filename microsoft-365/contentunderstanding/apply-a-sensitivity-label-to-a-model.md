---
title: Aplicar um rótulo de confidencialidade a um modelo no Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Este artigo descreve como aplicar um rótulo de confidencialidade a um modelo no SharePoint Syntex.
ms.openlocfilehash: ebcd398799e7c8addd96d5941427628d3db5ad43
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028938"
---
# <a name="apply-a-sensitivity-label-to-a-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="1dcc7-103">Aplicar um rótulo de confidencialidade a um modelo no Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="1dcc7-103">Apply a sensitivity label to a model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="1dcc7-104">Você pode aplicar facilmente um [rótulo de confidencialidade](../compliance/sensitivity-labels.md) a um modelo de compreensão de documentos no Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="1dcc7-104">You can easily apply a [sensitivity label](../compliance/sensitivity-labels.md) to document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="1dcc7-105">Este recurso ainda não está disponível para modelos de processamento de formulário.</span><span class="sxs-lookup"><span data-stu-id="1dcc7-105">This feature isn't available yet for form processing models.</span></span>

<span data-ttu-id="1dcc7-106">Os rótulos de confidencialidade permitem aplicar políticas de criptografia, compartilhamento e acesso condicional aos documentos que seus modelos identificam.</span><span class="sxs-lookup"><span data-stu-id="1dcc7-106">Sensitivity labels let you apply encryption, sharing, and conditional access policies to the documents that your models identify.</span></span> <span data-ttu-id="1dcc7-107">Por exemplo, você deseja que seu modelo não apenas identifique documentos financeiros que contenham números de conta bancária ou números de cartão de crédito carregados em sua biblioteca de documentos, mas também para aplicar um rótulo de confidencialidade de *Criptografia* a eles para restringir quem pode acessar esse conteúdo e como ele pode ser usado.</span><span class="sxs-lookup"><span data-stu-id="1dcc7-107">For example, you want your model to not only identify any financial documents that contain bank account numbers or credit card numbers that are uploaded to your document library, but also to apply an *Encryption* sensitivity label to them to restrict who can access that content and how it can be used.</span></span> <span data-ttu-id="1dcc7-108">Os modelos SharePoint Syntex honram as [regras da etiqueta](../compliance/apply-sensitivity-label-automatically.md?view=o365-worldwide#how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label) e também não sobrescrevem uma etiqueta existente que foi aplicada manualmente por um usuário ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="1dcc7-108">SharePoint Syntex models honor the [label order](../compliance/apply-sensitivity-label-automatically.md?view=o365-worldwide#how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label) rules and also do not overwrite an existing label that was manually applied by a user to the file.</span></span> 

<span data-ttu-id="1dcc7-109">Você pode aplicar um rótulo de confidencialidade pré-existente ao seu modelo por meio das configurações do modelo na página inicial do seu modelo.</span><span class="sxs-lookup"><span data-stu-id="1dcc7-109">You can apply a pre-existing sensitivity label to your model through your model settings on your model's home page.</span></span> <span data-ttu-id="1dcc7-110">O rótulo já deve estar publicado para estar disponível para seleção a partir das configurações de modelo.</span><span class="sxs-lookup"><span data-stu-id="1dcc7-110">The label must already be published to be available for selection from model settings.</span></span>

> [!Important]
> <span data-ttu-id="1dcc7-111">Para que os rótulos de confidencialidade estejam disponíveis para serem aplicados aos seus modelos de compreensão de documentos, eles precisam ser [criados e publicados no Centro de Conformidade do Microsoft 365](../business-video/create-sensitivity-labels.md).</span><span class="sxs-lookup"><span data-stu-id="1dcc7-111">For sensitivity labels to be available to apply to your document understanding models, they need to be [created and published in the Microsoft 365 Compliance Center](../business-video/create-sensitivity-labels.md).</span></span>

## <a name="add-a-sensitivity-label-to-a-document-understanding-model"></a><span data-ttu-id="1dcc7-112">Adicionar um rótulo de confidencialidade a um modelo de compreensão de documentos</span><span class="sxs-lookup"><span data-stu-id="1dcc7-112">Add a sensitivity label to a document understanding model</span></span>

1. <span data-ttu-id="1dcc7-113">Na página inicial do modelo, selecione **Configurações de modelo**.</span><span class="sxs-lookup"><span data-stu-id="1dcc7-113">From the model home page, select **Model settings**.</span></span>

   ![Captura de tela da página Modelos com a opção de configurações de Modelo realçada.](../media/content-understanding/sensitivity-model-settings.png)

2. <span data-ttu-id="1dcc7-115">Em **Configurações de modelo**, na seção **Conformidade**, selecione o menu **Rótulo de confidencialidade** para ver uma lista de rótulos de confidencialidade que estão disponíveis para serem aplicados ao modelo.</span><span class="sxs-lookup"><span data-stu-id="1dcc7-115">On **Model settings** pane, in the **Compliance** section, select the **Sensitivity label** menu to see a list of sensitivity labels that are available for you to apply to the model.</span></span>

   ![Captura de tela do painel Configurações de modelo mostrando o menu de rótulo de confidencialidade.](../media/content-understanding/sensitivity-model-settings-pane.png) 

3. <span data-ttu-id="1dcc7-117">Selecione o rótulo de confidencialidade que você deseja aplicar ao modelo e, em seguida, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1dcc7-117">Select the sensitivity label you want to apply to the model, and then select **Save**.</span></span>

<span data-ttu-id="1dcc7-118">Depois de aplicar o rótulo de confidencialidade ao modelo, você poderá aplicá-lo a:</span><span class="sxs-lookup"><span data-stu-id="1dcc7-118">After you apply the sensitivity label to your model, you can apply it to a:</span></span>

- <span data-ttu-id="1dcc7-119">Nova biblioteca de documentos</span><span class="sxs-lookup"><span data-stu-id="1dcc7-119">New document library</span></span>
- <span data-ttu-id="1dcc7-120">Biblioteca de documentos para a qual o modelo já foi aplicado</span><span class="sxs-lookup"><span data-stu-id="1dcc7-120">Document library to which the model is already applied</span></span>
 
### <a name="apply-the-sensitivity-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="1dcc7-121">Aplicar o rótulo de confidencialidade a uma biblioteca de documentos para a qual o modelo já foi aplicado</span><span class="sxs-lookup"><span data-stu-id="1dcc7-121">Apply the sensitivity label to a document library to which the model is already applied</span></span>

<span data-ttu-id="1dcc7-122">Se seu modelo de compreensão de documentos já foi aplicado a uma biblioteca de documentos, você pode fazer o seguinte para sincronizar sua atualização de rótulo de confidencialidade para aplicá-la à biblioteca de documentos:</span><span class="sxs-lookup"><span data-stu-id="1dcc7-122">If your document understanding model has already been applied to a document library, you can do the following to sync your sensitivity label update to apply it to the document library:</span></span>

1. <span data-ttu-id="1dcc7-123">Na página inicial do seu modelo, na seção **Bibliotecas com esse modelo**, selecione a biblioteca de documentos à qual você deseja aplicar a atualização de rótulo de confidencialidade.</span><span class="sxs-lookup"><span data-stu-id="1dcc7-123">On the model home page, in the **Libraries with this model** section, select the document library to which you want to apply the sensitivity label update.</span></span>

2. <span data-ttu-id="1dcc7-124">Selecione **Sincronizar**.</span><span class="sxs-lookup"><span data-stu-id="1dcc7-124">Select **Sync**.</span></span>

   ![Captura de tela mostrando Bibliotecas com esta seção de modelo com a Sincronização realçada.](../media/content-understanding/sensitivity-libraries-sync.png)

<span data-ttu-id="1dcc7-126">Depois de aplicar a atualização e sincronizá-la com o seu modelo, você pode confirmar se ela foi aplicada da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="1dcc7-126">After you apply the update and sync it to your model, you can confirm that it has been applied by doing the following steps:</span></span>

1. <span data-ttu-id="1dcc7-127">No centro de conteúdo, na seção **Bibliotecas com esse modelo**, clique na biblioteca à qual o modelo atualizado foi aplicado.</span><span class="sxs-lookup"><span data-stu-id="1dcc7-127">In the content center, in the **Libraries with this model** section, select the library to which your updated model was applied.</span></span> 

2. <span data-ttu-id="1dcc7-128">No modo de exibição da biblioteca de documentos, selecione o ícone de informações para verificar as propriedades do modelo.</span><span class="sxs-lookup"><span data-stu-id="1dcc7-128">In your document library view, select the information icon to check the model properties.</span></span>

3. <span data-ttu-id="1dcc7-129">Na lista **Modelos ativos**, selecione o modelo atualizado.</span><span class="sxs-lookup"><span data-stu-id="1dcc7-129">In the **Active models** list, select your updated model.</span></span>

4. <span data-ttu-id="1dcc7-130">Na seção **Rótulo de confidencialidade**, você verá o nome do rótulo de confidencialidade aplicado.</span><span class="sxs-lookup"><span data-stu-id="1dcc7-130">In the **Sensitivity label** section, you'll see the name of the applied sensitivity label.</span></span>

<span data-ttu-id="1dcc7-131">Na página de exibição do seu modelo na biblioteca de documentos, uma nova coluna do **Rótulo de confidencialidade** será exibida.</span><span class="sxs-lookup"><span data-stu-id="1dcc7-131">On your model's view page in your document library, a new **Sensitivity label** column will display.</span></span> <span data-ttu-id="1dcc7-132">Conforme seu modelo classifica os arquivos, eles os identifica como pertencentes ao seu tipo de conteúdo e os lista no modo de exibição de biblioteca, a coluna **Rótulo de confidencialidade** também exibirá o nome do rótulo de confidencialidade que foi aplicado a ela por meio do modelo.</span><span class="sxs-lookup"><span data-stu-id="1dcc7-132">As your model classifies files it identifies as belonging to its content type and lists them in the library view, the **Sensitivity label** column will also display the name of the sensitivity label that has been applied to it through the model.</span></span>

<span data-ttu-id="1dcc7-133">Por exemplo, todos os documentos financeiros que seu modelo identificar também terão o rótulo de confidencialidade *Criptografia* aplicado a eles, impedindo que eles sejam acessados por pessoas não autorizadas.</span><span class="sxs-lookup"><span data-stu-id="1dcc7-133">For example, all financial documents that your model identifies also will have the *Encryption* sensitivity label applied to them, preventing them from being accessed by unauthorized people.</span></span> <span data-ttu-id="1dcc7-134">Se uma tentativa for realizada para acessar o arquivo na biblioteca de documentos por uma pessoa não autorizada, um erro será exibido informando que ela não tem permissão devido ao rótulo de confidencialidade aplicado.</span><span class="sxs-lookup"><span data-stu-id="1dcc7-134">If an attempt is made to access the file from the document library by an unauthorized person, an error will display saying it isn't allowed because of the applied sensitivity label.</span></span>

<!---
## Add a sensitivity label to a form processing model

> [!Important]
> For sensitivity labels to be available to apply to your form processing model, they need to be [created and published in the Microsoft 365 Compliance Center](../business-video/create-sensitivity-labels.md).

You can either apply a sensitivity label to a form processing model when you are creating a model, or apply it to an existing model.

### Add a sensitivity label when you create a form processing model

1. When you [create a new form processing model](create-a-form-processing-model.md), select **Advanced settings**.

2. In **Advanced settings**, in the **Sensitivity label** section, select the menu and then select the sensitivity label you want to apply to the model.

3.  After you've completed your remaining model settings, select **Create** to build your model.

### Add a sensitivity label to an existing form processing model

You can add a sensitivity label to an existing form processing model in different ways:

- Through the **Automate** menu in the document library
- Through the **Active model** settings in the document library 

#### Add a sensitivity label to an existing form processing model through the Automate menu

You can add a sensitivity label to an existing form processing model that you own through the **Automate** menu in the document library in which the model is applied.

1. In your document library to which the form processing model is applied, select the **Automate** menu, select **AI Builder**, and then select **View form processing model details**.

2. On the **Model details** pane, in the **Sensitivity label** section, select the sensitivity label you want to apply. Then select **Save**.

#### Add a sensitivity label to an existing form processing model in the active model settings

You can add a sensitivity label to an existing form processing model that you own through the **Active model** settings in the document library in which the model is applied.

1. In the SharePoint document library in which the model is applied, select the **View active models** icon, and then select **View active models**.

2. In **Active models**, select the form processing model to which you want to apply the sensitivity label.

3. On the **Model details** pane, in the **Sensitivity label** section, select the sensitivity label you want to apply. Then select **Save**.

   > [!NOTE]
   > You must be the model owner for the **Model settings** pane to be editable. 
--->

## <a name="see-also"></a><span data-ttu-id="1dcc7-135">Confira também</span><span class="sxs-lookup"><span data-stu-id="1dcc7-135">See also</span></span>

[<span data-ttu-id="1dcc7-136">Aplicar um rótulo de retenção</span><span class="sxs-lookup"><span data-stu-id="1dcc7-136">Apply a retention label</span></span>](apply-a-retention-label-to-a-model.md)

[<span data-ttu-id="1dcc7-137">Criar um classificador</span><span class="sxs-lookup"><span data-stu-id="1dcc7-137">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="1dcc7-138">Criar um extrator</span><span class="sxs-lookup"><span data-stu-id="1dcc7-138">Create an extractor</span></span>](create-an-extractor.md)

<span data-ttu-id="1dcc7-139">[Visão geral sobre Compreensão de Documentos](document-understanding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1dcc7-139">[Document Understanding overview](document-understanding-overview.md)</span></span>
