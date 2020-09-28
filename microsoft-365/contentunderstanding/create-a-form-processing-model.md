---
title: Criar um modelo de processamento de formulários
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
description: Criar um modelo de processamento de formulários no Microsoft SharePoint Syntex.
ms.openlocfilehash: f61dbad837173c412daefb7285c4abff10a01817
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295473"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="f6d0e-103">Criar um modelo de processamento de formulários no Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="f6d0e-103">Create a form processing model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="f6d0e-104">O conteúdo deste artigo é para a visualização privada do projeto Cortex.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="f6d0e-105">[Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="f6d0e-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="f6d0e-106">Usando o [ai Builder](https://docs.microsoft.com/ai-builder/overview) -um recurso no Microsoft PowerApps-Project Cortex os usuários podem criar um [modelo de processamento de formulários](form-processing-overview.md) diretamente de uma biblioteca de documentos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-106">Using [AI Builder](https://docs.microsoft.com/ai-builder/overview) - a feature in Microsoft PowerApps - Project Cortex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="f6d0e-107">A criação de um modelo de processamento de formulários envolve o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f6d0e-107">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="f6d0e-108">Etapa 1: criar o modelo de processamento do para criar o tipo de conteúdo</span><span class="sxs-lookup"><span data-stu-id="f6d0e-108">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="f6d0e-109">Etapa 2: Adicionar e analisar arquivos de exemplo</span><span class="sxs-lookup"><span data-stu-id="f6d0e-109">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="f6d0e-110">Etapa 3: selecionar seus campos de formulário</span><span class="sxs-lookup"><span data-stu-id="f6d0e-110">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="f6d0e-111">Etapa 4: treinar e testar seu modelo</span><span class="sxs-lookup"><span data-stu-id="f6d0e-111">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="f6d0e-112">Etapa 5: publicar seu modelo</span><span class="sxs-lookup"><span data-stu-id="f6d0e-112">Step 5: Publish your model</span></span>
 - <span data-ttu-id="f6d0e-113">Etapa 6: usar o modelo</span><span class="sxs-lookup"><span data-stu-id="f6d0e-113">Step 6: Use your model</span></span>

## <a name="requirements"></a><span data-ttu-id="f6d0e-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f6d0e-114">Requirements</span></span>

<span data-ttu-id="f6d0e-115">Você só pode criar um modelo de processamento de formulário em bibliotecas de documentos do SharePoint para os quais ele está habilitado.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-115">You can only create a form processing model in SharePoint document libraries for which it is enabled.</span></span> <span data-ttu-id="f6d0e-116">Se o processamento de formulários estiver habilitado, você poderá ver o **Construtor ai** **"criar um modelo de processamento de formulários** " no menu **automatizar** da biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-116">If form processing is enabled, you are able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.</span></span>  <span data-ttu-id="f6d0e-117">Se você precisar de processamento habilitado em sua biblioteca de documentos, você deve entrar em contato com seu administrador do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-117">If you need processing enabled on your document library, you must contact your SharePoint administrator.</span></span>

 ![Criar um modelo do AI Builder](../media/content-understanding/create-ai-builder-model.png)</br>

## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="f6d0e-119">Etapa 1: criar um modelo de processamento de formulário</span><span class="sxs-lookup"><span data-stu-id="f6d0e-119">Step 1: Create a form Processing model</span></span>

<span data-ttu-id="f6d0e-120">A primeira etapa na criação de um modelo de processamento de formulários é nomeá-lo e criar o novo tipo de conteúdo e criar um novo modo de exibição de biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-120">The first step in creating a form processing model is to name it and create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="f6d0e-121">Na biblioteca de documentos, selecione o menu **automatizar** , selecione **Construtor ai**e, em seguida, selecione **criar um modelo de processamento de formulários**.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-121">From the document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![Criar um modelo](../media/content-understanding/create-ai-builder-model.png)</br>

2. <span data-ttu-id="f6d0e-123">No painel **novo modelo de processamento de formulário** , no campo  **nome** , digite um nome para o modelo (por exemplo, *ordens de compra*).</span><span class="sxs-lookup"><span data-stu-id="f6d0e-123">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![Novo modelo de processamento de formulário](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="f6d0e-125">Ao criar um modelo de processamento de formulário, você cria um novo tipo de conteúdo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-125">When you create a form processing model, you create a new SharePoint content type.</span></span> <span data-ttu-id="f6d0e-126">Um tipo de conteúdo do SharePoint representa uma categoria de documentos que têm características comuns e compartilham uma coleção de colunas ou propriedades de metadados para esse conteúdo específico.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-126">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="f6d0e-127">Os tipos de conteúdo do SharePoint são gerenciados por meio da [Galeria de tipos de conteúdo]().</span><span class="sxs-lookup"><span data-stu-id="f6d0e-127">SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="f6d0e-128">Selecione **Configurações avançadas** se quiser mapear esse modelo para um tipo de conteúdo existente na Galeria de tipos de conteúdo do SharePoint para usar seu esquema.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-128">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="f6d0e-129">Seu modelo cria um novo modo de exibição na biblioteca de documentos para os dados extraídos.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-129">Your model creates a new view in your document library for your extracted data.</span></span> <span data-ttu-id="f6d0e-130">Se você não quiser fazê-lo para o modo de exibição padrão, desmarque **definir o modo de exibição como padrão**.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-130">If you do not want it to the default view, deselect **Set the view as default**.</span></span>

5. <span data-ttu-id="f6d0e-131">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-131">Select **Create**.</span></span>

## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="f6d0e-132">Etapa 2: Adicionar e analisar documentos</span><span class="sxs-lookup"><span data-stu-id="f6d0e-132">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="f6d0e-133">Depois de criar seu novo modelo de processamento de formulário, seu navegador abre uma nova página de modelo de processamento de formulários do Construtor AI.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-133">After you create your new form processing model, your browser opens a new PowerApps AI Builder forms processing model page.</span></span> <span data-ttu-id="f6d0e-134">Nesta página, você pode adicionar e analisar seus documentos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-134">On this page you can add and analyze your example documents.</span></span> </br>

> [!NOTE]
> <span data-ttu-id="f6d0e-135">Ao procurar por exemplos de arquivos a serem usados, consulte o [modelo de processamento de formulários de entrada e dicas de otimização](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span><span class="sxs-lookup"><span data-stu-id="f6d0e-135">When looking for example files to use, see the [form processing model input document requirements and optimization tips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

   ![Construtor AI de aplicativos de energia](../media/content-understanding/powerapps.png)</br> 
 
1. <span data-ttu-id="f6d0e-137">Selecione **adicionar documentos** para começar a adicionar documentos de exemplo analisados para determinar os pares de valores nomeados que podem ser extraídos.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-137">Select **Add documents** to begin adding example documents analyzed to determine the named value pairs that can be extracted.</span></span> <span data-ttu-id="f6d0e-138">Em seguida, você pode escolher **carregar do armazenamento local**, **do SharePoint**ou **do armazenamento de blob do Azure**.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-138">You can then choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**.</span></span> <span data-ttu-id="f6d0e-139">Você precisa usar pelo menos cinco arquivos para treinamento.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-139">You need to use at least five files for training.</span></span>

2. <span data-ttu-id="f6d0e-140">Após adicionar arquivos, selecione **analisar** para verificar se há informações comuns em todos os arquivos.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-140">After adding files, select **Analyze** to check for any information common is all files.</span></span> <span data-ttu-id="f6d0e-141">Isso pode levar alguns minutos para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-141">This may take several minutes to complete.</span></span></br> 
 
    ![Analisar arquivos](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="f6d0e-143">Após a análise dos arquivos, na página **Selecione os campos de formulário que você deseja salvar** , selecione o arquivo para exibir os campos detectados.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-143">After the files have been analyzed, in the **Select the form fields you want to save** page select the file to view the detected fields.</span></span></br>

    ![Selecionar campos de formulário](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="f6d0e-145">Etapa 3: selecionar seus campos de formulário</span><span class="sxs-lookup"><span data-stu-id="f6d0e-145">Step 3: Select your form fields</span></span>

<span data-ttu-id="f6d0e-146">Após analisar os documentos de campos, agora você pode ver os campos que foram encontrados e identificar aqueles que você deseja salvar.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-146">After analyzing the documents for fields, you can now see the fields that were found, and identify the ones that you want to save.</span></span> <span data-ttu-id="f6d0e-147">Os campos salvos são exibidos como colunas no modo de exibição de biblioteca de documentos do seu modelo e mostram os valores extraídos de cada documento.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-147">Saved fields display as columns in your model's document library view and show the values extracted from each document.</span></span>

1. <span data-ttu-id="f6d0e-148">A próxima página exibe um de seus arquivos de amostra e realçará todos os campos comuns que foram detectados automaticamente pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-148">The next page displays one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![Página Selecionar campos](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="f6d0e-150">Selecione os campos que você deseja salvar e marque a caixa de seleção para confirmar sua seleção.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-150">Select the fields that you want to save and select the checkbox to confirm your selection.</span></span> <span data-ttu-id="f6d0e-151">Por exemplo, no modelo de ordem de compra, escolha a seleção dos campos *Data*, *OC*e *total* .</span><span class="sxs-lookup"><span data-stu-id="f6d0e-151">For example, in the Purchase Order model, choose to select the *Date*, *PO*, and *Total* fields.</span></span>  <span data-ttu-id="f6d0e-152">Observe que você também pode optar por renomear um campo se escolher.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-152">Note that you can also choose to rename a field if you choose.</span></span> </br>

    ![Selecionar OC #](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="f6d0e-154">Se um campo não foi detectado pela análise, você ainda pode optar por adicioná-lo.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-154">If a field was not detected by analysis, you can still choose to add it.</span></span> <span data-ttu-id="f6d0e-155">Destaque as informações que você deseja extrair e, na caixa nome, digite o nome desejado.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-155">Highlight the information you want to extract, and in the name box type in the name you want.</span></span> <span data-ttu-id="f6d0e-156">Em seguida, marque a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-156">Then select the check box.</span></span> <span data-ttu-id="f6d0e-157">Observe que você precisa confirmar campos não detectados em seus arquivos de amostra restantes.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-157">Note that you need to confirm undetected fields in your remaining sample files.</span></span>

4. <span data-ttu-id="f6d0e-158">Clique em **confirmar campos** depois de selecionar os campos que você deseja salvar.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-158">Click **Confirm fields** after you have selected the fields that you want to save.</span></span> </br>
 
    ![Confirmar campos após selecionar campos](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="f6d0e-160">Na página **selecionar os campos de formulário que você deseja salvar** , ele mostra o número de campos que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-160">On the **Select the form fields you want to save** page, it shows the number of fields you have selected.</span></span> <span data-ttu-id="f6d0e-161">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-161">Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="f6d0e-162">Etapa 4: treinar e testar seu modelo</span><span class="sxs-lookup"><span data-stu-id="f6d0e-162">Step 4: Train and test your model</span></span>

<span data-ttu-id="f6d0e-163">Depois de selecionar os campos que você deseja salvar, a página de **Resumo do modelo** permite treinar e testar o modelo.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-163">After selecting the fields you want to save, the **Model Summary** page lets you train and test your model.</span></span>

1. <span data-ttu-id="f6d0e-164">Na página de **Resumo do modelo** , os campos salvos serão exibidos na seção **campos selecionados** .</span><span class="sxs-lookup"><span data-stu-id="f6d0e-164">On the **Model Summary** page, the saved fields will show in the **Selected fields** section.</span></span> <span data-ttu-id="f6d0e-165">Selecione **treinar** para começar o treinamento nos seus arquivos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-165">Select **Train** to begin training on your example files.</span></span> <span data-ttu-id="f6d0e-166">Observe que isso pode levar alguns minutos para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-166">Note that this may take a few minutes to complete.</span></span></br>

     ![Selecionar campos treinar](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="f6d0e-168">Quando você vir a notificação de que o treinamento foi concluído, selecione **ir para a página de detalhes**.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-168">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="f6d0e-169">Na página **detalhes do modelo** , você pode optar por testar como funciona o modelo selecionando **teste rápido**.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-169">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="f6d0e-170">Isso permite que você arraste e solte arquivos para a página e veja se os campos foram detectados.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-170">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

    ![Confirmar campos](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="f6d0e-172">Quando você vir a notificação de que o treinamento foi concluído, selecione **ir para a página de detalhes**.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-172">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="f6d0e-173">Na página **detalhes do modelo** , escolha testar como funciona o modelo selecionando **teste rápido**.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-173">On the **Model details** page, choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="f6d0e-174">Isso permite que você arraste e solte arquivos para a página e veja se os campos foram detectados.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-174">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="f6d0e-175">Etapa 5: publicar seu modelo</span><span class="sxs-lookup"><span data-stu-id="f6d0e-175">Step 5: Publish your model</span></span>

1. <span data-ttu-id="f6d0e-176">Se estiver satisfeito com os resultados do modelo, selecione **publicar** para torná-lo disponível para uso.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-176">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>

2. <span data-ttu-id="f6d0e-177">Depois que o modelo for publicado, selecione **usar modelo**.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-177">After the model is published, select **Use model**.</span></span> <span data-ttu-id="f6d0e-178">Isso cria um fluxo de PowerAutomate que pode ser executado na biblioteca de documentos do SharePoint e extrai os campos que foram identificados no modelo e, em seguida, selecione **criar fluxo**.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-178">This creates a PowerAutomate flow that can run in your SharePoint document library and extracts the fields that have been identified in the model, then select **Create Flow**.</span></span>
  
3. <span data-ttu-id="f6d0e-179">Quando for concluída, você verá a mensagem **de que o fluxo foi criado com êxito**.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-179">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="f6d0e-180">Etapa 6: usar o modelo</span><span class="sxs-lookup"><span data-stu-id="f6d0e-180">Step 6: Use your model</span></span>

<span data-ttu-id="f6d0e-181">Após publicar o modelo e criar o fluxo de PowerAutomate, você pode usar o modelo na biblioteca de documentos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-181">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="f6d0e-182">Após publicar o modelo, selecione **ir para o SharePoint** para ir para a biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-182">After publishing your model, select **Go to SharePoint** to go to your document library.</span></span>

2. <span data-ttu-id="f6d0e-183">No modo de exibição modelo de biblioteca de documentos, observe que os campos selecionados agora são exibidos como colunas.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-183">In the document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![Modelo de biblioteca de documentos aplicado](../media/content-understanding/doc-lib-view.png)</br> 

3. <span data-ttu-id="f6d0e-185">Observe que o link de informações ao lado de **documentos** avisa que um modelo de processamento de formulários é aplicado a esta biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-185">Notice that the information link next to **Documents** notes that a forms processing model is applied to this document library.</span></span>

    ![Botão informações](../media/content-understanding/info-button.png)</br>  

4. <span data-ttu-id="f6d0e-187">Carregar arquivos para sua biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-187">Upload files to your document library.</span></span> <span data-ttu-id="f6d0e-188">Qualquer arquivo que o modelo identifica como o tipo de conteúdo lista os arquivos em seu modo de exibição e exibe os dados extraídos nas colunas.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-188">Any files that the model identifies as it's content type lists the files in your view and displays the extracted data in the columns.</span></span></br>

    ![Concluído](../media/content-understanding/doc-lib-done.png)</br>  

## <a name="see-also"></a><span data-ttu-id="f6d0e-190">Confira também</span><span class="sxs-lookup"><span data-stu-id="f6d0e-190">See Also</span></span>
  
[<span data-ttu-id="f6d0e-191">Documentação da automatização de energia</span><span class="sxs-lookup"><span data-stu-id="f6d0e-191">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="f6d0e-192">Treinamento: aprimore o desempenho de negócios com o Construtor AI</span><span class="sxs-lookup"><span data-stu-id="f6d0e-192">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
