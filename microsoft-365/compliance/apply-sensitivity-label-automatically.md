---
title: Aplicar um rótulo de confidencialidade automaticamente ao conteúdo
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
description: Quando você cria um rótulo de confidencialidade, pode atribuir automaticamente um rótulo ao documento ou email, ou solicitar que os usuários selecionem o rótulo recomendado.
ms.openlocfilehash: a1ea81bf8c65d3f54d26b19eae3b590f11283c30
ms.sourcegitcommit: 109b44aa71bb8453d0a602663df0fcf7ed7dfdbe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/25/2020
ms.locfileid: "42277208"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a><span data-ttu-id="b9917-103">Aplicar um rótulo de confidencialidade automaticamente ao conteúdo</span><span class="sxs-lookup"><span data-stu-id="b9917-103">Apply a sensitivity label to content automatically</span></span>

<span data-ttu-id="b9917-104">Quando você cria um rótulo de confidencialidade, pode atribuir automaticamente esse rótulo ao conteúdo, que inclui informações confidenciais, ou solicitar que os usuários apliquem o rótulo recomendado.</span><span class="sxs-lookup"><span data-stu-id="b9917-104">When you create a sensitivity label, you can automatically assign that label to content when it contains sensitive information, or you can prompt users to apply the label that you recommend.</span></span>

<span data-ttu-id="b9917-105">A capacidade de aplicar rótulos de confidencialidade automaticamente ao conteúdo é importante porque:</span><span class="sxs-lookup"><span data-stu-id="b9917-105">The ability to apply sensitivity labels to content automatically is important because:</span></span>

- <span data-ttu-id="b9917-106">Você não precisa treinar os usuários com relação a todas as classificações.</span><span class="sxs-lookup"><span data-stu-id="b9917-106">You don't need to train your users on all of your classifications.</span></span>

- <span data-ttu-id="b9917-107">Você não precisa depender dos usuários para classificar corretamente o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b9917-107">You don't need to rely on users to classify all content correctly.</span></span>

- <span data-ttu-id="b9917-108">Os usuários não precisam mais conhecer as políticas. Em vez disso, eles podem se concentrar no próprio trabalho.</span><span class="sxs-lookup"><span data-stu-id="b9917-108">Users no longer need to know about your policies — they can instead focus on their work.</span></span>

