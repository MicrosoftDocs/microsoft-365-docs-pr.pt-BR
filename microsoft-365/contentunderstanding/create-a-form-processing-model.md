---
title: Criar um modelo de processamento de formulário (versão prévia)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Criar um modelo de processamento de formulários no Project Cortex.
ms.openlocfilehash: d3ca64ff5923e95704b72fd748884549a18624a3
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540137"
---
# <a name="create-a-form-processing-model-preview"></a><span data-ttu-id="741d0-103">Criar um modelo de processamento de formulário (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="741d0-103">Create a form processing model (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="741d0-104">O conteúdo deste artigo é para a visualização privada do Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="741d0-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="741d0-105">[Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="741d0-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="741d0-106">Usando o [ai Builder](https://docs.microsoft.com/ai-builder/overview) -um recurso no Microsoft PowerApps-Project Cortex os usuários podem criar um [modelo de processamento de formulários](form-processing-overview.md) diretamente de uma biblioteca de documentos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="741d0-106">Using [AI Builder](https://docs.microsoft.com/ai-builder/overview) - a feature in Microsoft PowerApps - Project Cortex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="741d0-107">A criação de um modelo de processamento de formulários envolve o seguinte:</span><span class="sxs-lookup"><span data-stu-id="741d0-107">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="741d0-108">Etapa 1: criar o modelo de processamento do para criar o tipo de conteúdo</span><span class="sxs-lookup"><span data-stu-id="741d0-108">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="741d0-109">Etapa 2: Adicionar e analisar arquivos de exemplo</span><span class="sxs-lookup"><span data-stu-id="741d0-109">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="741d0-110">Etapa 3: selecionar seus campos de formulário</span><span class="sxs-lookup"><span data-stu-id="741d0-110">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="741d0-111">Etapa 4: treinar e testar seu modelo</span><span class="sxs-lookup"><span data-stu-id="741d0-111">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="741d0-112">Etapa 5: publicar seu modelo</span><span class="sxs-lookup"><span data-stu-id="741d0-112">Step 5: Publish your model</span></span>
 - <span data-ttu-id="741d0-113">Etapa 6: usar o modelo</span><span class="sxs-lookup"><span data-stu-id="741d0-113">Step 6: Use your model</span></span>


## <a name="requirements"></a><span data-ttu-id="741d0-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="741d0-114">Requirements</span></span>

<span data-ttu-id="741d0-115">Você só pode criar um modelo de processamento de formulário em bibliotecas de documentos do SharePoint em que ele está habilitado.</span><span class="sxs-lookup"><span data-stu-id="741d0-115">You can only create a form processing model in SharePoint document libraries in which it is enabled.</span></span> <span data-ttu-id="741d0-116">Se o processamento de formulários estiver habilitado, você poderá ver o **Construtor ai** **"criar um modelo de processamento de formulários** " no menu **automatizar** da biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="741d0-116">If form processing is enabled, you will be able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.</span></span>  <span data-ttu-id="741d0-117">Se você precisar do processamento habilitado em sua biblioteca de documentos, entre em contato com seu administrador.</span><span class="sxs-lookup"><span data-stu-id="741d0-117">If you need from processing enabled on your document library, contact your admin.</span></span>

 ![Criar um modelo do AI Builder](../media/content-understanding/create-ai-builder-model.png)</br>


## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="741d0-119">Etapa 1: criar um modelo de processamento de formulário</span><span class="sxs-lookup"><span data-stu-id="741d0-119">Step 1: Create a Form Processing model</span></span>

