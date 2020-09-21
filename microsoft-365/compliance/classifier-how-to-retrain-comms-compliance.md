---
title: Como treinar novamente um classificador em conformidade de comunicações (visualização)
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
description: Saiba como fornecer comentários para um classificador treinado em conformidade com comunicações.
ms.openlocfilehash: 1466c211e3a4958f58a7c1f1a6a5a77bed881d60
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132293"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance-preview"></a><span data-ttu-id="41250-103">Como treinar novamente um classificador em conformidade de comunicações (visualização)</span><span class="sxs-lookup"><span data-stu-id="41250-103">How to retrain a classifier in communications compliance (preview)</span></span>

<span data-ttu-id="41250-104">Um classificador Microsoft 365 treinado é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo dando amostras a eles.</span><span class="sxs-lookup"><span data-stu-id="41250-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="41250-105">Depois de treinado, você pode usá-lo para identificar o item para a aplicação de rótulos de confidencialidade do Office, políticas de conformidade de comunicações e políticas de rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="41250-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="41250-106">Este artigo mostra como melhorar o desempenho de classificadores treinados personalizados e alguns classificadores pré-qualificados, fornecendo comentários adicionais.</span><span class="sxs-lookup"><span data-stu-id="41250-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="41250-107">Para saber mais sobre os diferentes tipos de classificadores, confira [saiba mais sobre classificadores estagiários (visualização)](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="41250-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="41250-108">Permissões</span><span class="sxs-lookup"><span data-stu-id="41250-108">Permissions</span></span>

<span data-ttu-id="41250-109">Para acessar classificadores no centro de conformidade da Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="41250-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="41250-110">a função de administrador de conformidade ou o administrador de dados de conformidade é necessário para treinar um classificador</span><span class="sxs-lookup"><span data-stu-id="41250-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="41250-111">Você precisará de contas com essas permissões para usar classificadores nestes cenários:</span><span class="sxs-lookup"><span data-stu-id="41250-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="41250-112">Cenário de política de conformidade de comunicação: administração de gerenciamento de risco do Insider, administrador de análise de supervisão</span><span class="sxs-lookup"><span data-stu-id="41250-112">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="41250-113">Fluxo de trabalho geral</span><span class="sxs-lookup"><span data-stu-id="41250-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="41250-114">Você fornece comentários na solução de conformidade que está usando o classificador como uma condição.</span><span class="sxs-lookup"><span data-stu-id="41250-114">You provide feedback in the compliance solution that is using the classifier as a condition.</span></span> <span data-ttu-id="41250-115">**Se você não tiver uma política de conformidade de comunicações que usa um classificador como condição, pare aqui.**</span><span class="sxs-lookup"><span data-stu-id="41250-115">**If you don't have a communications compliance policy that uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="41250-116">Ao usar seus classificadores, convém aumentar a precisão das classificações que eles estão fazendo.</span><span class="sxs-lookup"><span data-stu-id="41250-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="41250-117">Para fazer isso, avalie a qualidade das classificações feitas para os itens identificados como uma correspondência ou não com uma correspondência.</span><span class="sxs-lookup"><span data-stu-id="41250-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="41250-118">Depois de fazer 30 avaliações de um classificador, o resultado é que ele se retreina automaticamente.</span><span class="sxs-lookup"><span data-stu-id="41250-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="41250-119">Para entender mais sobre o fluxo de trabalho geral do retreinamento de um classificador, confira o [fluxo de processo para treinar novamente um classificador](classifier-learn-about.md#retraining-classifiers).</span><span class="sxs-lookup"><span data-stu-id="41250-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="41250-120">Um classificador já deve estar publicado e em uso para que possa ser retreinado.</span><span class="sxs-lookup"><span data-stu-id="41250-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies-preview"></a><span data-ttu-id="41250-121">Como treinar novamente um classificador em políticas de conformidade de comunicação (visualização)</span><span class="sxs-lookup"><span data-stu-id="41250-121">How to retrain a classifier in communication compliance policies (preview)</span></span>

1. <span data-ttu-id="41250-122">Abra a política de conformidade de comunicação que usa um classificador como uma condição e escolha um dos itens identificados da lista **pendente** .</span><span class="sxs-lookup"><span data-stu-id="41250-122">Open the Communication compliance policy that uses a classifier as a condition and choose one of the identified items from the **Pending** list.</span></span>
2. <span data-ttu-id="41250-123">Escolha as reticências e **aprimore a classificação**.</span><span class="sxs-lookup"><span data-stu-id="41250-123">Choose the ellipsis and **Improve classification**.</span></span>
3. <span data-ttu-id="41250-124">No painel de **comentários detalhado** , se o item for um verdadeiro positivo, escolha, **corresponder**.</span><span class="sxs-lookup"><span data-stu-id="41250-124">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="41250-125">Se o item for um falso positivo, ele foi incorretamente incluído na categoria, escolha **não uma correspondência**.</span><span class="sxs-lookup"><span data-stu-id="41250-125">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
4. <span data-ttu-id="41250-126">Se houver outro classificador que seria mais apropriado para o item, você pode escolher a partir da lista **sugerir outros classificadores estagiários** .</span><span class="sxs-lookup"><span data-stu-id="41250-126">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="41250-127">Isso disparará o outro classificador para avaliar o item.</span><span class="sxs-lookup"><span data-stu-id="41250-127">This will trigger the other classifier to evaluate the item.</span></span>

