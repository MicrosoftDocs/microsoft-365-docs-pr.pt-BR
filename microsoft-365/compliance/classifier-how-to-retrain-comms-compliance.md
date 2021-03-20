---
title: Como treinar novamente um classificador em conformidade de comunicações
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
description: Saiba como fornecer comentários a um classificador treinável em conformidade com comunicações.
ms.openlocfilehash: 75fff8220b052618c70a6490b8c3569c11ecc861
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918142"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance"></a><span data-ttu-id="adae0-103">Como treinar novamente um classificador em conformidade de comunicações</span><span class="sxs-lookup"><span data-stu-id="adae0-103">How to retrain a classifier in communications compliance</span></span>

<span data-ttu-id="adae0-104">Um classificador de treinamento do Microsoft 365 é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo, dando a ele exemplos para ver.</span><span class="sxs-lookup"><span data-stu-id="adae0-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="adae0-105">Depois de treinado, você pode usá-lo para identificar o item para a aplicação de rótulos de sensibilidade do Office, políticas de conformidade de comunicações e políticas de rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="adae0-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="adae0-106">Este artigo mostra como melhorar o desempenho de classificadores treinados personalizados e alguns classificadores pré-treinados fornecendo comentários adicionais.</span><span class="sxs-lookup"><span data-stu-id="adae0-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="adae0-107">Para saber mais sobre os diferentes tipos de classificadores, consulte [Learn about trainable classifiers](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="adae0-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="adae0-108">Permissões</span><span class="sxs-lookup"><span data-stu-id="adae0-108">Permissions</span></span>

<span data-ttu-id="adae0-109">Para acessar classificadores no Centro de Conformidade do Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="adae0-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="adae0-110">a função de administrador de conformidade ou Administrador de Dados de Conformidade é necessária para treinar um classificador</span><span class="sxs-lookup"><span data-stu-id="adae0-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="adae0-111">Você precisará de contas com essas permissões para usar classificadores nesses cenários:</span><span class="sxs-lookup"><span data-stu-id="adae0-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="adae0-112">Cenário de política de conformidade de comunicação: Administrador de Gerenciamento de Riscos do Insider, Administrador de Revisão de Supervisão</span><span class="sxs-lookup"><span data-stu-id="adae0-112">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="adae0-113">Fluxo de trabalho geral</span><span class="sxs-lookup"><span data-stu-id="adae0-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="adae0-114">Você fornece comentários na solução de conformidade que está usando o classificador como uma condição.</span><span class="sxs-lookup"><span data-stu-id="adae0-114">You provide feedback in the compliance solution that is using the classifier as a condition.</span></span> <span data-ttu-id="adae0-115">**Se você não tiver uma política de conformidade de comunicações que use um classificador como condição, pare aqui.**</span><span class="sxs-lookup"><span data-stu-id="adae0-115">**If you don't have a communications compliance policy that uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="adae0-116">À medida que você usa seus classificadores, talvez você queira aumentar a precisão das classificações que eles estão fazendo.</span><span class="sxs-lookup"><span data-stu-id="adae0-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="adae0-117">Você faz isso avaliando a qualidade das classificações feitas para itens identificados como sendo uma combinação ou não uma combinação.</span><span class="sxs-lookup"><span data-stu-id="adae0-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="adae0-118">Depois de fazer 30 avaliações para um classificador, ele recebe os comentários e se retreina automaticamente.</span><span class="sxs-lookup"><span data-stu-id="adae0-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="adae0-119">Para entender mais sobre o fluxo de trabalho geral de retreinamento de um classificador, consulte Fluxo de processos para [retreinar um classificador](classifier-learn-about.md#retraining-classifiers).</span><span class="sxs-lookup"><span data-stu-id="adae0-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="adae0-120">Um classificador já deve ser publicado e em uso antes de poder ser retreinado.</span><span class="sxs-lookup"><span data-stu-id="adae0-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies"></a><span data-ttu-id="adae0-121">Como retreinar um classificador em políticas de conformidade de comunicação</span><span class="sxs-lookup"><span data-stu-id="adae0-121">How to retrain a classifier in communication compliance policies</span></span>

1. <span data-ttu-id="adae0-122">Abra a política de conformidade de comunicação que usa um classificador como uma condição e escolha um dos itens identificados na lista **Pendente.**</span><span class="sxs-lookup"><span data-stu-id="adae0-122">Open the Communication compliance policy that uses a classifier as a condition and choose one of the identified items from the **Pending** list.</span></span>
2. <span data-ttu-id="adae0-123">Escolha as releições e **Melhorar a classificação.**</span><span class="sxs-lookup"><span data-stu-id="adae0-123">Choose the ellipsis and **Improve classification**.</span></span>
3. <span data-ttu-id="adae0-124">No painel **comentários detalhados,** se o item for um verdadeiro positivo, escolha, **Corresponder**.</span><span class="sxs-lookup"><span data-stu-id="adae0-124">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="adae0-125">Se o item for um falso positivo, ou seja, ele foi incluído incorretamente na categoria, escolha **Não uma combinação**.</span><span class="sxs-lookup"><span data-stu-id="adae0-125">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
4. <span data-ttu-id="adae0-126">Se houver outro classificador que seria mais apropriado para o item, você pode escolher-o na lista Sugerir outros classificadores **treináveis.**</span><span class="sxs-lookup"><span data-stu-id="adae0-126">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="adae0-127">Isso disparará o outro classificador para avaliar o item.</span><span class="sxs-lookup"><span data-stu-id="adae0-127">This will trigger the other classifier to evaluate the item.</span></span>

