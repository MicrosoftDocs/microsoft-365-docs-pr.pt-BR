---
title: Configurar detecção de privilégio de cliente de advogado na descoberta eletrônica avançada
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: Aceite e use o modelo de detecção de privilégio de cliente advogado para usar a detecção baseada em aprendizado de máquina de conteúdo privilegiado ao examinar o conteúdo em uma ocorrência de descoberta eletrônica avançada.
ms.openlocfilehash: 943b788dfea62433f0f6c1dca3b6b105cf92bae8
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072277"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a><span data-ttu-id="87107-103">Configurar detecção de privilégio de cliente de advogado na descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="87107-103">Set up attorney-client privilege detection in Advanced eDiscovery</span></span>

<span data-ttu-id="87107-104">Um aspecto importante e dispendioso da fase de análise de qualquer processo de descoberta eletrônica é a revisão de documentos para conteúdo privilegiado.</span><span class="sxs-lookup"><span data-stu-id="87107-104">A major and costly aspect of the review phase of any eDiscovery process is reviewing documents for privileged content.</span></span> <span data-ttu-id="87107-105">A descoberta eletrônica avançada fornece detecção de conteúdo privilegiado com base em aprendizado de máquina para tornar esse processo mais eficiente.</span><span class="sxs-lookup"><span data-stu-id="87107-105">Advanced eDiscovery provides machine learning-based detection of privileged content to make this process more efficient.</span></span> <span data-ttu-id="87107-106">Esse recurso é chamado *detecção de privilégio de cliente de advogado*.</span><span class="sxs-lookup"><span data-stu-id="87107-106">This feature is called *attorney-client privilege detection*.</span></span>