> [!TIP]
> <span data-ttu-id="41250-128">Você pode fornecer comentários sobre vários itens simultaneamente escolhendo todos eles e escolhendo **fornecer comentários detalhados** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="41250-128">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Provide detailed feedback** in the command bar.</span></span>

5. <span data-ttu-id="41250-129">Escolha **enviar comentários** para enviar sua avaliação do `match` , `not a match` classificações e sugerir outros classificadores estagiários.</span><span class="sxs-lookup"><span data-stu-id="41250-129">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="41250-130">Quando você fornecer 30 instâncias de comentários para um classificador, ele será automaticamente retreinada.</span><span class="sxs-lookup"><span data-stu-id="41250-130">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="41250-131">O retreinamento pode levar de 1-4 horas.</span><span class="sxs-lookup"><span data-stu-id="41250-131">Retraining can take from 1-4 hours.</span></span> <span data-ttu-id="41250-132">Os classificadores só podem ser retreinados duas vezes por dia.</span><span class="sxs-lookup"><span data-stu-id="41250-132">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="41250-133">Essas informações vão para o classificador no locatário, **não volta para a Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="41250-133">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

6.  <span data-ttu-id="41250-134">Abra a página de **classificação de dados** no centro de **conformidade da Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="41250-134">Open the **Data classification** page in the **Microsoft 365 compliance center**.</span></span>
7. <span data-ttu-id="41250-135">Abra **classificadores estagiários (visualização)**.</span><span class="sxs-lookup"><span data-stu-id="41250-135">Open **Trainable classifiers (preview)**.</span></span>
8. <span data-ttu-id="41250-136">O classificador que foi usado na política de conformidade de comunicações aparecerá sob o título de **novo treinamento** .</span><span class="sxs-lookup"><span data-stu-id="41250-136">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![classificador no status de retreinamento](../media/classifier-retraining.png)

9. <span data-ttu-id="41250-138">Após o destreinamento ser concluído, escolha o classificador para abrir a visão geral do retreinamento.</span><span class="sxs-lookup"><span data-stu-id="41250-138">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![Visão geral dos resultados do retreinamento do classificador](../media/classifier-retraining-overview.png)

10. <span data-ttu-id="41250-140">Revise a ação recomendada e as comparações de previsão das versões retreinadas e publicadas atualmente do classificador.</span><span class="sxs-lookup"><span data-stu-id="41250-140">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
11. <span data-ttu-id="41250-141">Se você estiver satisfeito com os resultados do novo treinamento, escolha **republicar**.</span><span class="sxs-lookup"><span data-stu-id="41250-141">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
12. <span data-ttu-id="41250-142">Se você não estiver satisfeito com os resultados do retreinamento, poderá optar por fornecer comentários adicionais para o classificador na interface de conformidade de comunicações e iniciar outro ciclo de treinamento ou não fazer nada, caso a versão atualmente publicada do classificador continue a ser usada.</span><span class="sxs-lookup"><span data-stu-id="41250-142">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="41250-143">Detalhes sobre como republicar recomendações</span><span class="sxs-lookup"><span data-stu-id="41250-143">Details on republishing recommendations</span></span>

<span data-ttu-id="41250-144">Veja aqui algumas informações sobre como formulamos a recomendação para republicar um classificador retreinado ou sugerir um novo treinamento.</span><span class="sxs-lookup"><span data-stu-id="41250-144">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="41250-145">Isso requer uma compreensão mais profunda de como os classificadores de treinamento funcionam.</span><span class="sxs-lookup"><span data-stu-id="41250-145">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="41250-146">Após um retreinamento, avaliamos o desempenho do classificador nos dois itens com comentários, bem como qualquer item usado originalmente para treinar o classificador.</span><span class="sxs-lookup"><span data-stu-id="41250-146">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="41250-147">Para os modelos internos, os itens usados para treinar o classificador são os itens usados pela Microsoft para criar o modelo.</span><span class="sxs-lookup"><span data-stu-id="41250-147">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="41250-148">Para modelos personalizados, os itens usados no treinamento original o classificador são dos sites que você adicionou para teste e análise.</span><span class="sxs-lookup"><span data-stu-id="41250-148">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="41250-149">Comparamos os números de desempenho em ambos os conjuntos de itens para o classificador retreinado e publicado para fornecer uma recomendação sobre se houvesse melhorias na republicação.</span><span class="sxs-lookup"><span data-stu-id="41250-149">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="41250-150">Confira também</span><span class="sxs-lookup"><span data-stu-id="41250-150">See also</span></span>

- [<span data-ttu-id="41250-151">Saiba mais sobre classificadores estagiários (visualização)</span><span class="sxs-lookup"><span data-stu-id="41250-151">Learn about trainable classifiers (preview)</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="41250-152">Extensões de nome de arquivo rastreado padrão e tipos de arquivos analisados no SharePoint Server Server</span><span class="sxs-lookup"><span data-stu-id="41250-152">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
