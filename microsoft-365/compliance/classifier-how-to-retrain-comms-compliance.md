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
description: Saiba como fornecer comentários a um classificador de treinamento em conformidade com as comunicações.
ms.openlocfilehash: cdb8787715c3e022dfa0aa17cd83cc405aeef955
ms.sourcegitcommit: 54d1a2f363b2d5b63aae258c3cec0573a08f2866
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49752645"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance"></a><span data-ttu-id="8039e-103">Como treinar novamente um classificador em conformidade de comunicações</span><span class="sxs-lookup"><span data-stu-id="8039e-103">How to retrain a classifier in communications compliance</span></span>

<span data-ttu-id="8039e-104">Um classificador de treinamento do Microsoft 365 é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo, dando a ele exemplos para olhar.</span><span class="sxs-lookup"><span data-stu-id="8039e-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="8039e-105">Depois de treinado, você pode usá-lo para identificar o item para a aplicação de rótulos de sensibilidade do Office, políticas de conformidade de comunicações e políticas de rótulos de retenção.</span><span class="sxs-lookup"><span data-stu-id="8039e-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="8039e-106">Este artigo mostra como melhorar o desempenho de classificadores de treinamento personalizados e alguns classificadores pré-treinados fornecendo comentários adicionais.</span><span class="sxs-lookup"><span data-stu-id="8039e-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="8039e-107">Para saber mais sobre os diferentes tipos de classificadores, consulte Saiba mais [sobre classificadores de](classifier-learn-about.md)treinamento.</span><span class="sxs-lookup"><span data-stu-id="8039e-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="8039e-108">Permissions</span><span class="sxs-lookup"><span data-stu-id="8039e-108">Permissions</span></span>

<span data-ttu-id="8039e-109">Para acessar classificadores no Centro de Conformidade do Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="8039e-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="8039e-110">a função de administrador de Conformidade ou Administrador de Dados de Conformidade é necessária para treinar um classificador</span><span class="sxs-lookup"><span data-stu-id="8039e-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="8039e-111">Você precisará de contas com essas permissões para usar classificadores nestes cenários:</span><span class="sxs-lookup"><span data-stu-id="8039e-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="8039e-112">Cenário de política de conformidade de comunicação: Administrador de Gerenciamento de Riscos Insider, Administrador de Revisão de Supervisão</span><span class="sxs-lookup"><span data-stu-id="8039e-112">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="8039e-113">Fluxo de trabalho geral</span><span class="sxs-lookup"><span data-stu-id="8039e-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8039e-114">Você fornece comentários na solução de conformidade que está usando o classificador como uma condição.</span><span class="sxs-lookup"><span data-stu-id="8039e-114">You provide feedback in the compliance solution that is using the classifier as a condition.</span></span> <span data-ttu-id="8039e-115">**Se você não tiver uma política de conformidade de comunicações que use um classificador como uma condição, pare aqui.**</span><span class="sxs-lookup"><span data-stu-id="8039e-115">**If you don't have a communications compliance policy that uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="8039e-116">À medida que você usa seus classificadores, talvez você queira aumentar a precisão das classificações que eles estão fazendo.</span><span class="sxs-lookup"><span data-stu-id="8039e-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="8039e-117">Faça isso avaliando a qualidade das classificações feitas para itens que ele identificou como sendo uma combinação ou não.</span><span class="sxs-lookup"><span data-stu-id="8039e-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="8039e-118">Depois de fazer 30 avaliações para um classificador, ele recebe esse feedback e se restringe automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8039e-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="8039e-119">Para entender mais sobre o fluxo de trabalho geral de restrição de um classificador, consulte o fluxo de processo para [restringir um classificador.](classifier-learn-about.md#retraining-classifiers)</span><span class="sxs-lookup"><span data-stu-id="8039e-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="8039e-120">Um classificador já deve ser publicado e em uso antes de poder ser restringido.</span><span class="sxs-lookup"><span data-stu-id="8039e-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies"></a><span data-ttu-id="8039e-121">Como restringir um classificador em políticas de conformidade de comunicação</span><span class="sxs-lookup"><span data-stu-id="8039e-121">How to retrain a classifier in communication compliance policies</span></span>

1. <span data-ttu-id="8039e-122">Abra a política de conformidade de comunicação que usa um classificador como uma condição e escolha um dos itens identificados **na** lista Pendente.</span><span class="sxs-lookup"><span data-stu-id="8039e-122">Open the Communication compliance policy that uses a classifier as a condition and choose one of the identified items from the **Pending** list.</span></span>
2. <span data-ttu-id="8039e-123">Escolha as reellipses e **melhore a classificação.**</span><span class="sxs-lookup"><span data-stu-id="8039e-123">Choose the ellipsis and **Improve classification**.</span></span>
3. <span data-ttu-id="8039e-124">No painel **de comentários detalhado,** se o item for um verdadeiro positivo, escolha, **Corresponder.**</span><span class="sxs-lookup"><span data-stu-id="8039e-124">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="8039e-125">Se o item for um falso positivo, ou seja, foi incluído incorretamente na categoria, escolha **Não uma combinação.**</span><span class="sxs-lookup"><span data-stu-id="8039e-125">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
4. <span data-ttu-id="8039e-126">Se houver outro classificador que seria mais apropriado para o item, você pode escolher na lista Sugerir **outros classificadores** que possam ser treinar.</span><span class="sxs-lookup"><span data-stu-id="8039e-126">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="8039e-127">Isso disparará o outro classificador para avaliar o item.</span><span class="sxs-lookup"><span data-stu-id="8039e-127">This will trigger the other classifier to evaluate the item.</span></span>

