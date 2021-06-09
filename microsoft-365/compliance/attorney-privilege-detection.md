---
title: Configurar a detecção de privilégio advogado-cliente em Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use o modelo de detecção de privilégio advogado-cliente para usar a detecção baseada em aprendizado de máquina de conteúdo privilegiado ao analisar o conteúdo em um Advanced eDiscovery caso.
ms.openlocfilehash: 73a0efeece7bc331045e9bbe1a1da56f9fd24700
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358037"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a><span data-ttu-id="85649-103">Configurar a detecção de privilégio advogado-cliente em Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="85649-103">Set up attorney-client privilege detection in Advanced eDiscovery</span></span>

<span data-ttu-id="85649-104">Um aspecto importante e caro da fase de revisão de qualquer processo de Descoberta e é analisar documentos para conteúdo privilegiado.</span><span class="sxs-lookup"><span data-stu-id="85649-104">A major and costly aspect of the review phase of any eDiscovery process is reviewing documents for privileged content.</span></span> <span data-ttu-id="85649-105">Advanced eDiscovery fornece detecção baseada em aprendizado de máquina de conteúdo privilegiado para tornar esse processo mais eficiente.</span><span class="sxs-lookup"><span data-stu-id="85649-105">Advanced eDiscovery provides machine learning-based detection of privileged content to make this process more efficient.</span></span> <span data-ttu-id="85649-106">Esse recurso é chamado de *detecção de privilégio advogado-cliente.*</span><span class="sxs-lookup"><span data-stu-id="85649-106">This feature is called *attorney-client privilege detection*.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="85649-107">Como funciona?</span><span class="sxs-lookup"><span data-stu-id="85649-107">How does it work?</span></span>

<span data-ttu-id="85649-108">Quando a detecção de privilégio advogado-cliente estiver habilitada, todos os documentos em [](analyzing-data-in-review-set.md) um conjunto de revisão serão processados pelo modelo de detecção de privilégio advogado-cliente quando você analisar os dados no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="85649-108">When attorney-client privilege detection is enabled, all documents in a review set will be processed by the attorney-client privilege detection model when you [analyze the data](analyzing-data-in-review-set.md) in the review set.</span></span> <span data-ttu-id="85649-109">O modelo procura duas coisas:</span><span class="sxs-lookup"><span data-stu-id="85649-109">The model looks for two things:</span></span>

- <span data-ttu-id="85649-110">Conteúdo privilegiado – O modelo usa o aprendizado de máquina para determinar a probabilidade de que o documento contenha conteúdo legal de natureza.</span><span class="sxs-lookup"><span data-stu-id="85649-110">Privileged content – The model uses machine learning to determine the likelihood that the document contains content that is legal in nature.</span></span>

- <span data-ttu-id="85649-111">Participantes – Como parte da configuração da detecção de privilégio advogado-cliente, você precisa enviar uma lista de advogados para sua organização.</span><span class="sxs-lookup"><span data-stu-id="85649-111">Participants – As part of setting up attorney-client privilege detection, you have to submit a list of attorneys for your organization.</span></span> <span data-ttu-id="85649-112">Em seguida, o modelo compara os participantes do documento com a lista de contatos para determinar se um documento tem pelo menos um participante.</span><span class="sxs-lookup"><span data-stu-id="85649-112">The model then compares the participants of the document with the attorney list to determine if a document has at least one attorney participant.</span></span>

<span data-ttu-id="85649-113">O modelo produz as três propriedades a seguir para cada documento:</span><span class="sxs-lookup"><span data-stu-id="85649-113">The model produces the following three properties for every document:</span></span>

- <span data-ttu-id="85649-114">**AttorneyClientPrivilegeScore:** A probabilidade de o documento ser legal; os valores da pontuação estão entre **0** e **1**.</span><span class="sxs-lookup"><span data-stu-id="85649-114">**AttorneyClientPrivilegeScore:** The likelihood the document is legal in nature; the values for the score are between **0** and **1**.</span></span>