> [!NOTE]
> <span data-ttu-id="87107-107">Você deve aceitar o modelo de detecção de privilégio de cliente advogado antes de poder usá-lo.</span><span class="sxs-lookup"><span data-stu-id="87107-107">You must opt in to the attorney-client privilege detection model before you can use it.</span></span> <span data-ttu-id="87107-108">Consulte a [etapa 1](#step-1-opt-in-to-attorney-client-privilege-detection) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="87107-108">See [Step 1](#step-1-opt-in-to-attorney-client-privilege-detection) for instructions.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="87107-109">Como funciona?</span><span class="sxs-lookup"><span data-stu-id="87107-109">How does it work?</span></span>

<span data-ttu-id="87107-110">Quando a detecção de privilégio de cliente do advogado estiver habilitada, todos os documentos em um conjunto de análise serão processados pelo modelo de detecção de privilégio de cliente advogado quando você [analisar os dados](analyzing-data-in-review-set.md) no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="87107-110">When attorney-client privilege detection is enabled, all documents in a review set will be processed by the attorney-client privilege detection model when you [analyze the data](analyzing-data-in-review-set.md) in the review set.</span></span> <span data-ttu-id="87107-111">O modelo procura duas coisas:</span><span class="sxs-lookup"><span data-stu-id="87107-111">The model looks for two things:</span></span>

- <span data-ttu-id="87107-112">Conteúdo privilegiado – o modelo usa o Machine Learning para determinar a probabilidade de que o documento contenha conteúdo legal de natureza.</span><span class="sxs-lookup"><span data-stu-id="87107-112">Privileged content – The model uses machine learning to determine the likelihood that the document contains content that is legal in nature.</span></span>

- <span data-ttu-id="87107-113">Participantes – como parte da configuração de detecção de privilégio de cliente de advogado, você precisa enviar uma lista de advogados para sua organização.</span><span class="sxs-lookup"><span data-stu-id="87107-113">Participants – As part of setting up attorney-client privilege detection, you have to submit a list of attorneys for your organization.</span></span> <span data-ttu-id="87107-114">O modelo compara os participantes do documento com a lista advogado para determinar se um documento tem pelo menos um participante advogado.</span><span class="sxs-lookup"><span data-stu-id="87107-114">The model then compares the participants of the document with the attorney list to determine if a document has at least one attorney participant.</span></span>

<span data-ttu-id="87107-115">O modelo produz as três seguintes propriedades para cada documento:</span><span class="sxs-lookup"><span data-stu-id="87107-115">The model produces the following three properties for every document:</span></span>

- <span data-ttu-id="87107-116">**AttorneyClientPrivilegeScore** – a probabilidade de que o documento seja legal por natureza; os valores da Pontuação estão entre **0** e **1**.</span><span class="sxs-lookup"><span data-stu-id="87107-116">**AttorneyClientPrivilegeScore** – The likelihood the document is legal in nature; the values for the score are between **0** and **1**.</span></span>

- <span data-ttu-id="87107-117">**HasAttorney** – essa propriedade será definida como **true** se um dos participantes do documento estiver listado na lista advogado; caso contrário, o valor será **false**.</span><span class="sxs-lookup"><span data-stu-id="87107-117">**HasAttorney** – This property is set to **true** if one of the document participants is listed in the attorney list; otherwise the value is **false**.</span></span> <span data-ttu-id="87107-118">O valor também será definido como **false** se sua organização não tiver carregado uma lista de advogados.</span><span class="sxs-lookup"><span data-stu-id="87107-118">The value is also set to **false** if your organization didn't upload an attorney list.</span></span>

- <span data-ttu-id="87107-119">**Isprivilege** – essa propriedade será definida como **true** se o valor de **AttorneyClientPrivilegeScore** estiver acima do limite *ou* se o documento tiver um participante advogado; caso contrário, o valor é definido como **false**.</span><span class="sxs-lookup"><span data-stu-id="87107-119">**IsPrivilege** – This property is set to **true** if the value for **AttorneyClientPrivilegeScore** is above the threshold *or* if the document has an attorney participant; otherwise the value is set to **false**.</span></span>

<span data-ttu-id="87107-120">Essas propriedades (e seus valores correspondentes) são adicionadas aos metadados de arquivo dos documentos em um conjunto de revisão, conforme mostrado na captura de tela a seguir:</span><span class="sxs-lookup"><span data-stu-id="87107-120">These properties (and their corresponding values) are added to the file metadata of the documents in a review set, as shown in the following screenshot:</span></span>

![Propriedades de privilégio de cliente do advogado mostrados nos metadados do arquivo](media/AeDAttorneyClientPrivilegeMetadata.png)

<span data-ttu-id="87107-122">Essas três propriedades também podem ser pesquisadas em um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="87107-122">These three properties are also searchable within a review set.</span></span> <span data-ttu-id="87107-123">Para obter mais informações, consulte [consultar os dados em um conjunto de revisão](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="87107-123">For more information, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="set-up-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="87107-124">Configurar o modelo de detecção de privilégio de cliente advogado</span><span class="sxs-lookup"><span data-stu-id="87107-124">Set up the attorney-client privilege detection model</span></span>

<span data-ttu-id="87107-125">Para habilitar o modelo de detecção de privilégio de cliente advogado, sua organização deve aceitar e carregar uma lista de advogados.</span><span class="sxs-lookup"><span data-stu-id="87107-125">To enable the attorney-client privilege detection model, your organization has to opt-in and then upload an attorney list.</span></span>

### <a name="step-1-opt-in-to-attorney-client-privilege-detection"></a><span data-ttu-id="87107-126">Etapa 1: aceitar a detecção de privilégio de cliente advogado</span><span class="sxs-lookup"><span data-stu-id="87107-126">Step 1: Opt-in to attorney-client privilege detection</span></span>

<span data-ttu-id="87107-127">Conforme mencionado anteriormente, o modelo de detecção de privilégio de cliente advogado está em visualização.</span><span class="sxs-lookup"><span data-stu-id="87107-127">As previously stated, the attorney-client privilege detection model is in Preview.</span></span> <span data-ttu-id="87107-128">Portanto, uma pessoa em seu administrador de descoberta eletrônica da organização (membro do subgrupo administrador de descoberta eletrônica no grupo de funções Gerenciador de descoberta eletrônica) deve optar por disponibilizar o modelo em suas ocorrências de descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="87107-128">Therefore a person in your organization eDiscovery Administrator (a member of the eDiscovery Administrator subgroup in the eDiscovery Manager role group) must opt in to make the model available in your Advanced eDiscovery cases.</span></span>

1. <span data-ttu-id="87107-129">No centro de conformidade & segurança, vá para **descoberta eletrônica avançada**de descoberta eletrônica >.</span><span class="sxs-lookup"><span data-stu-id="87107-129">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery**.</span></span>

2. <span data-ttu-id="87107-130">Na home page de **descoberta eletrônica avançada** , no bloco **configurações** , clique em **configurar recursos experimentales**.</span><span class="sxs-lookup"><span data-stu-id="87107-130">On the **Advanced eDiscovery** home page, in the **Settings** tile, click **Configure experimental features**.</span></span>

   ![Clique em "configurar recursos experimentais"](media/AeDExperimentalFeatures.png)

3. <span data-ttu-id="87107-132">Na guia **recursos experimentales** , clique em **gerenciar definição de privilégio de cliente do advogado**.</span><span class="sxs-lookup"><span data-stu-id="87107-132">On the **Experimental features** tab, click **Manage attorney-client privilege setting**.</span></span>

4. <span data-ttu-id="87107-133">Na página do submenu de **privilégio de cliente do advogado** , clique no botão de alternância para ativar o recurso e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="87107-133">On the **Attorney-client privilege** flyout page, click the toggle to turn on the feature and then click **Save**.</span></span>

### <a name="step-2-upload-a-list-of-attorneys-optional"></a><span data-ttu-id="87107-134">Etapa 2: carregar uma lista de advogados (opcional)</span><span class="sxs-lookup"><span data-stu-id="87107-134">Step 2: Upload a list of attorneys (optional)</span></span>

<span data-ttu-id="87107-135">Para aproveitar ao máximo o modelo de detecção de privilégio do advogado-Client e usar os resultados da detecção de **advogado ou com** **privilégios possíveis** descritos anteriormente, recomendamos carregar uma lista de endereços de email para o advogados e pessoas jurídicas que trabalham para sua organização.</span><span class="sxs-lookup"><span data-stu-id="87107-135">To take full advantage of the attorney-client privilege detection model and use the results of the **Has Attorney** or **Potentially Privileged** detection that was previously described, we recommend that you upload a list of email addresses for the lawyers and legal personnel who work for your organization.</span></span> 

<span data-ttu-id="87107-136">Para carregar uma lista de advogados para uso pelo modelo de detecção de privilégio de cliente advogado:</span><span class="sxs-lookup"><span data-stu-id="87107-136">To upload an attorney list for use by the attorney-client privilege detection model:</span></span>

1. <span data-ttu-id="87107-137">Crie um arquivo. csv (sem uma linha de cabeçalho) e adicione o endereço de email de cada pessoa apropriada em uma linha separada.</span><span class="sxs-lookup"><span data-stu-id="87107-137">Create a .csv file (without a header row) and add the email address for each appropriate person on a separate line.</span></span> <span data-ttu-id="87107-138">Salve esse arquivo no computador local.</span><span class="sxs-lookup"><span data-stu-id="87107-138">Save this file to your local computer.</span></span>

2. <span data-ttu-id="87107-139">Na home page de **descoberta eletrônica avançada** , no bloco **configurações** , clique em **configurar recursos experimentais**e, em seguida, clique em **gerenciar definição de privilégio de cliente**.</span><span class="sxs-lookup"><span data-stu-id="87107-139">On the **Advanced eDiscovery** home page, in the **Settings** tile, click **Configure experimental features**, and then click **Manage attorney-client privilege setting**.</span></span>

   <span data-ttu-id="87107-140">A página de **privilégio advogado-cliente** é exibida, e a opção de **detecção de privilégio advogado-cliente** é ativada.</span><span class="sxs-lookup"><span data-stu-id="87107-140">The **Attorney-client privilege** page is displayed, and the **Attorney-client privilege detection** toggle is turned on.</span></span>

   ![Página de submenu de privilégio de cliente do advogado](media/AeDUploadAttorneyList.png)

3. <span data-ttu-id="87107-142">Clique em **procurar** e, em seguida, localize e selecione o arquivo. csv que você criou na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="87107-142">Click **Browse** and then find and select the .csv file that you created in step 1.</span></span>

4. <span data-ttu-id="87107-143">Clique em **salvar** para carregar a lista advogado.</span><span class="sxs-lookup"><span data-stu-id="87107-143">Click **Save** to upload the attorney list.</span></span>

## <a name="use-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="87107-144">Usar o modelo de detecção de privilégio de cliente advogado</span><span class="sxs-lookup"><span data-stu-id="87107-144">Use the attorney-client privilege detection model</span></span>

<span data-ttu-id="87107-145">Siga as etapas desta seção para usar a detecção de privilégio de cliente de advogados para documentos em um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="87107-145">Follow the steps in this section to use attorney-client privilege detection for documents in a review set.</span></span>

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a><span data-ttu-id="87107-146">Etapa 1: criar um grupo de marcas inteligentes com modelo de detecção de privilégio de cliente advogado</span><span class="sxs-lookup"><span data-stu-id="87107-146">Step 1: Create a smart tag group with attorney-client privilege detection model</span></span>

<span data-ttu-id="87107-147">Uma das principais maneiras de ver os resultados da detecção de privilégio de cliente de advogados no processo de revisão é usar um grupo de marcas inteligentes.</span><span class="sxs-lookup"><span data-stu-id="87107-147">One of the primary ways to see the results of attorney-client privilege detection in your review process is by using a smart tag group.</span></span> <span data-ttu-id="87107-148">Um grupo de marcas inteligentes indica os resultados da detecção de privilégio de cliente advogado e mostra os resultados em linha ao lado das marcas em um grupo de marcas inteligentes.</span><span class="sxs-lookup"><span data-stu-id="87107-148">A smart tag group indicates the results of the attorney-client privilege detection and shows the results in-line next to the tags in a smart tag group.</span></span> <span data-ttu-id="87107-149">Isso permite identificar rapidamente documentos potencialmente privilegiados durante a revisão do documento.</span><span class="sxs-lookup"><span data-stu-id="87107-149">This lets you quickly identify potentially privileged documents during document review.</span></span> <span data-ttu-id="87107-150">Além disso, você também pode usar as marcas no grupo de marcas inteligentes para marcar documentos como privilegiados ou não privilegiados.</span><span class="sxs-lookup"><span data-stu-id="87107-150">Additionally, you can also use the tags in the smart tag group to tag documents as privileged or non-privileged.</span></span> <span data-ttu-id="87107-151">Para obter mais informações sobre marcas inteligentes, consulte [Configurar marcas inteligentes na descoberta eletrônica avançada](smart-tags.md).</span><span class="sxs-lookup"><span data-stu-id="87107-151">For more information about smart tags, see [Set up smart tags in Advanced eDiscovery](smart-tags.md).</span></span>

1. <span data-ttu-id="87107-152">No conjunto de revisão que contém os documentos analisados na etapa 1, clique em **gerenciar o conjunto de revisão** e, em seguida, clique em **gerenciar marcas**.</span><span class="sxs-lookup"><span data-stu-id="87107-152">In the review set that contains the documents that you analyzed in Step 1, click **Manage review set** and then click **Manage tags**.</span></span>
 
2. <span data-ttu-id="87107-153">Em **marcas**, clique na parte suspensa ao lado de **Adicionar grupo** e, em seguida, clique em **Adicionar grupo de marcas inteligentes**.</span><span class="sxs-lookup"><span data-stu-id="87107-153">Under **Tags**, click the pull-down next to **Add group** and then click **Add smart tag group**.</span></span>

   ![Clique em "Adicionar grupo de marcas inteligentes"](media/AeDCreateSmartTag.png)

3. <span data-ttu-id="87107-155">Na página **escolha um modelo para a marca inteligente** , clique em **selecionar** ao lado de **privilégio advogado-cliente**.</span><span class="sxs-lookup"><span data-stu-id="87107-155">On the **Choose a model for your smart tag** page, click **Select** next to **Attorney-client privilege**.</span></span>

   <span data-ttu-id="87107-156">Um grupo de marcas chamado **privilégio advogado-cliente** é exibido.</span><span class="sxs-lookup"><span data-stu-id="87107-156">A tag group named **Attorney-client privilege** is displayed.</span></span> <span data-ttu-id="87107-157">Ele contém duas marcas filhas chamadas **positiva** e **negativas**, que correspondem aos resultados possíveis produzidos pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="87107-157">It contains two child tags named **Positive** and **Negative**, which correspond to the possible results produced by the model.</span></span>

   ![Grupo de marcas inteligentes de privilégio de cliente advogado](media/AeDAttorneyClientSmartTagGroup.png)

3. <span data-ttu-id="87107-159">Renomeie o grupo de marcas e as marcas conforme apropriado para sua revisão.</span><span class="sxs-lookup"><span data-stu-id="87107-159">Rename the tag group and tags as appropriate for your review.</span></span> <span data-ttu-id="87107-160">Por exemplo, você pode renomear **positivo** como **privilegiado** e **negativo** para **não privilegiado**.</span><span class="sxs-lookup"><span data-stu-id="87107-160">For example, you can rename **Positive** to **Privileged** and **Negative** to **Not privileged**.</span></span>

### <a name="step-2-analyze-a-review-set"></a><span data-ttu-id="87107-161">Etapa 2: analisar um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="87107-161">Step 2: Analyze a review set</span></span>

<span data-ttu-id="87107-162">Quando você analisa os documentos em um conjunto de revisão, o modelo de detecção de privilégio advogado-cliente também será executado e as propriedades correspondentes (descritas em[como funciona?](#how-does-it-work) serão adicionadas a todos os documentos do conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="87107-162">When you analyze the documents in a review set, the attorney-client privilege detection model will also be run and the corresponding properties (described in[How does it work?](#how-does-it-work) will be added to every document in the review set.</span></span> <span data-ttu-id="87107-163">Para obter mais informações sobre a análise de dados no conjunto de revisão, consulte [analisar dados em uma revisão definida em descoberta eletrônica avançada](analyzing-data-in-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="87107-163">For more information about analyzing data in review set, see [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span></span>

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a><span data-ttu-id="87107-164">Etapa 3: usar o grupo de marcas inteligentes para análise de conteúdo privilegiado</span><span class="sxs-lookup"><span data-stu-id="87107-164">Step 3: Use the smart tag group for review of privileged content</span></span>

<span data-ttu-id="87107-165">Após analisar o conjunto de revisão e configurar marcas inteligentes, a próxima etapa é revisar os documentos.</span><span class="sxs-lookup"><span data-stu-id="87107-165">After analyzing the review set and setting up smart tags, the next step is to review the documents.</span></span> <span data-ttu-id="87107-166">Se o modelo tiver determinado que o documento é potencialmente privilegiado, a marca inteligente correspondente no **painel de marcação** indicará os seguintes resultados produzidos pela detecção de privilégio advogado-cliente:</span><span class="sxs-lookup"><span data-stu-id="87107-166">If the model has determined the document is potentially privileged, the corresponding smart tag in the **Tagging panel** will indicate the following results produced by the attorney-client privilege detection:</span></span>

- <span data-ttu-id="87107-167">Se o documento tiver conteúdo que possa ser de natureza legal, o **conteúdo legal** do rótulo será exibido ao lado da marca inteligente correspondente (que neste caso é a marca **positiva** padrão).</span><span class="sxs-lookup"><span data-stu-id="87107-167">If the document has content that may be legal in nature, the label **Legal content** is displayed next to the corresponding smart tag (which in this case is the default **Positive** tag).</span></span>

- <span data-ttu-id="87107-168">Se o documento tiver um participante encontrado na lista de advogados da sua organização, o **advogado** do rótulo será exibido ao lado da marca inteligente correspondente (que neste caso também é a marca **positiva** padrão).</span><span class="sxs-lookup"><span data-stu-id="87107-168">If the document has a participant who is found in your organization's attorney list, the label **Attorney** is displayed next to the corresponding smart tag (which in this case is also the default **Positive** tag).</span></span>

- <span data-ttu-id="87107-169">Se o documento tiver conteúdo que possa ser legal por natureza *e* tiver um participante encontrado na lista de advogados, tanto o **conteúdo legal** como os rótulos de **advogado** serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="87107-169">If the document has content that may be legal in nature *and* has a participant found in the attorney list, both the **Legal content**  and **Attorney** labels are displayed.</span></span> 

<span data-ttu-id="87107-170">Se o modelo determinar que um documento não contém conteúdo legal ou que não contenha um participante da lista advogado, nenhum rótulo será exibido no painel de marcação.</span><span class="sxs-lookup"><span data-stu-id="87107-170">If the model determines that a document doesn't contain content that is legal in nature or doesn't contain a participant from the attorney list, then neither label is displayed in the tagging panel.</span></span>

<span data-ttu-id="87107-171">Por exemplo, as capturas de tela a seguir mostram dois documentos; o primeiro contém conteúdo que é legal e tem um participante encontrado na lista de advogados; o segundo não contém e, portanto, não exibe nenhum rótulo.</span><span class="sxs-lookup"><span data-stu-id="87107-171">For example, the following screenshots show two documents; the first one contains content that is legal in nature and has a participant found in the list of attorneys; the second contains neither and therefore doesn't display any labels.</span></span>

![Documento com rótulos de conteúdo legal e advogado](media/AeDTaggingPanelLegalContentAttorney.png)

![Documento sem rótulos](media/AeDTaggingPanelNegative.png)

<span data-ttu-id="87107-174">Após revisar um documento para ver se ele contém conteúdo privilegiado, você pode marcar o documento com a marca apropriada.</span><span class="sxs-lookup"><span data-stu-id="87107-174">After you review a document to see if it contains privileged content, you can tag the document with the appropriate tag.</span></span>