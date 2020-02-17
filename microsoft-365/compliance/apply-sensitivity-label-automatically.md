---
title: Aplicar um rótulo de confidencialidade automaticamente ao conteúdo
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: 12/13/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
description: Quando você cria um rótulo de confidencialidade, pode atribuir automaticamente um rótulo ao documento ou email, ou solicitar que os usuários selecionem o rótulo recomendado.
ms.openlocfilehash: b2b78c6b028dc34040019f5087f1f8773eed768d
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42079668"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a><span data-ttu-id="40e30-103">Aplicar um rótulo de confidencialidade automaticamente ao conteúdo</span><span class="sxs-lookup"><span data-stu-id="40e30-103">Apply a sensitivity label to content automatically</span></span>

<span data-ttu-id="40e30-104">Quando você cria um rótulo de confidencialidade, pode atribuir automaticamente um rótulo ao conteúdo, que inclui informações confidenciais, ou solicitar que os usuários apliquem o rótulo recomendado.</span><span class="sxs-lookup"><span data-stu-id="40e30-104">When you create a sensitivity label, you can automatically assign that label to content containing sensitive information, or you can prompt users to apply the label that you recommend.</span></span>

<span data-ttu-id="40e30-105">A capacidade de aplicar rótulos de confidencialidade automaticamente ao conteúdo é importante porque:</span><span class="sxs-lookup"><span data-stu-id="40e30-105">The ability to apply sensitivity labels to content automatically is important because:</span></span>

- <span data-ttu-id="40e30-106">Você não precisa treinar os usuários com relação a todas as classificações.</span><span class="sxs-lookup"><span data-stu-id="40e30-106">You don't need to train your users on all of your classifications.</span></span>

- <span data-ttu-id="40e30-107">Você não precisa depender dos usuários para classificar corretamente o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="40e30-107">You don't need to rely on users to classify all content correctly.</span></span>

- <span data-ttu-id="40e30-108">Os usuários não precisam mais conhecer as políticas. Em vez disso, eles podem se concentrar no próprio trabalho.</span><span class="sxs-lookup"><span data-stu-id="40e30-108">Users no longer need to know about your policies — they can instead focus on their work.</span></span>

