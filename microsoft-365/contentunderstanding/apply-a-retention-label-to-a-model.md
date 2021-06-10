---
title: Aplicar um rótulo de retenção a um modelo
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
description: Este artigo descreve como aplicar um rótulo de retenção a um modelo no SharePoint Syntex
ms.openlocfilehash: 00a8d255b3274af3cd96527e0dcd2ae2644226ac
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861606"
---
# <a name="apply-a-retention-label-to-a-model-in-sharepoint-syntex"></a><span data-ttu-id="2ee5f-103">Aplicar um rótulo de retenção a um modelo no SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="2ee5f-103">Apply a retention label to a model in SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


<span data-ttu-id="2ee5f-104">Você pode facilmente aplicar um [rótulo de retenção](../compliance/retention.md) a um modelo no Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="2ee5f-104">You can easily apply a [retention label](../compliance/retention.md) to a model in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="2ee5f-105">Você pode fazer isso para a compreensão de documentos e modelos de processamento de formulários.</span><span class="sxs-lookup"><span data-stu-id="2ee5f-105">You can do this for both document understanding and form processing models.</span></span>

<span data-ttu-id="2ee5f-106">Rótulos de retenção permitem que você aplique configurações de retenção aos documentos que seus modelos identificam.</span><span class="sxs-lookup"><span data-stu-id="2ee5f-106">Retention labels let you apply retention settings to the documents that your models identify.</span></span>  <span data-ttu-id="2ee5f-107">Por exemplo, você deseja que o seu modelo não só identifique todos os documentos de *Aviso de seguro* que são carregados na biblioteca de documentos, mas também aplique uma marca de retenção de *Negócios* a eles para que esses documentos não possam ser excluídos da biblioteca de documentos no período de tempo especificado (os próximos cinco meses, por exemplo).</span><span class="sxs-lookup"><span data-stu-id="2ee5f-107">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="2ee5f-108">Você pode aplicar um rótulo de retenção pré-existente ao seu modelo por meio das configurações do modelo na página inicial do seu modelo.</span><span class="sxs-lookup"><span data-stu-id="2ee5f-108">You can apply a pre-existing retention label to your model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="2ee5f-109">Para que os rótulos de retenção estejam disponíveis para serem aplicados aos seus modelos de compreensão de documentos, eles precisam ser [criados e publicados no Centro de Conformidade do Microsoft 365](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="2ee5f-109">For retention labels to be available to apply to your document understanding models, they need to be [created and published in the Microsoft 365 Compliance Center](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="2ee5f-110">Para adicionar um rótulo de retenção a um modelo de compreensão de documentos</span><span class="sxs-lookup"><span data-stu-id="2ee5f-110">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="2ee5f-111">Na página inicial do modelo, selecione **Configurações de modelo**.</span><span class="sxs-lookup"><span data-stu-id="2ee5f-111">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="2ee5f-112">Em **Configurações de modelo**, na seção **Segurança e conformidade**, selecione o menu **Rótulo de retenção** para ver uma lista de rótulos de retenção que estão disponíveis para serem aplicados ao modelo.</span><span class="sxs-lookup"><span data-stu-id="2ee5f-112">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="2ee5f-113">![Menu rótulo de retenção](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="2ee5f-113">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="2ee5f-114">Selecione o rótulo de retenção que você deseja aplicar ao modulo e, em seguida, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2ee5f-114">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="2ee5f-115">Depois de aplicar o rótulo de retenção ao seu modelo, você pode aplicá-lo a:</span><span class="sxs-lookup"><span data-stu-id="2ee5f-115">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="2ee5f-116">Nova biblioteca de documentos</span><span class="sxs-lookup"><span data-stu-id="2ee5f-116">New document library</span></span>
- <span data-ttu-id="2ee5f-117">Biblioteca de documentos para a qual o modelo já foi aplicado</span><span class="sxs-lookup"><span data-stu-id="2ee5f-117">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="2ee5f-118">Aplicar o rótulo de retenção a uma biblioteca de documentos para a qual o modelo já foi aplicado</span><span class="sxs-lookup"><span data-stu-id="2ee5f-118">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="2ee5f-119">Se seu modelo de compreensão de documentos já foi aplicado a uma biblioteca de documentos, você pode fazer o seguinte para sincronizar sua atualização de rótulo de retenção para aplicá-la à biblioteca de documentos:</span><span class="sxs-lookup"><span data-stu-id="2ee5f-119">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="2ee5f-120">Na página inicial do seu modelo, na seção **Bibliotecas com esse modelo**, selecione a biblioteca de documentos à qual você deseja aplicar a atualização de rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="2ee5f-120">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="2ee5f-121">Selecione **Sincronizar**.</span><span class="sxs-lookup"><span data-stu-id="2ee5f-121">Select **Sync**.</span></span> </br>
 <span data-ttu-id="2ee5f-122">![Modelo de sincronização](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="2ee5f-122">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="2ee5f-123">Depois de aplicar a atualização e sincronizá-la com o seu modelo, você pode confirmar se ela foi aplicada da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="2ee5f-123">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="2ee5f-124">No centro de conteúdo, na seção **Bibliotecas com esse modelo**, clique na biblioteca à qual o modelo atualizado foi aplicado.</span><span class="sxs-lookup"><span data-stu-id="2ee5f-124">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="2ee5f-125">No modo de exibição da biblioteca de documentos, selecione o ícone de informações para verificar as propriedades do modelo.</span><span class="sxs-lookup"><span data-stu-id="2ee5f-125">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="2ee5f-126">Na lista **Modelos ativos**, selecione o modelo atualizado.</span><span class="sxs-lookup"><span data-stu-id="2ee5f-126">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="2ee5f-127">Na seção **Rótulo de retenção**, você verá o nome do rótulo de retenção aplicado.</span><span class="sxs-lookup"><span data-stu-id="2ee5f-127">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="2ee5f-128">Na página de exibição do seu modelo na biblioteca de documentos, uma nova coluna do **Rótulo de retenção** será exibida.</span><span class="sxs-lookup"><span data-stu-id="2ee5f-128">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="2ee5f-129">Conforme seu modelo classifica os arquivos, eles os identifica como pertencentes ao seu tipo de conteúdo e os lista no modo de exibição de biblioteca, a coluna rótulo de retenção também exibirá o nome do rótulo de retenção que foi aplicado a ela por meio do modelo.</span><span class="sxs-lookup"><span data-stu-id="2ee5f-129">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="2ee5f-130">Por exemplo, todos os documentos de *Aviso de seguro* identificados pelo seu modelo também têm o rótulo de retenção *Negócios* aplicado a eles, impedindo que eles sejam excluídos da biblioteca de documentos por cinco meses.</span><span class="sxs-lookup"><span data-stu-id="2ee5f-130">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="2ee5f-131">Se você tentar excluir o arquivo da biblioteca de documentos, o programa exibirá um erro informando que isso não é permitido por causa do rótulo de retenção aplicado.</span><span class="sxs-lookup"><span data-stu-id="2ee5f-131">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="to-add-a-retention-label-to-a-form-processing-model"></a><span data-ttu-id="2ee5f-132">Para adicionar um rótulo de retenção a um modelo de processamento de formulário</span><span class="sxs-lookup"><span data-stu-id="2ee5f-132">To add a retention label to a form processing model</span></span>

> [!Important]
> <span data-ttu-id="2ee5f-133">Para que os rótulos de retenção estejam disponíveis para serem aplicados ao seu modelo de processamento de formulário, eles precisam ser [criados e publicados no Centro de Conformidade do Microsoft 365](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="2ee5f-133">For retention labels to be available to apply to your form processing model, they need to be [created and published in the Microsoft 365 Compliance Center](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).</span></span>

<span data-ttu-id="2ee5f-134">Você pode aplicar um rótulo de retenção a um modelo de processamento de formulário ao criar um modelo ou aplicá-lo a um modelo existente.</span><span class="sxs-lookup"><span data-stu-id="2ee5f-134">You can either apply a retention label to a form processing model when you are creating a model, or apply it to an existing model.</span></span>

### <a name="to-add-a-retention-label-when-you-create-a-form-processing-model"></a><span data-ttu-id="2ee5f-135">Para adicionar um rótulo de retenção ao criar um modelo de processamento de formulário</span><span class="sxs-lookup"><span data-stu-id="2ee5f-135">To add a retention label when you create a form processing model</span></span>

1. <span data-ttu-id="2ee5f-136">Quando você estiver [criando um novo modelo de processamento de formulário](./create-a-form-processing-model.md), selecione <b>Configurações avançadas.</b></span><span class="sxs-lookup"><span data-stu-id="2ee5f-136">When you are [creating a new form processing model](./create-a-form-processing-model.md), select <b>Advanced settings.</b></span></span>
2. <span data-ttu-id="2ee5f-137">Em <b>Configurações avançadas</b>, na seção <b>Rótulo de retenção</b>, selecione o menu e selecione o rótulo de retenção que deseja aplicar ao modelo.</b></span><span class="sxs-lookup"><span data-stu-id="2ee5f-137">In <b>Advanced settings</b>, in the <b>Retention label</b> section, select the menu and then select the retention label you want to apply to the model.</b></span></span>

 
     ![Adicionar a um novo modelo de processamento de formulário](../media/content-understanding/retention-label-forms.png)</br>

3.  <span data-ttu-id="2ee5f-139">Depois de concluir as configurações restantes do modelo, selecione <b>Criar</b> para construir o seu modelo.</span><span class="sxs-lookup"><span data-stu-id="2ee5f-139">After you've completed your remaining model settings, select <b>Create</b> to build your model.</span></span>

### <a name="to-add-a-retention-label-to-an-existing-form-processing-model"></a><span data-ttu-id="2ee5f-140">Para adicionar um rótulo de retenção a um modelo de processamento de formulário existente</span><span class="sxs-lookup"><span data-stu-id="2ee5f-140">To add a retention label to an existing form processing model</span></span>

<span data-ttu-id="2ee5f-141">Você pode adicionar um rótulo de retenção a um modelo de processamento de formulário existente de diferentes maneiras:</span><span class="sxs-lookup"><span data-stu-id="2ee5f-141">You can add a retention label to an existing form processing model in different ways:</span></span>
- <span data-ttu-id="2ee5f-142">Por meio do menu Automatizar na biblioteca de documentos</span><span class="sxs-lookup"><span data-stu-id="2ee5f-142">Through the Automate menu in the document library</span></span>
- <span data-ttu-id="2ee5f-143">Por meio das configurações do modelo Ativo na biblioteca de documentos</span><span class="sxs-lookup"><span data-stu-id="2ee5f-143">Through the Active model settings in the document library</span></span> 


#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-through-the-automate-menu"></a><span data-ttu-id="2ee5f-144">Para adicionar um rótulo de retenção a um modelo de processamento de formulário existente através do menu Automatizar</span><span class="sxs-lookup"><span data-stu-id="2ee5f-144">To add a retention label to an existing form processing model through the Automate menu</span></span>

<span data-ttu-id="2ee5f-145">Você pode adicionar um rótulo de retenção a um modelo de processamento de formulário existente de sua propriedade por meio do menu Automatizar na biblioteca de documentos em que o modelo é aplicado.</span><span class="sxs-lookup"><span data-stu-id="2ee5f-145">You can add a retention label to an existing form processing model that you own through the Automate menu in the document library in which the model is applied.</span></span>


1. <span data-ttu-id="2ee5f-146">Em sua biblioteca de documentos à qual o modelo de processamento de formulário é aplicado, selecione o menu <b>Automatizar</b>, selecione <b>Construtor AI</b> e selecione <b>Exibir detalhes do modelo de processamento de formulário</b>.</span><span class="sxs-lookup"><span data-stu-id="2ee5f-146">In your document library to which the form processing model is applied, select the <b>Automate</b> menu, select <b>AI Builder</b>, then select <b>View form processing model details</b>.</span></span>

   ![Menu automatizar](../media/content-understanding/automate-menu.png)</br>

2. <span data-ttu-id="2ee5f-148">Nos detalhes do modelo, na seção <b>Rótulo de Retenção</b>, selecione o rótulo de retenção que deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="2ee5f-148">In the model details, in the <b>Retention Label</b> section, select the retention label you want to apply.</span></span>  <span data-ttu-id="2ee5f-149">Em seguida, selecione <b>Salvar</b>.</span><span class="sxs-lookup"><span data-stu-id="2ee5f-149">Then select <b>Save</b>.</span></span>

     ![Adicionar a um modelo de processamento de formulário existente](../media/content-understanding/retention-label-model-details.png)</br> 

#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-in-the-active-model-settings"></a><span data-ttu-id="2ee5f-151">Para adicionar um rótulo de retenção a um modelo de processamento de formulário existente nas configurações do modelo ativo</span><span class="sxs-lookup"><span data-stu-id="2ee5f-151">To add a retention label to an existing form processing model in the active model settings</span></span>

<span data-ttu-id="2ee5f-152">Você pode adicionar um rótulo de retenção a um modelo de processamento de formulário existente de sua propriedade por meio das configurações do modelo Ativo na biblioteca de documentos em que o modelo é aplicado.</span><span class="sxs-lookup"><span data-stu-id="2ee5f-152">You can add a retention label to an existing form processing model that you own through the Active model settings in the document library in which the model is applied.</span></span>

1. <span data-ttu-id="2ee5f-153">Na biblioteca de documentos do SharePoint em que o modelo é aplicado, selecione o ícone <b>Exibir modelos ativos</b> e selecione <b>Exibir modelos ativos</b> </b></span><span class="sxs-lookup"><span data-stu-id="2ee5f-153">In the SharePoint document library in which the model is applied, select the <b>View active models</b> icon, and then select <b>View active models</b>.</b></span></span>

   ![Ver modelos ativos](../media/content-understanding/info-du.png)</br> 

2. <span data-ttu-id="2ee5f-155">Em <b>Modelos ativos</b>, selecione o modelo de processamento de formulário para o qual deseja aplicar o rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="2ee5f-155">In <b>Active models</b>, select the form processing model to which you want to apply the retention label.</span></span>

     ![Detalhes do modelo](../media/content-understanding/retention-label-model-details.png)</br> 


3. <span data-ttu-id="2ee5f-157">Nos detalhes do modelo, na seção <b>Rótulo de Retenção</b>, selecione o rótulo de retenção que deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="2ee5f-157">In the model details, in the <b>Retention Label</b> section, select the retention label you want to apply.</span></span>  <span data-ttu-id="2ee5f-158">Em seguida, selecione <b>Salvar</b>.</span><span class="sxs-lookup"><span data-stu-id="2ee5f-158">Then select <b>Save</b>.</span></span>

> [!NOTE]
> <span data-ttu-id="2ee5f-159">Você deve ser o proprietário do modelo para que o painel de configurações do modelo seja editável.</span><span class="sxs-lookup"><span data-stu-id="2ee5f-159">You must be the model owner for the model settings pane to be editable.</span></span> 


## <a name="see-also"></a><span data-ttu-id="2ee5f-160">Confira também</span><span class="sxs-lookup"><span data-stu-id="2ee5f-160">See Also</span></span>
[<span data-ttu-id="2ee5f-161">Criar um classificador</span><span class="sxs-lookup"><span data-stu-id="2ee5f-161">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="2ee5f-162">Criar um extrator</span><span class="sxs-lookup"><span data-stu-id="2ee5f-162">Create an extractor</span></span>](create-an-extractor.md)

<span data-ttu-id="2ee5f-163">[Visão geral sobre Compreensão de Documentos](document-understanding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2ee5f-163">[Document Understanding overview](document-understanding-overview.md)</span></span>