- <span data-ttu-id="85649-115">**HasAttorney:** Essa propriedade será definida como **true** se um dos participantes do documento estiver listado na lista de advogados; caso contrário, o valor é **false**.</span><span class="sxs-lookup"><span data-stu-id="85649-115">**HasAttorney:** This property is set to **true** if one of the document participants is listed in the attorney list; otherwise the value is **false**.</span></span> <span data-ttu-id="85649-116">O valor também será definido como **falso** caso sua organização não tenha carregado uma lista de valores.</span><span class="sxs-lookup"><span data-stu-id="85649-116">The value is also set to **false** if your organization didn't upload an attorney list.</span></span>

- <span data-ttu-id="85649-117">**IsPrivilege:** Essa propriedade será definida como **true** se o valor **de AttorneyClientPrivilegeScore** estiver acima do limite ou se o documento tiver um participante de advogado;  caso contrário, o valor é definido como **false**.</span><span class="sxs-lookup"><span data-stu-id="85649-117">**IsPrivilege:** This property is set to **true** if the value for **AttorneyClientPrivilegeScore** is above the threshold *or* if the document has an attorney participant; otherwise the value is set to **false**.</span></span>

<span data-ttu-id="85649-118">Essas propriedades (e seus valores correspondentes) são adicionadas aos metadados de arquivo dos documentos em um conjunto de revisão, conforme mostrado na captura de tela a seguir:</span><span class="sxs-lookup"><span data-stu-id="85649-118">These properties (and their corresponding values) are added to the file metadata of the documents in a review set, as shown in the following screenshot:</span></span>

![Propriedades de privilégio advogado-cliente mostradas em metadados de arquivo](../media/AeDAttorneyClientPrivilegeMetadata.png)