> [!TIP]
> <span data-ttu-id="adae0-128">Você pode fornecer comentários sobre vários itens simultaneamente escolhendo-os todos e escolhendo Fornecer **comentários** detalhados na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="adae0-128">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Provide detailed feedback** in the command bar.</span></span>

5. <span data-ttu-id="adae0-129">Escolha **Enviar comentários** para enviar sua avaliação das `match` classificações , e sugerir outros `not a match` classificadores com treinamento.</span><span class="sxs-lookup"><span data-stu-id="adae0-129">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="adae0-130">Quando você forneceu 30 instâncias de comentários para um classificador, ele será retreinado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="adae0-130">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="adae0-131">A retreinamento pode levar de 1 a 4 horas.</span><span class="sxs-lookup"><span data-stu-id="adae0-131">Retraining can take from 1-4 hours.</span></span> <span data-ttu-id="adae0-132">Os classificadores só podem ser retreinados duas vezes por dia.</span><span class="sxs-lookup"><span data-stu-id="adae0-132">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="adae0-133">Essas informações vão para o classificador em seu locatário, **ela não volta para a Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="adae0-133">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

6.  <span data-ttu-id="adae0-134">Abra a **página classificação de** dados no centro de conformidade do Microsoft **365.**</span><span class="sxs-lookup"><span data-stu-id="adae0-134">Open the **Data classification** page in the **Microsoft 365 compliance center**.</span></span>
7. <span data-ttu-id="adae0-135">Abra **classificadores com treinamento.**</span><span class="sxs-lookup"><span data-stu-id="adae0-135">Open **Trainable classifiers**.</span></span>
8. <span data-ttu-id="adae0-136">O classificador que foi usado em sua política de conformidade de Comunicações aparecerá sob o **título Re-training.**</span><span class="sxs-lookup"><span data-stu-id="adae0-136">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![classificador no status de retreinamento](../media/classifier-retraining.png)

9. <span data-ttu-id="adae0-138">Depois de concluir a retreinamento, escolha o classificador para abrir a visão geral de retreinamento.</span><span class="sxs-lookup"><span data-stu-id="adae0-138">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![visão geral dos resultados de retreinamento do classificador](../media/classifier-retraining-overview.png)

10. <span data-ttu-id="adae0-140">Revise a ação recomendada e as comparações de previsão das versões retreinadas e publicadas no momento do classificador.</span><span class="sxs-lookup"><span data-stu-id="adae0-140">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
11. <span data-ttu-id="adae0-141">Se você estiver satisfeito com os resultados da retreinamento, escolha **Publicar de novo.**</span><span class="sxs-lookup"><span data-stu-id="adae0-141">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
12. <span data-ttu-id="adae0-142">Se você não estiver satisfeito com os resultados do retreinamento, poderá optar por fornecer comentários adicionais ao classificador na interface de conformidade de comunicações e iniciar outro ciclo de retreinamento ou não fazer nada nesse caso, caso em que a versão publicada no momento do classificador continuará a ser usada.</span><span class="sxs-lookup"><span data-stu-id="adae0-142">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="adae0-143">Detalhes sobre recomendações de redação</span><span class="sxs-lookup"><span data-stu-id="adae0-143">Details on republishing recommendations</span></span>

<span data-ttu-id="adae0-144">Aqui estão algumas informações sobre como formulamos a recomendação para publicar um classificador retreinado ou sugerir um novo treinamento.</span><span class="sxs-lookup"><span data-stu-id="adae0-144">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="adae0-145">Isso requer uma compreensão um pouco mais profunda de como os classificadores treináveis funcionam.</span><span class="sxs-lookup"><span data-stu-id="adae0-145">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="adae0-146">Após um retreinamento, avaliamos o desempenho do classificador nos itens com comentários, bem como em todos os itens originalmente usados para treinar o classificador.</span><span class="sxs-lookup"><span data-stu-id="adae0-146">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="adae0-147">Para modelos integrados, os itens usados para treinar o classificador são os itens usados pela Microsoft para criar o modelo.</span><span class="sxs-lookup"><span data-stu-id="adae0-147">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="adae0-148">Para modelos personalizados, os itens usados no treinamento original do classificador são dos sites que você adicionou para teste e revisão.</span><span class="sxs-lookup"><span data-stu-id="adae0-148">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="adae0-149">Comparamos os números de desempenho em ambos os conjuntos de itens para o classificador retreinado e publicado para fornecer uma recomendação sobre se houve melhoria para republicar.</span><span class="sxs-lookup"><span data-stu-id="adae0-149">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="adae0-150">Confira também</span><span class="sxs-lookup"><span data-stu-id="adae0-150">See also</span></span>

- [<span data-ttu-id="adae0-151">Saiba mais sobre classificadores treináveis</span><span class="sxs-lookup"><span data-stu-id="adae0-151">Learn about trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="adae0-152">Extensões de nome de arquivo rastreado padrão e tipos de arquivos analisados no SharePoint Server Server</span><span class="sxs-lookup"><span data-stu-id="adae0-152">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)