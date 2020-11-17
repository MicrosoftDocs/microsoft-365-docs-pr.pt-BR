---
title: Criar um modelo de processamento de formulário
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Crie um modelo de processamento de formulário no Microsoft SharePoint Syntex.
ms.openlocfilehash: aed918d899fe7c5e3c49b733d2411c178e9b98d0
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087686"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="16b03-103">Criar um modelo de processamento de formulário no Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="16b03-103">Create a form processing model in Microsoft SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GnhN]  

</br>

<span data-ttu-id="16b03-104">Usando o [AI Builder](https://docs.microsoft.com/ai-builder/overview), um recurso no Microsoft PowerApps, os usuários do SharePoint Syntex podem criar um [modelo de processamento de formulário](form-processing-overview.md) diretamente de uma biblioteca de documentos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="16b03-104">Using [AI Builder](https://docs.microsoft.com/ai-builder/overview) - a feature in Microsoft PowerApps - SharePoint Syntex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="16b03-105">A criação de um modelo de processamento de formulário envolve o seguinte:</span><span class="sxs-lookup"><span data-stu-id="16b03-105">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="16b03-106">Etapa 1: criar a partir do modelo de processamento para criar o tipo de conteúdo</span><span class="sxs-lookup"><span data-stu-id="16b03-106">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="16b03-107">Etapa 2: Adicionar e analisar arquivos de exemplo</span><span class="sxs-lookup"><span data-stu-id="16b03-107">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="16b03-108">Etapa 3: selecionar os campos de formulário</span><span class="sxs-lookup"><span data-stu-id="16b03-108">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="16b03-109">Etapa 4: treinar e testar o seu modelo</span><span class="sxs-lookup"><span data-stu-id="16b03-109">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="16b03-110">Etapa 5: publicar seu modelo</span><span class="sxs-lookup"><span data-stu-id="16b03-110">Step 5: Publish your model</span></span>
 - <span data-ttu-id="16b03-111">Etapa 6: usar o seu modelo</span><span class="sxs-lookup"><span data-stu-id="16b03-111">Step 6: Use your model</span></span>

## <a name="requirements"></a><span data-ttu-id="16b03-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="16b03-112">Requirements</span></span>

<span data-ttu-id="16b03-p101">Você só pode criar um modelo de processamento de formulário nas bibliotecas de documentos do SharePoint para os quais ele está habilitado. Se o processamento de formulário estiver habilitado, você poderá ver o **AI Builder** **"Criar um modelo de processamento de formulário"** no menu **Automação** na biblioteca de documentos.  Se precisar de processamento habilitado na biblioteca de documentos, você deve contatar o administrador de serviços do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="16b03-p101">You can only create a form processing model in SharePoint document libraries for which it is enabled. If form processing is enabled, you are able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.  If you need processing enabled on your document library, you must contact your SharePoint administrator.</span></span>

 ![Criar um modelo do AI Builder](../media/content-understanding/create-ai-builder-model.png)</br>

## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="16b03-117">Etapa 1: Criar um modelo de processamento de formulário</span><span class="sxs-lookup"><span data-stu-id="16b03-117">Step 1: Create a form processing model</span></span>

<span data-ttu-id="16b03-118">A primeira etapa na criação de um modelo de processamento de formulário é nomeá-lo e, em seguida, criar o novo tipo de conteúdo e criar um novo modo de exibição de biblioteca de documentos para ele.</span><span class="sxs-lookup"><span data-stu-id="16b03-118">The first step in creating a form processing model is to name it and create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="16b03-119">Na biblioteca de documentos, selecione o menu **Automatizar**, selecione **AI Builder** e selecione **Criar um Modelo de Processamento de Formulário**.</span><span class="sxs-lookup"><span data-stu-id="16b03-119">From the document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![Criar um modelo](../media/content-understanding/create-ai-builder-model.png)</br>

2. <span data-ttu-id="16b03-121">No painel **Novo modelo de processamento de formulário**, no campo **Nome**, digite um nome para o seu modelo (por exemplo, *Ordens de Compra*).</span><span class="sxs-lookup"><span data-stu-id="16b03-121">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![Novo modelo de processamento de formulário](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="16b03-p102">Ao criar um modelo de processamento de formulário, você cria um novo tipo de conteúdo do SharePoint. Um tipo de conteúdo do SharePoint representa uma categoria de documentos que tem características comuns e compartilha um conjunto de propriedades de colunas ou metadados para esse conteúdo específico. Os tipos de conteúdo do SharePoint são gerenciados por meio da [Galeria de tipos de conteúdo]().</span><span class="sxs-lookup"><span data-stu-id="16b03-p102">When you create a form processing model, you create a new SharePoint content type. A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content. SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="16b03-126">Selecione **Configurações avançadas** se desejar mapear esse modelo para um tipo de conteúdo existente na Galeria de tipos de conteúdo do SharePoint para usar o esquema.</span><span class="sxs-lookup"><span data-stu-id="16b03-126">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="16b03-p103">Seu modelo cria um novo modo de exibição na biblioteca de documentos para seus dados extraídos. Se você não quiser usar o modo de exibição padrão, desmarque **Definir o modo de exibição como padrão**.</span><span class="sxs-lookup"><span data-stu-id="16b03-p103">Your model creates a new view in your document library for your extracted data. If you do not want it to the default view, deselect **Set the view as default**.</span></span>

5. <span data-ttu-id="16b03-129">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="16b03-129">Select **Create**.</span></span>

## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="16b03-130">Etapa 2: Adicionar e analisar documentos</span><span class="sxs-lookup"><span data-stu-id="16b03-130">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="16b03-p104">Depois de criar seu novo modelo de processamento de formulário, seu navegador abre uma nova página de modelo de processamento de formulários do AI Builder do PowerApps. Nesta página, você pode adicionar e analisar seus documentos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="16b03-p104">After you create your new form processing model, your browser opens a new PowerApps AI Builder forms processing model page. On this page you can add and analyze your example documents.</span></span> </br>

> [!NOTE]
> <span data-ttu-id="16b03-133">Ao procurar os arquivos de exemplo que serão usados, confira as[informações sobre o modelo de processamento de formulário e dicas de otimização](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span><span class="sxs-lookup"><span data-stu-id="16b03-133">When looking for example files to use, see the [form processing model input document requirements and optimization tips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

   ![AI Builder do Power Apps](../media/content-understanding/powerapps.png)</br> 
 
1. <span data-ttu-id="16b03-p105">Selecione **Adicionar documentos** para começar a adicionar documentos de exemplo analisados para determinar os pares de valores nomeados que podem ser extraídos. Em seguida, você pode escolher **Carregar do armazenamento local**, **do SharePoint** ou do **armazenamento de BLOBs do Azure**. Você deve usar pelo menos cinco arquivos para treinamento.</span><span class="sxs-lookup"><span data-stu-id="16b03-p105">Select **Add documents** to begin adding example documents analyzed to determine the named value pairs that can be extracted. You can then choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**. You need to use at least five files for training.</span></span>

2. <span data-ttu-id="16b03-p106">Depois de adicionar arquivos, marque **Analisar** para verificar se há informações comuns a todos os arquivos. Esta ação pode levar vários minutos para ser concluída.</span><span class="sxs-lookup"><span data-stu-id="16b03-p106">After adding files, select **Analyze** to check for any information common is all files. This may take several minutes to complete.</span></span></br> 
 
    ![Analisar arquivos](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="16b03-141">Após a análise dos arquivos, na página **Selecionar os campos de formulário que você deseja salvar**, selecione o arquivo para exibir os campos detectados.</span><span class="sxs-lookup"><span data-stu-id="16b03-141">After the files have been analyzed, in the **Select the form fields you want to save** page select the file to view the detected fields.</span></span></br>

    ![Selecionar campos de formulário](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="16b03-143">Etapa 3: Selecionar os campos de formulário</span><span class="sxs-lookup"><span data-stu-id="16b03-143">Step 3: Select your form fields</span></span>

<span data-ttu-id="16b03-p107">Depois de analisar os documentos dos campos, agora você pode ver os campos encontrados e identificar os que deseja salvar. Os campos salvos são exibidos como colunas no modo de exibição de biblioteca de documentos do modelo e mostram os valores extraídos de cada documento.</span><span class="sxs-lookup"><span data-stu-id="16b03-p107">After analyzing the documents for fields, you can now see the fields that were found, and identify the ones that you want to save. Saved fields display as columns in your model's document library view and show the values extracted from each document.</span></span>

1. <span data-ttu-id="16b03-146">A próxima página exibe um dos seus arquivos de exemplo e realçará todos os campos comuns que foram detectados automaticamente pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="16b03-146">The next page displays one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![Página Selecionar campos](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="16b03-p108">Selecione os campos que você deseja salvar e marque a caixa de seleção para confirmar a seleção. Por exemplo, no modelo de Ordem de Compra, escolha os campos *Data*, *OC* e *Total*. Observe que você também pode optar por renomear um campo.</span><span class="sxs-lookup"><span data-stu-id="16b03-p108">Select the fields that you want to save and select the checkbox to confirm your selection. For example, in the Purchase Order model, choose to select the *Date*, *PO*, and *Total* fields.  Note that you can also choose to rename a field if you choose. </span></span></br>

    ![Selecionar Pedido de Compra#](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="16b03-p109">Se um campo não foi detectado pela análise, ainda será possível adicioná-lo. Realce as informações que você deseja extrair e, na caixa nome, digite o nome desejado. Marque a caixa de seleção. Observe que você precisa confirmar campos não detectados em seus arquivos de exemplo restantes.</span><span class="sxs-lookup"><span data-stu-id="16b03-p109">If a field was not detected by analysis, you can still choose to add it. Highlight the information you want to extract, and in the name box type in the name you want. Then select the check box. Note that you need to confirm undetected fields in your remaining sample files.</span></span>

4. <span data-ttu-id="16b03-156">Clique em **Confirmar campos** depois de selecionar os campos que você deseja salvar.</span><span class="sxs-lookup"><span data-stu-id="16b03-156">Click **Confirm fields** after you have selected the fields that you want to save.</span></span> </br>
 
    ![Confirmar campos após selecionar campos](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="16b03-p110">Na página **Selecionar os campos de formulário que você deseja salvar**, ele mostra o número de campos selecionados. Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="16b03-p110">On the **Select the form fields you want to save** page, it shows the number of fields you have selected. Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="16b03-160">Etapa 4: treinar e testar o seu modelo</span><span class="sxs-lookup"><span data-stu-id="16b03-160">Step 4: Train and test your model</span></span>

<span data-ttu-id="16b03-161">Depois de selecionar os campos que você deseja salvar, a página de **Resumo do modelo** permite treinar e testar o seu modelo.</span><span class="sxs-lookup"><span data-stu-id="16b03-161">After selecting the fields you want to save, the **Model Summary** page lets you train and test your model.</span></span>

1. <span data-ttu-id="16b03-p111">Na página **Resumo de modelo**, os campos salvos serão exibidos na seção **Campos selecionados**. Marque **Treinar** para começar o treinamento em seus arquivos de exemplo. Observe que isso pode levar alguns minutos para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="16b03-p111">On the **Model Summary** page, the saved fields will show in the **Selected fields** section. Select **Train** to begin training on your example files. Note that this may take a few minutes to complete.</span></span></br>

     ![Selecionar campos treinamento](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="16b03-166">Quando vir a notificação de que o treinamento foi concluído, marque **Acessar a página de detalhes**.</span><span class="sxs-lookup"><span data-stu-id="16b03-166">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="16b03-p112">Na página **Detalhes do modelo**, você pode optar por testar como seu modelo funciona selecionando **Teste rápido**. Isso permite arrastar e soltar arquivos para a página e ver se os campos são detectados.</span><span class="sxs-lookup"><span data-stu-id="16b03-p112">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**. This lets you drag and drop files to the page and see if the fields are detected.</span></span>

    ![Confirmar campos](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="16b03-170">Quando vir a notificação de que o treinamento foi concluído, marque **Acessar a página de detalhes**.</span><span class="sxs-lookup"><span data-stu-id="16b03-170">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="16b03-p113">Na página **Detalhes do modelo**, opte por testar como seu modelo funciona selecionando **Teste rápido**. Isso permite arrastar e soltar arquivos para a página e ver se os campos são detectados.</span><span class="sxs-lookup"><span data-stu-id="16b03-p113">On the **Model details** page, choose to test how your model works by selecting **Quick test**. This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="16b03-173">Etapa 5: publicar seu modelo</span><span class="sxs-lookup"><span data-stu-id="16b03-173">Step 5: Publish your model</span></span>

1. <span data-ttu-id="16b03-174">Se você estiver satisfeito com os resultados do modelo, selecione **Publicar** para disponibilizá-lo para uso.</span><span class="sxs-lookup"><span data-stu-id="16b03-174">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>

2. <span data-ttu-id="16b03-p114">Após a publicação do modelo, selecione **Usar modelo**. Isso cria um fluxo PowerAutomate que pode ser executado na biblioteca de documentos do SharePoint e extrai os campos identificados no modelo e, em seguida, selecione **Criar Fluxo**.</span><span class="sxs-lookup"><span data-stu-id="16b03-p114">After the model is published, select **Use model**. This creates a PowerAutomate flow that can run in your SharePoint document library and extracts the fields that have been identified in the model, then select **Create Flow**.</span></span>
  
3. <span data-ttu-id="16b03-177">Quando concluir, você verá a mensagem **Seu fluxo foi criado com êxito**.</span><span class="sxs-lookup"><span data-stu-id="16b03-177">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="16b03-178">Etapa 6: usar o seu modelo</span><span class="sxs-lookup"><span data-stu-id="16b03-178">Step 6: Use your model</span></span>

<span data-ttu-id="16b03-179">Depois de publicar seu modelo e criar seu fluxo PowerAutomate, você pode usar o modelo na biblioteca de documentos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="16b03-179">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="16b03-180">Depois de publicar seu modelo, selecione **Acessar o SharePoint** para ir para a biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="16b03-180">After publishing your model, select **Go to SharePoint** to go to your document library.</span></span>

2. <span data-ttu-id="16b03-181">No modo de exibição modelo de biblioteca de documentos, observe que os campos selecionados agora são exibidos como colunas.</span><span class="sxs-lookup"><span data-stu-id="16b03-181">In the document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![Modelo de biblioteca de documentos aplicado](../media/content-understanding/doc-lib-view.png)</br> 

3. <span data-ttu-id="16b03-183">Observe que o link de informações ao lado de **Documentos** nota que um modelo de processamento de formulários foi aplicado a essa biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="16b03-183">Notice that the information link next to **Documents** notes that a forms processing model is applied to this document library.</span></span>

    ![Botão informações](../media/content-understanding/info-button.png)</br>  

4. <span data-ttu-id="16b03-p115">Carregar arquivos para uma biblioteca de documentos. Qualquer arquivo identificado pelo modelo como tipo de conteúdo, lista os arquivos em seu modo de exibição e exibe os dados extraídos nas colunas.</span><span class="sxs-lookup"><span data-stu-id="16b03-p115">Upload files to your document library. Any files that the model identifies as it's content type lists the files in your view and displays the extracted data in the columns.</span></span></br>

    ![Concluído](../media/content-understanding/doc-lib-done.png)</br>  

## <a name="see-also"></a><span data-ttu-id="16b03-188">Confira também</span><span class="sxs-lookup"><span data-stu-id="16b03-188">See Also</span></span>
  
[<span data-ttu-id="16b03-189">Documentação do Power Automate</span><span class="sxs-lookup"><span data-stu-id="16b03-189">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)

[<span data-ttu-id="16b03-190">Treinamento: Melhore o desempenho de negócios com o AI Builder</span><span class="sxs-lookup"><span data-stu-id="16b03-190">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