<span data-ttu-id="40e30-109">Para saber mais sobre os requisitos de licença, confira [Requisitos de assinatura e licenciamento de rótulos de confidencialidade](sensitivity-labels-office-apps.md#subscription-and-licensing-requirements-for-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="40e30-109">For information about license requirements, see [Subscription and licensing requirements for sensitivity labels](sensitivity-labels-office-apps.md#subscription-and-licensing-requirements-for-sensitivity-labels).</span></span>

<span data-ttu-id="40e30-110">As configurações de rotulagem automática estão disponíveis quando você cria um rótulo de confidencialidade no centro de conformidade do Microsoft 365, no centro de segurança do Microsoft 365 ou no Centro de Conformidade e Segurança do Office 365 em **Classificação** > **Rótulos de confidencialidade**.</span><span class="sxs-lookup"><span data-stu-id="40e30-110">The auto-labeling settings are available when you create a sensitivity label in the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security & Compliance Center under **Classification** > **Sensitivity labels**.</span></span>

![Opções de rotulagem automática para rótulos de confidencialidade](../media/Sensitivity-labels-Auto-labeling-options.png)

## <a name="apply-a-sensitivity-label-automatically-based-on-conditions"></a><span data-ttu-id="40e30-112">Aplicar um rótulo de confidencialidade automaticamente com base em condições</span><span class="sxs-lookup"><span data-stu-id="40e30-112">Apply a sensitivity label automatically based on conditions</span></span>

<span data-ttu-id="40e30-113">Um dos recursos mais poderosos dos rótulos de confidencialidade é a capacidade de aplicá-los automaticamente ao conteúdo que corresponde a determinadas condições.</span><span class="sxs-lookup"><span data-stu-id="40e30-113">One of the most powerful features of sensitivity labels is the ability to apply them automatically to content that matches certain conditions.</span></span> <span data-ttu-id="40e30-114">Nesse caso, as pessoas da sua organização não precisam aplicar os rótulos de confidencialidade. O Office 365 faz isso para elas.</span><span class="sxs-lookup"><span data-stu-id="40e30-114">In this case, people in your organization don't need to apply the sensitivity labels — Office 365 does the work for them.</span></span>

<span data-ttu-id="40e30-p102">Você pode optar por aplicar rótulos de confidencialidade automaticamente ao conteúdo sempre que ele inclui tipos específicos de informações confidenciais. Quando configura um rótulo de confidencialidade para ser aplicado automaticamente, você vê a mesma lista de tipos de informações confidenciais quando cria uma política de prevenção contra perda de dados (DLP). Assim, você pode, por exemplo, aplicar automaticamente um rótulo Altamente Confidencial a qualquer conteúdo que inclua PII (informações de identificação pessoal) dos clientes, como números de cartão de crédito ou de seguro social.</span><span class="sxs-lookup"><span data-stu-id="40e30-p102">You can choose to apply sensitivity labels to content automatically when that content contains specific types of sensitive information. When you configure a sensitivity label to be applied automatically, you see the same list of sensitive information types as when you create a data loss prevention (DLP) policy. So you can, for example, automatically apply a Highly Confidential label to any content that contains customers' personally identifiable information (PII), such as credit card numbers or social security numbers.</span></span>

![Opções de contagem de instâncias e precisão de correspondência](../media/Sensitivity-labels-instance-count-match-accuracy.png)

<span data-ttu-id="40e30-119">Depois de escolher os tipos de informações confidenciais, você pode refinar sua condição alterando a contagem de instâncias ou a precisão da correspondência.</span><span class="sxs-lookup"><span data-stu-id="40e30-119">After you choose your sensitive information types, you can refine your condition by changing the instance count or match accuracy.</span></span> <span data-ttu-id="40e30-120">Para mais informações, confira [Ajustar as regras para torná-las mais fáceis ou mais difíceis de combinar](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span><span class="sxs-lookup"><span data-stu-id="40e30-120">For more information, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>

<span data-ttu-id="40e30-121">Além disso, você pode escolher se uma condição deve detectar todos os tipos de informações confidenciais ou apenas uma delas.</span><span class="sxs-lookup"><span data-stu-id="40e30-121">Further, you can choose whether a condition must detect all sensitive information types, or just one of them.</span></span> <span data-ttu-id="40e30-122">E para tornar suas condições mais flexíveis ou complexas, você pode adicionar grupos e usar operadores lógicos entre os grupos.</span><span class="sxs-lookup"><span data-stu-id="40e30-122">And to make your conditions more flexible or complex, you can add groups and use logical operators between the groups.</span></span> <span data-ttu-id="40e30-123">Para mais informações, confira [Agrupamento e operadores lógicos](data-loss-prevention-policies.md#grouping-and-logical-operators).</span><span class="sxs-lookup"><span data-stu-id="40e30-123">For more information, see [Grouping and logical operators](data-loss-prevention-policies.md#grouping-and-logical-operators).</span></span>

<span data-ttu-id="40e30-p105">Quando um rótulo de confidencialidade é aplicado automaticamente, o usuário vê uma notificação no aplicativo do Office. Ele pode escolher **OK** ou ignorar a notificação.</span><span class="sxs-lookup"><span data-stu-id="40e30-p105">When a sensitivity label is automatically applied, the user sees a notification in their Office app. They can choose **OK** to dismiss the notification.</span></span>

![Notificação informando que o documento tem um rótulo aplicado automaticamente](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

## <a name="recommend-that-the-user-apply-a-sensitivity-label"></a><span data-ttu-id="40e30-127">Recomendar ao usuário que ele aplique um rótulo de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="40e30-127">Recommend that the user apply a sensitivity label</span></span>

<span data-ttu-id="40e30-128">Se preferir, você pode recomendar aos usuários que apliquem o rótulo.</span><span class="sxs-lookup"><span data-stu-id="40e30-128">If you prefer, you can recommend to your users that they apply the label.</span></span> <span data-ttu-id="40e30-129">Com essa opção, seus usuários podem aceitar a classificação e qualquer proteção associada ou descartar a recomendação se o rótulo não for adequado para seus documentos ou emails.</span><span class="sxs-lookup"><span data-stu-id="40e30-129">With this option, your users can accept the classification and any associated protection, or dismiss the recommendation if the label isn't suitable for their document or email.</span></span>

<span data-ttu-id="40e30-130">Os rótulos recomendados têm suporte no Word, PowerPoint e Excel (e exigem que o cliente de rotulagem unificado da Proteção de Informações do Azure esteja instalado).</span><span class="sxs-lookup"><span data-stu-id="40e30-130">Recommended labels are supported in Word, PowerPoint, and Excel (and require that the Azure Information Protection unified labeling client is installed).</span></span>

![Opção para recomendar um rótulo de confidencialidade a usuários](../media/Sensitivity-labels-Recommended-label-option.png)

<span data-ttu-id="40e30-p107">Veja o exemplo de um aviso ao configurar uma condição para aplicar um rótulo como uma ação recomendada, com uma dica de política personalizada. Você poderá escolher o texto que será exibido na dica de política.</span><span class="sxs-lookup"><span data-stu-id="40e30-p107">Here's an example of a prompt when you configure a condition to apply a label as a recommended action, with a custom policy tip. You can choose what text is displayed in the policy tip.</span></span>

![Aviso para aplicar um rótulo recomendado](../media/Sensitivity-label-Prompt-for-required-label.png)

## <a name="how-automatic-or-recommended-labels-are-applied"></a><span data-ttu-id="40e30-135">Como aplicar rótulos automáticos ou recomendados</span><span class="sxs-lookup"><span data-stu-id="40e30-135">How automatic or recommended labels are applied</span></span>

- <span data-ttu-id="40e30-136">A etiquetagem automática se aplica ao Word, Excel e PowerPoint quando você salva um documento, e ao Outlook ao enviar um email.</span><span class="sxs-lookup"><span data-stu-id="40e30-136">Automatic labeling applies to Word, Excel, and PowerPoint when you save a document, and to Outlook when you send an email.</span></span> <span data-ttu-id="40e30-137">Essas condições detectam informações confidenciais no corpo de texto em documentos e emails, além de cabeçalhos e rodapés - mas não na linha de assunto ou nos anexos do email.</span><span class="sxs-lookup"><span data-stu-id="40e30-137">These conditions detect sensitive information in the body text in documents and emails, and to headers and footers — but not in the subject line or attachments of email.</span></span>

- <span data-ttu-id="40e30-138">Você não pode usar a classificação automática para documentos e e-mails rotulados anteriormente manualmente ou rotulados automaticamente com uma classificação mais alta.</span><span class="sxs-lookup"><span data-stu-id="40e30-138">You can't use automatic classification for documents and emails that were previously manually labeled, or previously automatically labeled with a higher classification.</span></span> <span data-ttu-id="40e30-139">Lembre-se de que você só pode aplicar um único rótulo de confidencialidade a um documento ou e-mail (além de um único rótulo de retenção).</span><span class="sxs-lookup"><span data-stu-id="40e30-139">Remember, you can only apply a single sensitivity label to a document or email (in addition to a single retention label).</span></span>

- <span data-ttu-id="40e30-140">As classificações recomendadas se aplicam ao Word, Excel e PowerPoint quando você salva os documentos.</span><span class="sxs-lookup"><span data-stu-id="40e30-140">Recommended classification applies to Word, Excel, and PowerPoint when you save documents.</span></span>

- <span data-ttu-id="40e30-141">Não é possível usar a classificação recomendada para os documentos que foram rotulados anteriormente com uma classificação mais alta.</span><span class="sxs-lookup"><span data-stu-id="40e30-141">You can't use recommended classification for documents that were previously labeled with a higher classification.</span></span> <span data-ttu-id="40e30-142">Quando o conteúdo já estiver rotulado com uma classificação mais alta, o usuário não verá o aviso com a recomendação e a dica de política.</span><span class="sxs-lookup"><span data-stu-id="40e30-142">When the content's already labeled with a higher classification, the user won't see the prompt with the recommendation and policy tip.</span></span>

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a><span data-ttu-id="40e30-143">Como várias condições são avaliadas quando elas se aplicam a mais de um rótulo</span><span class="sxs-lookup"><span data-stu-id="40e30-143">How multiple conditions are evaluated when they apply to more than one label</span></span>

<span data-ttu-id="40e30-p111">Os rótulos são ordenados para avaliação de acordo com a posição especificada na política: o rótulo posicionado no início tem a posição mais baixa (menos confidencial) e o rótulo posicionado no final tem a posição mais alta (mais confidencial). Para saber mais sobre prioridade, confira [Prioridade de rótulos: a ordem é importante](sensitivity-labels.md#label-priority-order-matters)</span><span class="sxs-lookup"><span data-stu-id="40e30-p111">The labels are ordered for evaluation according to their position that you specify in the policy: The label positioned first has the lowest position (least sensitive) and the label positioned last has the highest position (most sensitive). For more information on priority, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters).</span></span>

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a><span data-ttu-id="40e30-146">Não configure uma etiqueta pai para ser aplicada automaticamente ou recomendada</span><span class="sxs-lookup"><span data-stu-id="40e30-146">Don't configure a parent label to be applied automatically or recommended</span></span>

<span data-ttu-id="40e30-147">Lembre-se de que você não pode aplicar um rótulo pai (um rótulo com sub-rótulos) ao conteúdo.</span><span class="sxs-lookup"><span data-stu-id="40e30-147">Remember, you can't apply a parent label (a label with sublabels) to content.</span></span> <span data-ttu-id="40e30-148">Certifique-se de não configurar uma etiqueta pai para aplicação automática ou para a opção recomendada, pois a etiqueta pai não será aplicada ao conteúdo em aplicativos do Office que usam o cliente de rotulagem unificada da Proteção de Informações do Azure.</span><span class="sxs-lookup"><span data-stu-id="40e30-148">Make sure that you don't configure a parent label to be auto-applied or recommended, because the parent label won't be applied to content in Office apps that use the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="40e30-149">Confira mais informações em rótulos de pai e sub-rótulos[Sub-rótulos (agrupamento de rótulos)](sensitivity-labels.md#sublabels-grouping-labels).</span><span class="sxs-lookup"><span data-stu-id="40e30-149">For more information on parent labels and sublabels, see [Sublabels (grouping labels)](sensitivity-labels.md#sublabels-grouping-labels).</span></span>