<span data-ttu-id="b9917-109">A rotulagem automática nos aplicativos Office para Windows têm suporte no cliente de rotulagem unificada da Proteção de Informações do Azure. </span><span class="sxs-lookup"><span data-stu-id="b9917-109">Automatic labeling in Office apps for Windows is supported by the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="b9917-110">Para rotulagem interna nos aplicativos do Office, esse recurso está [na visualização de alguns aplicativos](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span><span class="sxs-lookup"><span data-stu-id="b9917-110">For built-in labeling in Office apps, this capability is [in preview for some apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

<span data-ttu-id="b9917-111">As configurações de rotulagem automática para aplicativos do Office estão disponíveis quando você [cria ou edita um rótulo de confidencialidade](create-sensitivity-labels.md):</span><span class="sxs-lookup"><span data-stu-id="b9917-111">The auto-labeling settings for Office apps are available when you [create or edit a sensitivity label](create-sensitivity-labels.md):</span></span>

![Opções de rotulagem automática para rótulos de confidencialidade](../media/sensitivity-labels-auto-labeling-options.png)

## <a name="how-to-configure-auto-labeling-for-office-apps"></a><span data-ttu-id="b9917-113">Como configurar rotulamento automático para aplicativos do Office</span><span class="sxs-lookup"><span data-stu-id="b9917-113">How to configure auto-labeling for Office apps</span></span>

<span data-ttu-id="b9917-114">Um dos recursos mais poderosos dos rótulos de confidencialidade é a capacidade de aplicá-los automaticamente ao conteúdo que corresponde a determinadas condições.</span><span class="sxs-lookup"><span data-stu-id="b9917-114">One of the most powerful features of sensitivity labels is the ability to apply them automatically to content that matches certain conditions.</span></span> <span data-ttu-id="b9917-115">Nesse caso, as pessoas da sua organização não precisam aplicar os rótulos de confidencialidade. O Office 365 faz isso para elas.</span><span class="sxs-lookup"><span data-stu-id="b9917-115">In this case, people in your organization don't need to apply the sensitivity labels — Office 365 does the work for them.</span></span>

<span data-ttu-id="b9917-116">Você pode optar por aplicar rótulos de confidencialidade ao conteúdo automaticamente quando esse conteúdo contém tipos específicos de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="b9917-116">You can choose to apply sensitivity labels to content automatically when that content contains specific types of sensitive information.</span></span> <span data-ttu-id="b9917-117">Escolha em uma lista de tipos ou classificadores de informações confidenciais:</span><span class="sxs-lookup"><span data-stu-id="b9917-117">Choose from a list of sensitive info types or classifers:</span></span>

![Condições de rótulos para rotulagem automática em aplicativos do Office](../media/sensitivity-labels-conditions.png)

> [!NOTE]
> <span data-ttu-id="b9917-119">Atualmente, a opção para **Classificadores** está em visualização limitada e exige que você envie um formulário à Microsoft para habilitar esse recurso para seu locatário.</span><span class="sxs-lookup"><span data-stu-id="b9917-119">Currently, the option for **Classifers** is in limited preview and requires you to submit a form to Microsoft to enable this capability for your tenant.</span></span> <span data-ttu-id="b9917-120">Para obter mais informações, confira a postagem do blog [Anunciar a rotulagem automática no Office Apps usando classificadores internos - Visualização limitada](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889).</span><span class="sxs-lookup"><span data-stu-id="b9917-120">For more information, see the blog post [Announcing automatic labeling in Office Apps using built-in classifiers - Limited Preview](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889).</span></span>

<span data-ttu-id="b9917-121">Quando esse rótulo de confidencialidade é aplicado automaticamente, o usuário vê uma notificação no aplicativo do Office.</span><span class="sxs-lookup"><span data-stu-id="b9917-121">When this sensitivity label is automatically applied, the user sees a notification in their Office app.</span></span> <span data-ttu-id="b9917-122">Ele pode escolher **OK** ou ignorar a notificação.</span><span class="sxs-lookup"><span data-stu-id="b9917-122">They can choose **OK** to dismiss the notification.</span></span>

![Notificação informando que o documento tem um rótulo aplicado automaticamente](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a><span data-ttu-id="b9917-124">Configurar tipos de informações confidenciais para um rótulo</span><span class="sxs-lookup"><span data-stu-id="b9917-124">Configuring sensitive info types for a label</span></span>

<span data-ttu-id="b9917-125">Ao selecionar a opção **Tipos de informações confidenciais**, você vê a mesma lista de tipos de informações confidenciais que quando cria uma política de prevenção contra perda de dados (DLP).</span><span class="sxs-lookup"><span data-stu-id="b9917-125">When you select the **Sensitive info types** option, you see the same list of sensitive information types as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="b9917-126">Assim, você pode, por exemplo, aplicar automaticamente um rótulo Altamente Confidencial a qualquer conteúdo que contenha informações de identificação pessoal (PII) dos clientes, como números de cartão de crédito ou números de previdência social:</span><span class="sxs-lookup"><span data-stu-id="b9917-126">So you can, for example, automatically apply a Highly Confidential label to any content that contains customers' personally identifiable information (PII), such as credit card numbers or social security numbers:</span></span>

![Tipos de informações confidenciais para rotulagem automática em aplicativos do Office](../media/sensitivity-labels-sensitive-info-types.png)

<span data-ttu-id="b9917-128">Depois de selecionar os tipos de informações confidenciais, você pode refinar sua condição alterando a contagem de instâncias ou a precisão da correspondência.</span><span class="sxs-lookup"><span data-stu-id="b9917-128">After you select your sensitive information types, you can refine your condition by changing the instance count or match accuracy.</span></span> <span data-ttu-id="b9917-129">Para mais informações, confira [Ajustar as regras para torná-las mais fáceis ou mais difíceis de combinar](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span><span class="sxs-lookup"><span data-stu-id="b9917-129">For more information, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>

<span data-ttu-id="b9917-130">Além disso, você pode escolher se uma condição deve detectar todos os tipos de informações confidenciais ou apenas uma delas.</span><span class="sxs-lookup"><span data-stu-id="b9917-130">Further, you can choose whether a condition must detect all sensitive information types, or just one of them.</span></span> <span data-ttu-id="b9917-131">E para tornar suas condições mais flexíveis ou complexas, você pode adicionar grupos e usar operadores lógicos entre os grupos.</span><span class="sxs-lookup"><span data-stu-id="b9917-131">And to make your conditions more flexible or complex, you can add groups and use logical operators between the groups.</span></span> <span data-ttu-id="b9917-132">Para mais informações, confira [Agrupamento e operadores lógicos](data-loss-prevention-policies.md#grouping-and-logical-operators).</span><span class="sxs-lookup"><span data-stu-id="b9917-132">For more information, see [Grouping and logical operators](data-loss-prevention-policies.md#grouping-and-logical-operators).</span></span>

![Opções de contagem de instâncias e precisão de correspondência](../media/Sensitivity-labels-instance-count-match-accuracy.png)

### <a name="configuring-classifers-for-a-label"></a><span data-ttu-id="b9917-134">Configurar classificadores para um rótulo</span><span class="sxs-lookup"><span data-stu-id="b9917-134">Configuring classifers for a label</span></span>

<span data-ttu-id="b9917-135">Ao selecionar a opção **Classificadores**, selecione um ou mais dos classificadores internos:</span><span class="sxs-lookup"><span data-stu-id="b9917-135">When you select the **Classifers** option, select one or more of the built-in classifiers:</span></span>

![Opções para classificadores e rótulos de confidencialidade](../media/sensitivity-labels-classifers.png)

<span data-ttu-id="b9917-137">Para obter mais informações sobre os classificadores, confira [Introdução aos classificadores de treinamento (visualização)](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="b9917-137">For more information about these classifers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="b9917-138">Durante o período de visualização, os seguintes aplicativos oferecem suporte a classificadores de rótulos de confidencialidade:</span><span class="sxs-lookup"><span data-stu-id="b9917-138">During the preview period, the following apps support classifers for sensitivity labels:</span></span>

- <span data-ttu-id="b9917-139">Aplicativos da área de trabalho do Office 365 ProPlus para Windows, do [Office Insider](https://office.com/insider):</span><span class="sxs-lookup"><span data-stu-id="b9917-139">Office 365 ProPlus desktop apps for Windows, from [Office Insider](https://office.com/insider):</span></span>
    - <span data-ttu-id="b9917-140">Word</span><span class="sxs-lookup"><span data-stu-id="b9917-140">Word</span></span>
    - <span data-ttu-id="b9917-141">Excel</span><span class="sxs-lookup"><span data-stu-id="b9917-141">Excel</span></span>
    - <span data-ttu-id="b9917-142">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="b9917-142">PowerPoint</span></span>

- <span data-ttu-id="b9917-143">Office para aplicativos da Web, quando você [habilitou os rótulos de confidencialidade para arquivos do Office no SharePoint e no OneDrive (visualização pública)](sensitivity-labels-sharepoint-onedrive-files.md):</span><span class="sxs-lookup"><span data-stu-id="b9917-143">Office for the web apps, when you have [enabled sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md):</span></span>
    - <span data-ttu-id="b9917-144">Word</span><span class="sxs-lookup"><span data-stu-id="b9917-144">Word</span></span>
    - <span data-ttu-id="b9917-145">Excel</span><span class="sxs-lookup"><span data-stu-id="b9917-145">Excel</span></span>
    - <span data-ttu-id="b9917-146">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="b9917-146">PowerPoint</span></span>
    - <span data-ttu-id="b9917-147">Outlook</span><span class="sxs-lookup"><span data-stu-id="b9917-147">Outlook</span></span>

## <a name="recommend-that-the-user-apply-a-sensitivity-label"></a><span data-ttu-id="b9917-148">Recomendar ao usuário que ele aplique um rótulo de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="b9917-148">Recommend that the user apply a sensitivity label</span></span>

<span data-ttu-id="b9917-149">Se preferir, você pode recomendar aos usuários que apliquem o rótulo.</span><span class="sxs-lookup"><span data-stu-id="b9917-149">If you prefer, you can recommend to your users that they apply the label.</span></span> <span data-ttu-id="b9917-150">Com essa opção, seus usuários podem aceitar a classificação e qualquer proteção associada ou descartar a recomendação se o rótulo não for adequado para seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b9917-150">With this option, your users can accept the classification and any associated protection, or dismiss the recommendation if the label isn't suitable for their content.</span></span>

<span data-ttu-id="b9917-151">Os rótulos recomendados têm suporte para o Word, PowerPoint e Excel.</span><span class="sxs-lookup"><span data-stu-id="b9917-151">Recommended labels are supported for Word, PowerPoint, and Excel.</span></span>

![Opção para recomendar um rótulo de confidencialidade a usuários](../media/Sensitivity-labels-Recommended-label-option.png)

<span data-ttu-id="b9917-p110">Veja o exemplo de um aviso ao configurar uma condição para aplicar um rótulo como uma ação recomendada, com uma dica de política personalizada. Você poderá escolher o texto que será exibido na dica de política.</span><span class="sxs-lookup"><span data-stu-id="b9917-p110">Here's an example of a prompt when you configure a condition to apply a label as a recommended action, with a custom policy tip. You can choose what text is displayed in the policy tip.</span></span>

![Aviso para aplicar um rótulo recomendado](../media/Sensitivity-label-Prompt-for-required-label.png)

## <a name="how-automatic-or-recommended-labels-are-applied"></a><span data-ttu-id="b9917-156">Como aplicar rótulos automáticos ou recomendados</span><span class="sxs-lookup"><span data-stu-id="b9917-156">How automatic or recommended labels are applied</span></span>

- <span data-ttu-id="b9917-157">A etiquetagem automática se aplica ao Word, Excel e PowerPoint quando você salva um documento, e ao Outlook ao enviar um email.</span><span class="sxs-lookup"><span data-stu-id="b9917-157">Automatic labeling applies to Word, Excel, and PowerPoint when you save a document, and to Outlook when you send an email.</span></span> <span data-ttu-id="b9917-158">Essas condições detectam informações confidenciais no corpo de texto em documentos e emails, além de cabeçalhos e rodapés - mas não na linha de assunto ou nos anexos do email.</span><span class="sxs-lookup"><span data-stu-id="b9917-158">These conditions detect sensitive information in the body text in documents and emails, and to headers and footers — but not in the subject line or attachments of email.</span></span>

- <span data-ttu-id="b9917-159">Você não pode usar a rotulagem automática para documentos e e-mails rotulados anteriormente manualmente ou rotulados automaticamente com uma confidencialidade mais alta.</span><span class="sxs-lookup"><span data-stu-id="b9917-159">You can't use automatic labeling for documents and emails that were previously manually labeled, or previously automatically labeled with a higher sensitivity.</span></span> <span data-ttu-id="b9917-160">Lembre-se de que você só pode aplicar um único rótulo de confidencialidade a um documento ou e-mail (além de um único rótulo de retenção).</span><span class="sxs-lookup"><span data-stu-id="b9917-160">Remember, you can only apply a single sensitivity label to a document or email (in addition to a single retention label).</span></span>

- <span data-ttu-id="b9917-161">As rotulagens recomendadas se aplicam ao Word, Excel e PowerPoint quando você salva os documentos.</span><span class="sxs-lookup"><span data-stu-id="b9917-161">Recommended labeling applies to Word, Excel, and PowerPoint when you save documents.</span></span>

- <span data-ttu-id="b9917-162">Não é possível usar a rotulagem recomendada para os documentos que foram rotulados anteriormente com uma confidencialidade mais alta.</span><span class="sxs-lookup"><span data-stu-id="b9917-162">You can't use recommended labeling for documents that were previously labeled with a higher sensitivity.</span></span> <span data-ttu-id="b9917-163">Quando o conteúdo já estiver rotulado com uma confidencialidade mais alta, o usuário não verá o aviso com a recomendação e a dica de política.</span><span class="sxs-lookup"><span data-stu-id="b9917-163">When the content's already labeled with a higher sensitivity, the user won't see the prompt with the recommendation and policy tip.</span></span>

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a><span data-ttu-id="b9917-164">Como várias condições são avaliadas quando elas se aplicam a mais de um rótulo</span><span class="sxs-lookup"><span data-stu-id="b9917-164">How multiple conditions are evaluated when they apply to more than one label</span></span>

<span data-ttu-id="b9917-p114">Os rótulos são ordenados para avaliação de acordo com a posição especificada na política: o rótulo posicionado no início tem a posição mais baixa (menos confidencial) e o rótulo posicionado no final tem a posição mais alta (mais confidencial). Para saber mais sobre prioridade, confira [Prioridade de rótulos: a ordem é importante](sensitivity-labels.md#label-priority-order-matters)</span><span class="sxs-lookup"><span data-stu-id="b9917-p114">The labels are ordered for evaluation according to their position that you specify in the policy: The label positioned first has the lowest position (least sensitive) and the label positioned last has the highest position (most sensitive). For more information on priority, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters).</span></span>

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a><span data-ttu-id="b9917-167">Não configure uma etiqueta pai para ser aplicada automaticamente ou recomendada</span><span class="sxs-lookup"><span data-stu-id="b9917-167">Don't configure a parent label to be applied automatically or recommended</span></span>

<span data-ttu-id="b9917-168">Lembre-se de que você não pode aplicar um rótulo pai (um rótulo com sub-rótulos) ao conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b9917-168">Remember, you can't apply a parent label (a label with sublabels) to content.</span></span> <span data-ttu-id="b9917-169">Certifique-se de não configurar uma etiqueta pai para aplicação automática ou para a opção recomendada, pois a etiqueta pai não será aplicada ao conteúdo em aplicativos do Office que usam o cliente de rotulagem unificada da Proteção de Informações do Azure.</span><span class="sxs-lookup"><span data-stu-id="b9917-169">Make sure that you don't configure a parent label to be auto-applied or recommended, because the parent label won't be applied to content in Office apps that use the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="b9917-170">Confira mais informações em rótulos de pai e sub-rótulos[Sub-rótulos (agrupamento de rótulos)](sensitivity-labels.md#sublabels-grouping-labels).</span><span class="sxs-lookup"><span data-stu-id="b9917-170">For more information on parent labels and sublabels, see [Sublabels (grouping labels)](sensitivity-labels.md#sublabels-grouping-labels).</span></span>
