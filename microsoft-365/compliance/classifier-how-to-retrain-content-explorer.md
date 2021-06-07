---
title: Como treinar novamente um classificador no explorador de conteúdo
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Saiba como fornecer comentários a um classificador treinável no Explorador de conteúdo.
ms.openlocfilehash: ef0539a3d474ffecaeac8633b4a58aa068a5c182
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793059"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="6e8ba-103">Como treinar novamente um classificador no explorador de conteúdo</span><span class="sxs-lookup"><span data-stu-id="6e8ba-103">How to retrain a classifier in content explorer</span></span>

<span data-ttu-id="6e8ba-104">Um Microsoft 365 classificador treinável é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo, dando a ele exemplos para ver.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="6e8ba-105">Depois de treinado, você pode usá-lo para identificar o item para a aplicação de rótulos de Office de sensibilidade, políticas de conformidade de comunicações e políticas de rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="6e8ba-106">Este artigo mostra como melhorar o desempenho de classificadores treinados personalizados e alguns classificadores pré-treinados fornecendo comentários adicionais.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="6e8ba-107">Para saber mais sobre os diferentes tipos de classificadores, consulte [Learn about trainable classifiers](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="6e8ba-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

<span data-ttu-id="6e8ba-108">Assista a este vídeo para um resumo rápido do processo de ajuste e retreinamento.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-108">Watch this video for a quick summary of the tuning and retraining process.</span></span> <span data-ttu-id="6e8ba-109">Você ainda precisará ler este artigo completo para obter os detalhes.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-109">You'll still need to read this full article to get the details.</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGMs]


## <a name="permissions"></a><span data-ttu-id="6e8ba-110">Permissões</span><span class="sxs-lookup"><span data-stu-id="6e8ba-110">Permissions</span></span>

<span data-ttu-id="6e8ba-111">Para acessar classificadores no centro Microsoft 365 Conformidade:</span><span class="sxs-lookup"><span data-stu-id="6e8ba-111">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="6e8ba-112">a função de administrador de conformidade ou Administrador de Dados de Conformidade é necessária para treinar um classificador</span><span class="sxs-lookup"><span data-stu-id="6e8ba-112">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="6e8ba-113">Você precisará de contas com essas permissões para usar classificadores nesses cenários:</span><span class="sxs-lookup"><span data-stu-id="6e8ba-113">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="6e8ba-114">Cenário de política de rótulo de retenção: funções de Gerenciamento de Registros e Gerenciamento de Retenção</span><span class="sxs-lookup"><span data-stu-id="6e8ba-114">Retention label policy scenario: Record Management and Retention Management roles</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="6e8ba-115">Fluxo de trabalho geral</span><span class="sxs-lookup"><span data-stu-id="6e8ba-115">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e8ba-116">Você fornece comentários no explorador de conteúdo para aplicar automaticamente políticas de rótulo de retenção Exchange itens e usa o classificador como uma condição.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-116">You provide feedback in content explorer for auto-apply retention label policies to Exchange items and uses the classifier as a condition.</span></span> <span data-ttu-id="6e8ba-117">**Se você não tiver uma política de retenção que aplique automaticamente um rótulo de retenção Exchange itens e use um classificador como condição, pare aqui.**</span><span class="sxs-lookup"><span data-stu-id="6e8ba-117">**If you don't have a retention policy that auto-applies a retention label to Exchange items and      uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="6e8ba-118">À medida que você usa seus classificadores, talvez você queira aumentar a precisão das classificações que eles estão fazendo.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-118">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="6e8ba-119">Você faz isso avaliando a qualidade das classificações feitas para itens identificados como sendo uma combinação ou não uma combinação.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-119">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="6e8ba-120">Depois de fazer 30 avaliações para um classificador, ele recebe os comentários e se retreina automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-120">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="6e8ba-121">Para entender mais sobre o fluxo de trabalho geral de retreinamento de um classificador, consulte Fluxo de processos para [retreinar um classificador](classifier-learn-about.md#retraining-classifiers).</span><span class="sxs-lookup"><span data-stu-id="6e8ba-121">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="6e8ba-122">Um classificador já deve ser publicado e em uso antes de poder ser retreinado.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-122">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="6e8ba-123">Como treinar novamente um classificador no explorador de conteúdo</span><span class="sxs-lookup"><span data-stu-id="6e8ba-123">How to retrain a classifier in content explorer</span></span>

1. <span data-ttu-id="6e8ba-124">Entre no centro Microsoft 365 de conformidade com o administrador de conformidade ou acesso **à** função de administrador de segurança e abra Microsoft 365 centro de conformidade  >  **Data classification**  >  **Data classification Explorador de conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-124">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Data classification** > **Content explorer**.</span></span> 
2. <span data-ttu-id="6e8ba-125">Na lista **Filtrar rótulos, tipos de informações ou** **categorias,** expanda classificadores com treinamento.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-125">Under the **Filter on labels, info types, or categories** list, expand **Trainable classifiers**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e8ba-126">Pode levar até oito dias para que os itens agregados apareçam sob o título de classificadores treináveis.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-126">It can take up to eight days for aggregated items to appear under the trainable classifiers heading.</span></span>

3. <span data-ttu-id="6e8ba-127">Escolha o classificador treinável que você usou em sua política de rótulo de retenção de aplicação automática.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-127">Choose the trainable classifier you used in you auto-apply retention label policy.</span></span> <span data-ttu-id="6e8ba-128">Este é o classificador treinável sobre o que você dará comentários.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-128">This is the trainable classifier you will give feedback on.</span></span>

> [!NOTE]
> <span data-ttu-id="6e8ba-129">Se um item tiver uma entrada na coluna **Rótulo de** retenção, isso significa que o item foi classificado como `match` um .</span><span class="sxs-lookup"><span data-stu-id="6e8ba-129">If an item has an entry in the **Retention label** column, it means that the item was classified as a `match`.</span></span>  <span data-ttu-id="6e8ba-130">Se um item não tiver uma entrada na coluna **Rótulo** de retenção, isso significa que ele foi classificado como `close match` um .</span><span class="sxs-lookup"><span data-stu-id="6e8ba-130">If an item doesn't have an entry in the **Retention label** column, it means it was classified as a `close match`.</span></span> <span data-ttu-id="6e8ba-131">Você pode melhorar mais a precisão do classificador fornecendo comentários sobre `close match` itens.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-131">You can improve the classifier precision the most by providing feedback on `close match` items.</span></span> 

4. <span data-ttu-id="6e8ba-132">Escolha um item e abra-o.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-132">Choose an item and open it.</span></span>
 
 > [!TIP]
> <span data-ttu-id="6e8ba-133">Você pode fornecer comentários sobre vários itens simultaneamente escolhendo-os todos e escolhendo **Melhorar a classificação** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-133">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Improve classification** in the command bar.</span></span>

5. <span data-ttu-id="6e8ba-134">Escolha **Fornecer comentários**.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-134">Choose **Provide feedback**.</span></span>
6. <span data-ttu-id="6e8ba-135">No painel **comentários detalhados,** se o item for um verdadeiro positivo, escolha, **Corresponder**.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-135">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="6e8ba-136">Se o item for um falso positivo, ou seja, ele foi incluído incorretamente na categoria, escolha **Não uma combinação**.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-136">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
7. <span data-ttu-id="6e8ba-137">Se houver outro classificador que seria mais apropriado para o item, você pode escolher-o na lista Sugerir outros classificadores **treináveis.**</span><span class="sxs-lookup"><span data-stu-id="6e8ba-137">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="6e8ba-138">Isso disparará o outro classificador para avaliar o item.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-138">This will trigger the other classifier to evaluate the item.</span></span>
8. <span data-ttu-id="6e8ba-139">Escolha **Enviar comentários** para enviar sua avaliação das `match` classificações , e sugerir outros `not a match` classificadores com treinamento.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-139">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="6e8ba-140">Quando você forneceu 30 instâncias de comentários para um classificador, ele será retreinado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-140">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="6e8ba-141">A retreinamento pode levar de uma a quatro horas.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-141">Retraining can take from one to four hours.</span></span> <span data-ttu-id="6e8ba-142">Os classificadores só podem ser retreinados duas vezes por dia.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-142">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e8ba-143">Essas informações vão para o classificador em seu locatário, **ela não volta para a Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-143">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

9. <span data-ttu-id="6e8ba-144">Abra **classificadores com treinamento.**</span><span class="sxs-lookup"><span data-stu-id="6e8ba-144">Open **Trainable classifiers**.</span></span>
10. <span data-ttu-id="6e8ba-145">O classificador que foi usado em sua política de conformidade de Comunicações aparecerá sob o **título Re-training.**</span><span class="sxs-lookup"><span data-stu-id="6e8ba-145">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![classificador no status de retreinamento](../media/classifier-retraining.png)

11. <span data-ttu-id="6e8ba-147">Depois de concluir a retreinamento, escolha o classificador para abrir a visão geral de retreinamento.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-147">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![visão geral dos resultados de retreinamento do classificador](../media/classifier-retraining-overview.png)

12. <span data-ttu-id="6e8ba-149">Revise a ação recomendada e as comparações de previsão das versões retreinadas e publicadas no momento do classificador.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-149">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
13. <span data-ttu-id="6e8ba-150">Se você estiver satisfeito com os resultados da retreinamento, escolha **Publicar de novo.**</span><span class="sxs-lookup"><span data-stu-id="6e8ba-150">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
14. <span data-ttu-id="6e8ba-151">Se você não estiver satisfeito com os resultados do retreinamento, poderá optar por fornecer comentários adicionais ao classificador na interface do Explorador de Conteúdo e iniciar outro ciclo de retreinamento ou não fazer nada nesse caso, caso em que a versão publicada no momento do classificador continuará a ser usada.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-151">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Content Explorer interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="6e8ba-152">Detalhes sobre recomendações de redação</span><span class="sxs-lookup"><span data-stu-id="6e8ba-152">Details on republishing recommendations</span></span>

<span data-ttu-id="6e8ba-153">Aqui estão algumas informações sobre como formulamos a recomendação para publicar um classificador retreinado ou sugerir um novo treinamento.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-153">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="6e8ba-154">Isso requer uma compreensão um pouco mais profunda de como os classificadores treináveis funcionam.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-154">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="6e8ba-155">Após um retreinamento, avaliamos o desempenho do classificador nos itens com comentários, bem como em todos os itens originalmente usados para treinar o classificador.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-155">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="6e8ba-156">Para modelos integrados, os itens usados para treinar o classificador são os itens usados pela Microsoft para criar o modelo.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-156">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="6e8ba-157">Para modelos personalizados, os itens usados no treinamento original do classificador são dos sites que você adicionou para teste e revisão.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-157">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="6e8ba-158">Comparamos os números de desempenho em ambos os conjuntos de itens para o classificador retreinado e publicado para fornecer uma recomendação sobre se houve melhoria para republicar.</span><span class="sxs-lookup"><span data-stu-id="6e8ba-158">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="6e8ba-159">Confira também</span><span class="sxs-lookup"><span data-stu-id="6e8ba-159">See also</span></span>

- [<span data-ttu-id="6e8ba-160">Saiba mais sobre classificadores treináveis</span><span class="sxs-lookup"><span data-stu-id="6e8ba-160">Learn about trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="6e8ba-161">Extensões de nome de arquivo rastreado padrão e tipos de arquivos analisados no SharePoint Server Server</span><span class="sxs-lookup"><span data-stu-id="6e8ba-161">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)