> [!TIP]
> <span data-ttu-id="8039e-128">Você pode fornecer comentários sobre vários itens simultaneamente escolhendo todos eles e escolhendo Fornecer comentários detalhados **na** barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="8039e-128">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Provide detailed feedback** in the command bar.</span></span>

5. <span data-ttu-id="8039e-129">Escolha **Enviar comentários** para enviar sua avaliação das `match` classificações , e sugerir outros `not a match` classificadores de treinamento.</span><span class="sxs-lookup"><span data-stu-id="8039e-129">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="8039e-130">Quando você forneceu 30 instâncias de comentários para um classificador, ele será automaticamente restrito.</span><span class="sxs-lookup"><span data-stu-id="8039e-130">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="8039e-131">O retraining pode levar de 1 a 4 horas.</span><span class="sxs-lookup"><span data-stu-id="8039e-131">Retraining can take from 1-4 hours.</span></span> <span data-ttu-id="8039e-132">Os classificadores só podem ser restringidos duas vezes por dia.</span><span class="sxs-lookup"><span data-stu-id="8039e-132">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8039e-133">Essas informações vão para o classificador em seu locatário, **ela não volta para a Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="8039e-133">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

6.  <span data-ttu-id="8039e-134">Abra a **página Classificação de** dados no centro de conformidade do Microsoft **365.**</span><span class="sxs-lookup"><span data-stu-id="8039e-134">Open the **Data classification** page in the **Microsoft 365 compliance center**.</span></span>
7. <span data-ttu-id="8039e-135">Open **Trainable classifiers**.</span><span class="sxs-lookup"><span data-stu-id="8039e-135">Open **Trainable classifiers**.</span></span>
8. <span data-ttu-id="8039e-136">O classificador que foi usado em sua política de conformidade de comunicações será exibido sob o título **de Re-treinamento.**</span><span class="sxs-lookup"><span data-stu-id="8039e-136">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![classificador no status de restrição](../media/classifier-retraining.png)

9. <span data-ttu-id="8039e-138">Depois que o retraining for concluído, escolha o classificador para abrir a visão geral de restrição.</span><span class="sxs-lookup"><span data-stu-id="8039e-138">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![visão geral dos resultados de retraining do classificador](../media/classifier-retraining-overview.png)

10. <span data-ttu-id="8039e-140">Revise a ação recomendada e as comparações de previsão das versões restritas e publicadas no momento do classificador.</span><span class="sxs-lookup"><span data-stu-id="8039e-140">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
11. <span data-ttu-id="8039e-141">Se você estiver satisfeito com os resultados da restrição, escolha **Re-publicar.**</span><span class="sxs-lookup"><span data-stu-id="8039e-141">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
12. <span data-ttu-id="8039e-142">Se você não estiver satisfeito com os resultados da restrição, você pode optar por fornecer comentários adicionais ao classificador na interface de conformidade de comunicações e iniciar outro ciclo de restrição ou não fazer nada nesse caso, a versão publicada no momento do classificador continuará a ser usada.</span><span class="sxs-lookup"><span data-stu-id="8039e-142">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="8039e-143">Detalhes sobre recomendações de publicação</span><span class="sxs-lookup"><span data-stu-id="8039e-143">Details on republishing recommendations</span></span>

<span data-ttu-id="8039e-144">Aqui estão algumas informações sobre como formular a recomendação para publicar um classificador retrained ou sugerir mais restrições.</span><span class="sxs-lookup"><span data-stu-id="8039e-144">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="8039e-145">Isso requer uma compreensão um pouco mais profunda de como os classificadores de treinamento funcionam.</span><span class="sxs-lookup"><span data-stu-id="8039e-145">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="8039e-146">Após um novo treinamento, avaliamos o desempenho do classificador nos itens com comentários, bem como em todos os itens originalmente usados para treinar o classificador.</span><span class="sxs-lookup"><span data-stu-id="8039e-146">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="8039e-147">Para modelos integrados, os itens usados para treinar o classificador são os itens usados pela Microsoft para criar o modelo.</span><span class="sxs-lookup"><span data-stu-id="8039e-147">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="8039e-148">Para modelos personalizados, os itens usados no treinamento original são dos sites que você adicionou para teste e revisão.</span><span class="sxs-lookup"><span data-stu-id="8039e-148">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="8039e-149">Comparamos os números de desempenho em ambos os conjuntos de itens do classificador retrained e published para fornecer uma recomendação sobre se houve melhoria para republicar.</span><span class="sxs-lookup"><span data-stu-id="8039e-149">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="8039e-150">Confira também</span><span class="sxs-lookup"><span data-stu-id="8039e-150">See also</span></span>

- [<span data-ttu-id="8039e-151">Saiba mais sobre classificadores treináveis</span><span class="sxs-lookup"><span data-stu-id="8039e-151">Learn about trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="8039e-152">Extensões de nome de arquivo rastreado padrão e tipos de arquivos analisados no SharePoint Server Server</span><span class="sxs-lookup"><span data-stu-id="8039e-152">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