<span data-ttu-id="85649-120">Essas três propriedades também podem ser pesquisadas em um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="85649-120">These three properties are also searchable within a review set.</span></span> <span data-ttu-id="85649-121">Para obter mais informações, [consulte Query the data in a review set](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="85649-121">For more information, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="set-up-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="85649-122">Configurar o modelo de detecção de privilégio advogado-cliente</span><span class="sxs-lookup"><span data-stu-id="85649-122">Set up the attorney-client privilege detection model</span></span>

<span data-ttu-id="85649-123">Para habilitar o modelo de detecção de privilégio advogado-cliente, sua organização precisa ative-lo e carregar uma lista de advogados.</span><span class="sxs-lookup"><span data-stu-id="85649-123">To enable the attorney-client privilege detection model, your organization has to turn it on and then upload an attorney list.</span></span>

### <a name="step-1-turn-on-attorney-client-privilege-detection"></a><span data-ttu-id="85649-124">Etapa 1: Ativar a detecção de privilégio advogado-cliente</span><span class="sxs-lookup"><span data-stu-id="85649-124">Step 1: Turn on attorney-client privilege detection</span></span>

<span data-ttu-id="85649-125">Uma pessoa que seja um Administrador de Descoberta e Descoberta Na sua organização (membro do subgrupo Administrador de Descoberta e No grupo de funções do Gerenciador de Descobertas E) deve disponibilizar o modelo em seus Advanced eDiscovery de descoberta.</span><span class="sxs-lookup"><span data-stu-id="85649-125">A person who is an eDiscovery Administrator in your organization (a member of the eDiscovery Administrator subgroup in the eDiscovery Manager role group) must make the model available in your Advanced eDiscovery cases.</span></span>

1. <span data-ttu-id="85649-126">No Centro de Conformidade & segurança, acesse **eDiscovery > Advanced eDiscovery**.</span><span class="sxs-lookup"><span data-stu-id="85649-126">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery**.</span></span>

2. <span data-ttu-id="85649-127">Na home **page Advanced eDiscovery,** no **Configurações,** clique em **Configurar configurações de análise global**.</span><span class="sxs-lookup"><span data-stu-id="85649-127">On the **Advanced eDiscovery** home page, in the **Settings** tile, click **Configure global analytics settings**.</span></span>

   ![Selecione "Configurar recursos experimentais"](../media/AeDExperimentalFeatures.png)

3. <span data-ttu-id="85649-129">Na guia **Configurações do Analytics,** selecione **Gerenciar a configuração de privilégio advogado-cliente.**</span><span class="sxs-lookup"><span data-stu-id="85649-129">On the **Analytics settings** tab, select **Manage attorney-client privilege setting**.</span></span>

4. <span data-ttu-id="85649-130">Na página **Privilégio do cliente de**, use o recurso de alternância para ativar o recurso e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="85649-130">On the **Attorney-client privilege** flyout page, use the toggle to turn on the feature and then select **Save**.</span></span>

### <a name="step-2-upload-a-list-of-attorneys-optional"></a><span data-ttu-id="85649-131">Etapa 2: Upload uma lista de advogados (opcional)</span><span class="sxs-lookup"><span data-stu-id="85649-131">Step 2: Upload a list of attorneys (optional)</span></span>

<span data-ttu-id="85649-132">Para aproveitar ao máximo o modelo de detecção de privilégio advogado-cliente e usar os resultados da detecção **Has Attorney** ou **Potentially Privileged** que foi descrita anteriormente, recomendamos carregar uma lista de endereços de email para os advogados e a equipe jurídica que trabalham para sua organização.</span><span class="sxs-lookup"><span data-stu-id="85649-132">To take full advantage of the attorney-client privilege detection model and use the results of the **Has Attorney** or **Potentially Privileged** detection that was previously described, we recommend that you upload a list of email addresses for the lawyers and legal personnel who work for your organization.</span></span> 

<span data-ttu-id="85649-133">Para carregar uma lista de advogados para uso pelo modelo de detecção de privilégio advogado-cliente:</span><span class="sxs-lookup"><span data-stu-id="85649-133">To upload an attorney list for use by the attorney-client privilege detection model:</span></span>

1. <span data-ttu-id="85649-p106">Crie um arquivo .csv (sem uma linha de cabeçalho) e adicione o endereço de email para cada pessoa apropriada em uma linha separada. Salve este arquivo em seu computador local.</span><span class="sxs-lookup"><span data-stu-id="85649-p106">Create a .csv file (without a header row) and add the email address for each appropriate person on a separate line. Save this file to your local computer.</span></span>

2. <span data-ttu-id="85649-136">Na home **page Advanced eDiscovery,** no  Configurações, selecione **Configurar** recursos experimentais e selecione Gerenciar configuração de privilégio **advogado-cliente.**</span><span class="sxs-lookup"><span data-stu-id="85649-136">On the **Advanced eDiscovery** home page, in the **Settings** tile, select **Configure experimental features**, and then select **Manage attorney-client privilege setting**.</span></span>

   <span data-ttu-id="85649-137">A página de privilégio **advogado-cliente** é exibida, e a alternância de detecção de privilégio **advogado-cliente** está 2016.</span><span class="sxs-lookup"><span data-stu-id="85649-137">The **Attorney-client privilege** page is displayed, and the **Attorney-client privilege detection** toggle is turned on.</span></span>

   ![Página de sub-sub-subsisão de privilégio advogado-cliente](../media/AeDUploadAttorneyList.png)

3. <span data-ttu-id="85649-139">Selecione **Procurar** e, em seguida, encontre e selecione o arquivo .csv que você criou na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="85649-139">Select **Browse** and then find and select the .csv file that you created in step 1.</span></span>

4. <span data-ttu-id="85649-140">Selecione **Salvar** para carregar a lista de advogados.</span><span class="sxs-lookup"><span data-stu-id="85649-140">Select **Save** to upload the attorney list.</span></span>

## <a name="use-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="85649-141">Usar o modelo de detecção de privilégio advogado-cliente</span><span class="sxs-lookup"><span data-stu-id="85649-141">Use the attorney-client privilege detection model</span></span>

<span data-ttu-id="85649-142">Siga as etapas nesta seção para usar a detecção de privilégio advogado-cliente para documentos em um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="85649-142">Follow the steps in this section to use attorney-client privilege detection for documents in a review set.</span></span>

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a><span data-ttu-id="85649-143">Etapa 1: Criar um grupo de marca inteligente com o modelo de detecção de privilégio advogado-cliente</span><span class="sxs-lookup"><span data-stu-id="85649-143">Step 1: Create a smart tag group with attorney-client privilege detection model</span></span>

<span data-ttu-id="85649-144">Uma das principais maneiras de ver os resultados da detecção de privilégios de cliente potencial em seu processo de revisão é usar um grupo de marca inteligente.</span><span class="sxs-lookup"><span data-stu-id="85649-144">One of the primary ways to see the results of attorney-client privilege detection in your review process is by using a smart tag group.</span></span> <span data-ttu-id="85649-145">Um grupo de marcas inteligentes indica os resultados da detecção de privilégios de cliente para análise e mostra os resultados alinhados ao lado das marcas em um grupo de marcas inteligentes.</span><span class="sxs-lookup"><span data-stu-id="85649-145">A smart tag group indicates the results of the attorney-client privilege detection and shows the results in-line next to the tags in a smart tag group.</span></span> <span data-ttu-id="85649-146">Isso permite identificar rapidamente documentos potencialmente privilegiados durante a revisão de documentos.</span><span class="sxs-lookup"><span data-stu-id="85649-146">This lets you quickly identify potentially privileged documents during document review.</span></span> <span data-ttu-id="85649-147">Além disso, você também pode usar as marcas no grupo de marcas inteligentes para marcar documentos como privilegiados ou não privilegiados.</span><span class="sxs-lookup"><span data-stu-id="85649-147">Additionally, you can also use the tags in the smart tag group to tag documents as privileged or non-privileged.</span></span> <span data-ttu-id="85649-148">Para obter mais informações sobre marcas inteligentes, consulte Configurar marcas [inteligentes em Advanced eDiscovery](smart-tags.md).</span><span class="sxs-lookup"><span data-stu-id="85649-148">For more information about smart tags, see [Set up smart tags in Advanced eDiscovery](smart-tags.md).</span></span>

1. <span data-ttu-id="85649-149">No conjunto de revisão que contém os documentos que  você analisou na Etapa 1, selecione Gerenciar conjunto de revisão e selecione **Gerenciar marcas**.</span><span class="sxs-lookup"><span data-stu-id="85649-149">In the review set that contains the documents that you analyzed in Step 1, select **Manage review set** and then select **Manage tags**.</span></span>
 
2. <span data-ttu-id="85649-150">Em **Marcas,** selecione a pull-down ao lado de **Adicionar grupo** e selecione Adicionar grupo de marca **inteligente**.</span><span class="sxs-lookup"><span data-stu-id="85649-150">Under **Tags**, select the pull-down next to **Add group** and then select **Add smart tag group**.</span></span>

   ![Selecione "Adicionar grupo de marca inteligente"](../media/AeDCreateSmartTag.png)

3. <span data-ttu-id="85649-152">Na página **Escolher um modelo para sua marca inteligente,** escolha **Selecionar** ao lado do **privilégio Advogado-cliente**.</span><span class="sxs-lookup"><span data-stu-id="85649-152">On the **Choose a model for your smart tag** page, choose **Select** next to **Attorney-client privilege**.</span></span>

   <span data-ttu-id="85649-153">Um grupo de marca chamado **Privilégio advogado-cliente** é exibido.</span><span class="sxs-lookup"><span data-stu-id="85649-153">A tag group named **Attorney-client privilege** is displayed.</span></span> <span data-ttu-id="85649-154">Ele contém duas marcas filho chamadas **Positivo** e **Negativo**, que correspondem aos possíveis resultados produzidos pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="85649-154">It contains two child tags named **Positive** and **Negative**, which correspond to the possible results produced by the model.</span></span>

   ![Grupo de marca inteligente de privilégio advogado-cliente](../media/AeDAttorneyClientSmartTagGroup.png)

3. <span data-ttu-id="85649-156">Renomeie o grupo de marcas e as marcas conforme apropriado para sua revisão.</span><span class="sxs-lookup"><span data-stu-id="85649-156">Rename the tag group and tags as appropriate for your review.</span></span> <span data-ttu-id="85649-157">Por exemplo, você pode renomear **Positivo** para **Privilegiado** e **Negativo** para **Não Privilegiado.**</span><span class="sxs-lookup"><span data-stu-id="85649-157">For example, you can rename **Positive** to **Privileged** and **Negative** to **Not privileged**.</span></span>

### <a name="step-2-analyze-a-review-set"></a><span data-ttu-id="85649-158">Etapa 2: Analisar um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="85649-158">Step 2: Analyze a review set</span></span>

<span data-ttu-id="85649-159">Quando você analisa os documentos em um conjunto de revisão, o modelo de detecção de privilégio advogado-cliente também será executado e as propriedades correspondentes (descritas em Como [funciona?](#how-does-it-work) serão adicionadas a cada documento no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="85649-159">When you analyze the documents in a review set, the attorney-client privilege detection model will also run and the corresponding properties (described in [How does it work?](#how-does-it-work) will be added to every document in the review set.</span></span> <span data-ttu-id="85649-160">Para obter mais informações sobre como analisar dados no conjunto de revisão, consulte [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="85649-160">For more information about analyzing data in review set, see [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span></span>

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a><span data-ttu-id="85649-161">Etapa 3: Usar o grupo de marca inteligente para revisão de conteúdo privilegiado</span><span class="sxs-lookup"><span data-stu-id="85649-161">Step 3: Use the smart tag group for review of privileged content</span></span>

<span data-ttu-id="85649-162">Depois de analisar o conjunto de revisão e configurar marcas inteligentes, a próxima etapa é revisar os documentos.</span><span class="sxs-lookup"><span data-stu-id="85649-162">After analyzing the review set and setting up smart tags, the next step is to review the documents.</span></span> <span data-ttu-id="85649-163">Se o modelo tiver determinado que o documento é  potencialmente privilegiado, a marca inteligente correspondente no painel De marcação indicará os seguintes resultados produzidos pela detecção de privilégio advogado-cliente:</span><span class="sxs-lookup"><span data-stu-id="85649-163">If the model has determined the document is potentially privileged, the corresponding smart tag in the **Tagging panel** will indicate the following results produced by the attorney-client privilege detection:</span></span>

- <span data-ttu-id="85649-164">Se o documento tiver conteúdo que possa ser legal, o rótulo **Conteúdo legal** será exibido ao lado da marca inteligente correspondente (que, nesse caso, é a marca **Positiva** padrão).</span><span class="sxs-lookup"><span data-stu-id="85649-164">If the document has content that may be legal in nature, the label **Legal content** is displayed next to the corresponding smart tag (which in this case is the default **Positive** tag).</span></span>

- <span data-ttu-id="85649-165">Se o documento tiver um participante encontrado na lista de advogados da sua organização, o rótulo **Advogado** será exibido ao lado da marca inteligente correspondente (que, nesse caso, também é a marca Positiva **padrão).**</span><span class="sxs-lookup"><span data-stu-id="85649-165">If the document has a participant who is found in your organization's attorney list, the label **Attorney** is displayed next to the corresponding smart tag (which in this case is also the default **Positive** tag).</span></span>

- <span data-ttu-id="85649-166">Se o documento tiver conteúdo que  possa ser legal e tiver um participante  encontrado na lista de advogados, os rótulos Conteúdo **Legal** e Advogado serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="85649-166">If the document has content that may be legal in nature *and* has a participant found in the attorney list, both the **Legal content**  and **Attorney** labels are displayed.</span></span> 

<span data-ttu-id="85649-167">Se o modelo determinar que um documento não contém conteúdo legal ou que não contenha um participante da lista de advogados, nenhum rótulo será exibido no painel de marcação.</span><span class="sxs-lookup"><span data-stu-id="85649-167">If the model determines that a document doesn't contain content that is legal in nature or doesn't contain a participant from the attorney list, then neither label is displayed in the tagging panel.</span></span>

<span data-ttu-id="85649-168">Por exemplo, as capturas de tela a seguir mostram dois documentos.</span><span class="sxs-lookup"><span data-stu-id="85649-168">For example, the following screenshots show two documents.</span></span> <span data-ttu-id="85649-169">O primeiro contém conteúdo legal e tem um participante encontrado na lista de advogados.</span><span class="sxs-lookup"><span data-stu-id="85649-169">The first one contains content that is legal in nature and has a participant found in the list of attorneys.</span></span> <span data-ttu-id="85649-170">O segundo não contém nenhum e, portanto, não exibe rótulos.</span><span class="sxs-lookup"><span data-stu-id="85649-170">The second contains neither and therefore doesn't display any labels.</span></span>

![Documento com rótulos de conteúdo jurídico e advogado](../media/AeDTaggingPanelLegalContentAttorney.png)

![Documento sem rótulos](../media/AeDTaggingPanelNegative.png)

<span data-ttu-id="85649-173">Depois de revisar um documento para ver se ele contém conteúdo privilegiado, você pode marcar o documento com a marca apropriada.</span><span class="sxs-lookup"><span data-stu-id="85649-173">After you review a document to see if it contains privileged content, you can tag the document with the appropriate tag.</span></span>