<span data-ttu-id="741d0-120">A primeira etapa na criação de um modelo de processamento de formulários é nomeá-lo para criar o novo tipo de conteúdo e criar um novo modo de exibição de biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="741d0-120">The first step in creating a form processing model is to name it to create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="741d0-121">Na biblioteca de documentos, selecione o menu **automatizar** , selecione **Construtor ai**e, em seguida, selecione **criar um modelo de processamento de formulários**.</span><span class="sxs-lookup"><span data-stu-id="741d0-121">In your document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![Criar um modelo do AI Builder](../media/content-understanding/create-ai-builder-model.png)</br>
2. <span data-ttu-id="741d0-123">No painel **novo modelo de processamento de formulário** , no campo **nome** , digite um nome para o modelo (por exemplo, *ordens de compra*).</span><span class="sxs-lookup"><span data-stu-id="741d0-123">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![Novo modelo de processamento de formulário](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="741d0-125">Ao criar um modelo de processamento de formulário, você está criando um novo tipo de conteúdo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="741d0-125">When you create a form processing model, you are creating a new SharePoint content type.</span></span> <span data-ttu-id="741d0-126">Um tipo de conteúdo do SharePoint representa uma categoria de documentos que têm características comuns e compartilham uma coleção de colunas ou propriedades de metadados para esse conteúdo específico.</span><span class="sxs-lookup"><span data-stu-id="741d0-126">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="741d0-127">Os tipos de conteúdo do SharePoint são gerenciados por meio da [Galeria de tipos de conteúdo]().</span><span class="sxs-lookup"><span data-stu-id="741d0-127">SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="741d0-128">Selecione **Configurações avançadas** se quiser mapear esse modelo para um tipo de conteúdo existente na Galeria de tipos de conteúdo do SharePoint para usar seu esquema.</span><span class="sxs-lookup"><span data-stu-id="741d0-128">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="741d0-129">Seu modelo criará um novo modo de exibição na biblioteca de documentos para os dados extraídos.</span><span class="sxs-lookup"><span data-stu-id="741d0-129">Your model will create a new view in your document library for your extracted data.</span></span> <span data-ttu-id="741d0-130">Se você não quiser fazê-lo para o modo de exibição padrão, desmarque **definir o modo de exibição como padrão**.</span><span class="sxs-lookup"><span data-stu-id="741d0-130">If you do not want it to the default view, deselect **Set the view as default**.</span></span>
5. <span data-ttu-id="741d0-131">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="741d0-131">Select **Create**.</span></span>


## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="741d0-132">Etapa 2: Adicionar e analisar documentos</span><span class="sxs-lookup"><span data-stu-id="741d0-132">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="741d0-133">Depois de criar seu novo modelo de processamento de formulário, seu navegador abrirá uma nova página de modelo de processamento de formulários do Construtor AI.</span><span class="sxs-lookup"><span data-stu-id="741d0-133">After you create your new form processing model, your browser will open a new PowerApps AI Builder forms processing model page.</span></span> <span data-ttu-id="741d0-134">Nesta página, você pode adicionar e analisar seus documentos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="741d0-134">On this page you can add and analyze your example documents.</span></span> </br>

> [!Note]
> <span data-ttu-id="741d0-135">Ao procurar por exemplos de arquivos a serem usados, consulte o [modelo de processamento de formulários de entrada e dicas de otimização](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span><span class="sxs-lookup"><span data-stu-id="741d0-135">When looking for example files to use, see the [form processing model input document requirements and optimization tips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

   ![Construtor AI de aplicativos de energia](../media/content-understanding/powerapps.png)</br> 
 

1. <span data-ttu-id="741d0-137">Clique em **adicionar documentos** para começar a adicionar documentos de exemplo que são analisados para determinar quais pares de valores nomeados podem ser extraídos.</span><span class="sxs-lookup"><span data-stu-id="741d0-137">Click **Add documents** to begin adding example documents that are analyzed to determine what named value pairs can be extracted.</span></span> <span data-ttu-id="741d0-138">Você pode escolher **carregar do armazenamento local**, **do SharePoint**ou **do armazenamento de blob do Azure**.</span><span class="sxs-lookup"><span data-stu-id="741d0-138">You can choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**.</span></span> <span data-ttu-id="741d0-139">Você precisará usar pelo menos cinco arquivos para treinamento.</span><span class="sxs-lookup"><span data-stu-id="741d0-139">You will need to use at least five files for training.</span></span>
2. <span data-ttu-id="741d0-140">Após adicionar seus arquivos, selecione **analisar** para verificar se há alguma informação comum em todos os arquivos.</span><span class="sxs-lookup"><span data-stu-id="741d0-140">After adding your files, select **Analyze** to check for any information that is common is all files.</span></span> <span data-ttu-id="741d0-141">Observe que isso pode levar alguns minutos para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="741d0-141">Note that this may take several minutes to complete.</span></span></br> 
 
    ![Analisar arquivos](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="741d0-143">Após a análise, na página **Selecione os campos de formulário que você deseja salvar** , clique no arquivo para ver os campos que foram detectados.</span><span class="sxs-lookup"><span data-stu-id="741d0-143">After they have been analyzed, in the **Select the form fields you want to save** page, click the file to see the fields that were detected.</span></span></br>

    ![Selecionar campos de formulário](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="741d0-145">Etapa 3: selecionar seus campos de formulário</span><span class="sxs-lookup"><span data-stu-id="741d0-145">Step 3: Select your form fields</span></span>

<span data-ttu-id="741d0-146">Após analisar seus documentos para campos, agora você poderá ver quais campos foram encontrados e quais serão salvos.</span><span class="sxs-lookup"><span data-stu-id="741d0-146">After analyzing your documents for fields, you can now see which fields were found, and which ones you want to save.</span></span> <span data-ttu-id="741d0-147">Os campos salvos serão exibidos como colunas no modo de exibição de biblioteca de documentos do seu modelo e mostrarão os valores extraídos de cada documento.</span><span class="sxs-lookup"><span data-stu-id="741d0-147">Saved fields will display as columns in your model's document library view and will show the values extracted from each document.</span></span>

1. <span data-ttu-id="741d0-148">A próxima página exibirá um de seus arquivos de exemplo e realçará todos os campos comuns que foram detectados automaticamente pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="741d0-148">The next page will display one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![Selecionar campos de formulário](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="741d0-150">Selecione os campos que você deseja salvar e marque a caixa de seleção para confirmar sua seleção.</span><span class="sxs-lookup"><span data-stu-id="741d0-150">Select the fields you want to save, and select the checkbox to confirm your selection.</span></span> <span data-ttu-id="741d0-151">Por exemplo, no modelo de ordem de compra, você pode optar por selecionar os campos *Data*, *OC*e *total* .</span><span class="sxs-lookup"><span data-stu-id="741d0-151">For example, in the Purchase Order model, you can choose to select the *Date*, *PO*, and *Total* fields.</span></span>  <span data-ttu-id="741d0-152">Observe que você também pode optar por renomear um campo se escolher.</span><span class="sxs-lookup"><span data-stu-id="741d0-152">Note that you can also choose to rename a field if you choose.</span></span> </br>

    ![Selecionar OC #](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="741d0-154">Se um campo não foi detectado pela análise, você ainda pode optar por adicioná-lo.</span><span class="sxs-lookup"><span data-stu-id="741d0-154">If a field was not detected by analysis, you can still choose to add it.</span></span> <span data-ttu-id="741d0-155">Destaque as informações que você deseja extrair e, na caixa nome, digite o nome que você deseja dar.</span><span class="sxs-lookup"><span data-stu-id="741d0-155">Highlight the information you want to extract, and in the name box type in the name you want to give it.</span></span> <span data-ttu-id="741d0-156">Em seguida, selecione a verificação.</span><span class="sxs-lookup"><span data-stu-id="741d0-156">Then select the check.</span></span> <span data-ttu-id="741d0-157">Observe que você precisará confirmar campos não detectados em seus arquivos de exemplo restantes.</span><span class="sxs-lookup"><span data-stu-id="741d0-157">Note that you will need to confirm undetected fields in your remaining example files.</span></span>
4. <span data-ttu-id="741d0-158">Clique em **confirmar campos** depois de selecionar os campos que você deseja salvar.</span><span class="sxs-lookup"><span data-stu-id="741d0-158">Click **Confirm fields** after you have selected the fields you want to save.</span></span> </br>
 
    ![Confirmar campos](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="741d0-160">Na página **selecionar os campos de formulário que você deseja salvar** , ele mostrará o número de campos selecionados.</span><span class="sxs-lookup"><span data-stu-id="741d0-160">On the **Select the form fields you want to save** page, it will show the number of fields you have selected.</span></span> <span data-ttu-id="741d0-161">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="741d0-161">Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="741d0-162">Etapa 4: treinar e testar seu modelo</span><span class="sxs-lookup"><span data-stu-id="741d0-162">Step 4: Train and test your model</span></span>

<span data-ttu-id="741d0-163">Depois de selecionar os campos que você deseja salvar, a página de **Resumo do modelo** permitirá treinar e testar o modelo.</span><span class="sxs-lookup"><span data-stu-id="741d0-163">After selecting the fields you want to save, the **Model Summary** page will let you train and test your model.</span></span>

1. <span data-ttu-id="741d0-164">Na página de **Resumo do modelo** , os campos salvos serão exibidos na seção **campos selecionados** .</span><span class="sxs-lookup"><span data-stu-id="741d0-164">On the **Model Summary** page, the saved fields will show in the **Selected fields** section.</span></span> <span data-ttu-id="741d0-165">Selecione **treinar** para começar o treinamento nos seus arquivos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="741d0-165">Select **Train** to begin training on your example files.</span></span> <span data-ttu-id="741d0-166">Observe que isso pode levar alguns minutos para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="741d0-166">Note that this may take a few minutes to complete.</span></span></br>
    <span data-ttu-id="741d0-167">![Confirmar campos](../media/content-understanding/select-fields-train.png)</span><span class="sxs-lookup"><span data-stu-id="741d0-167">![Confirm fields](../media/content-understanding/select-fields-train.png)</span></span></br> 
2. <span data-ttu-id="741d0-168">Quando você vir a notificação de que o treinamento foi concluído, selecione **ir para a página de detalhes**.</span><span class="sxs-lookup"><span data-stu-id="741d0-168">When you see the notification that training has completed, select **Go to details page**.</span></span> 
3. <span data-ttu-id="741d0-169">Na página **detalhes do modelo** , você pode optar por testar como funciona o modelo selecionando **teste rápido**.</span><span class="sxs-lookup"><span data-stu-id="741d0-169">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="741d0-170">Isso permite que você arraste e solte arquivos para a página e veja se os campos foram detectados.</span><span class="sxs-lookup"><span data-stu-id="741d0-170">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="741d0-171">Etapa 5: publicar seu modelo</span><span class="sxs-lookup"><span data-stu-id="741d0-171">Step 5: Publish your model</span></span>



1. <span data-ttu-id="741d0-172">Se estiver satisfeito com os resultados do modelo, selecione **publicar** para torná-lo disponível para uso.</span><span class="sxs-lookup"><span data-stu-id="741d0-172">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>
2. <span data-ttu-id="741d0-173">Após o modelo publicado, selecione **usar modelo**.</span><span class="sxs-lookup"><span data-stu-id="741d0-173">After the model published, select **Use model**.</span></span> <span data-ttu-id="741d0-174">Isso cria um fluxo do PowerAutomate que será executado na biblioteca de documentos do SharePoint e extrairá os campos que foram identificados no modelo.</span><span class="sxs-lookup"><span data-stu-id="741d0-174">This creates a PowerAutomate flow that will run in your SharePoint document library and will extract the fields that have been identified in the model.</span></span> <span data-ttu-id="741d0-175">Selecione **criar fluxo**.</span><span class="sxs-lookup"><span data-stu-id="741d0-175">Select **Create Flow**.</span></span>  
3. <span data-ttu-id="741d0-176">Quando for concluída, você verá a mensagem **de que o fluxo foi criado com êxito**.</span><span class="sxs-lookup"><span data-stu-id="741d0-176">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="741d0-177">Etapa 6: usar o modelo</span><span class="sxs-lookup"><span data-stu-id="741d0-177">Step 6: Use your model</span></span>

<span data-ttu-id="741d0-178">Após publicar o modelo e criar o fluxo de PowerAutomate, você pode usar o modelo na biblioteca de documentos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="741d0-178">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="741d0-179">Após publicar o modelo, selecione **ir para o SharePoint** para ir para a biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="741d0-179">After publishing your model , select **Go to SharePoint** to go to your document library.</span></span>
2. <span data-ttu-id="741d0-180">No modo de exibição modelo de biblioteca de documentos, observe que os campos selecionados agora são exibidos como colunas.</span><span class="sxs-lookup"><span data-stu-id="741d0-180">On your document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![Biblioteca de documentos com o modelo aplicado](../media/content-understanding/doc-lib-view.png)</br> 

    <span data-ttu-id="741d0-182">Observe também que o link de informações ao lado de **documentos** notará que um modelo de processamento de formulários é aplicado a esta biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="741d0-182">Also notice that the information link next to **Documents** will note that a forms processing model is applied to this document library.</span></span>

    ![Extrair](../media/content-understanding/info-button.png)</br>  

3. <span data-ttu-id="741d0-184">Carregar arquivos para sua biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="741d0-184">Upload files to your document library.</span></span> <span data-ttu-id="741d0-185">Qualquer arquivo que o modelo identifica como o tipo de conteúdo listará os arquivos em seu modo de exibição e exibirá os dados extraídos nas colunas.</span><span class="sxs-lookup"><span data-stu-id="741d0-185">Any files that the model identifies as it's content type will list the files in your view, and will display the extracted data in the columns.</span></span></br>

    ![Extrair](../media/content-understanding/doc-lib-done.png)</br>  



## <a name="see-also"></a><span data-ttu-id="741d0-187">Confira também</span><span class="sxs-lookup"><span data-stu-id="741d0-187">See Also</span></span>
  
[<span data-ttu-id="741d0-188">Documentação da automatização de energia</span><span class="sxs-lookup"><span data-stu-id="741d0-188">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="741d0-189">Treinamento: aprimore o desempenho de negócios com o Construtor AI</span><span class="sxs-lookup"><span data-stu-id="741d0-189">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




