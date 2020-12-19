---
title: 'Gerenciar tópicos no centro de tópicos no tópico experiências (versão prévia) '
description: Como gerenciar tópicos no centro de tópicos.
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 832067d157ed9ffcba1ed9ad514c375cbbdd752b
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698770"
---
# <a name="manage-topics-in-the-topic-center-preview"></a><span data-ttu-id="f6474-103">Gerenciar tópicos no centro de tópicos (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="f6474-103">Manage topics in the Topic center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="f6474-104">O conteúdo deste artigo é para a visualização privada do Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="f6474-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="f6474-105">[Mais informações sobre o Projeto Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="f6474-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="f6474-106">No centro de tópicos, um gerente de conhecimento pode exibir a página **gerenciar tópicos** para examinar os tópicos que foram identificados nos locais de origem do SharePoint, conforme especificado por seu administrador de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="f6474-106">In the Topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in SharePoint source locations as specified by your knowledge admin.</span></span>  

   ![Centro de tópicos](../media/knowledge-management/topic-center.png) </br> 



<span data-ttu-id="f6474-108">Os gerentes de conhecimento ajudam a guiar tópicos descobertos por meio do ciclo de vida do tópico em que os tópicos são:</span><span class="sxs-lookup"><span data-stu-id="f6474-108">Knowledge managers help to guide discovered topics through the topic lifecycle in which topics are:</span></span>

- <span data-ttu-id="f6474-109">Sugerido: um tópico foi identificado pelo AI e tem recursos de suporte, conexões e propriedades suficientes para atender ao limite do tópico.</span><span class="sxs-lookup"><span data-stu-id="f6474-109">Suggested: A topic has been identified by AI and has enough supporting resources, connections, and properties to meet the topic threshold.</span></span>
- <span data-ttu-id="f6474-110">Confirmado: um tópico sugerido pelo AI foi validado.</span><span class="sxs-lookup"><span data-stu-id="f6474-110">Confirmed: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="f6474-111">A validação é feita por meio da confirmação de um administrador de conhecimento. Além disso, um tópico pode ser confirmado se pelo menos dois usuários fornecerem comentários positivos por meio dos comentários de tópico que o tópico é válido.</span><span class="sxs-lookup"><span data-stu-id="f6474-111">Validation is done by confirmation from a knowledge admin. Additionally, a topic can be confirmed if at least two users give positive feedback through topic feedback that the topic is valid.</span></span>
- <span data-ttu-id="f6474-112">Removido: um tópico é rejeitado por um administrador de conhecimento e não estará mais visível para os visualizadores.</span><span class="sxs-lookup"><span data-stu-id="f6474-112">Removed: A topic is rejected by a knowledge admin and will no longer be visible to viewers.</span></span> <span data-ttu-id="f6474-113">O tópico pode estar em qualquer estado quando for removido (sugerido ou confirmado).</span><span class="sxs-lookup"><span data-stu-id="f6474-113">The topic can be in any state when it is removed (suggested or confirmed).</span></span> 
- <span data-ttu-id="f6474-114">Publicado: um tópico confirmado que foi atualizado manualmente.</span><span class="sxs-lookup"><span data-stu-id="f6474-114">Published: A confirmed topic that has been manually updated.</span></span>

   ![Gráfico de ciclo de vida do tópico](../media/knowledge-management/topic-lifecycle.png) </br> 

## <a name="requirements"></a><span data-ttu-id="f6474-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f6474-116">Requirements</span></span>

<span data-ttu-id="f6474-117">Para gerenciar tópicos no centro de tópicos, você precisa:</span><span class="sxs-lookup"><span data-stu-id="f6474-117">To manage topics in the Topic center, you need to:</span></span>
- <span data-ttu-id="f6474-118">Ter um tópico enfrentando licença.</span><span class="sxs-lookup"><span data-stu-id="f6474-118">Have a Topic Experiences license.</span></span>
- <span data-ttu-id="f6474-119">Ter permissões para [**quem pode gerenciar tópicos**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions).</span><span class="sxs-lookup"><span data-stu-id="f6474-119">Have permissions to [**Who can manage topics**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions).</span></span> <span data-ttu-id="f6474-120">Os administradores de conhecimento podem conceder essa permissão aos usuários nas configurações de permissões de tópico da rede de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="f6474-120">Knowledge admins can give users this permission in the Knowledge Network topic permissions settings.</span></span> 

<span data-ttu-id="f6474-121">Você não poderá exibir a página Gerenciar tópicos no centro de tópicos, a menos que tenha a permissão **quem pode gerenciar tópicos** .</span><span class="sxs-lookup"><span data-stu-id="f6474-121">You will not be able to view the Manage Topics page in the Topic Center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="f6474-122">No centro de tópicos, um gerente de conhecimento pode examinar os tópicos que foram identificados nos locais de origem do SharePoint que você especificou e pode confirmá-los ou rejeitá-los.</span><span class="sxs-lookup"><span data-stu-id="f6474-122">In the topic center, a knowledge manager can review topics that have been identified in the SharePoint source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="f6474-123">Um gerente de conhecimento também pode criar e publicar novas páginas de tópico, se uma não foi encontrada no tópico Discovery, ou editar as existentes, caso precisem ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="f6474-123">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="f6474-124">Analisar tópicos sugeridos</span><span class="sxs-lookup"><span data-stu-id="f6474-124">Review suggested topics</span></span>

<span data-ttu-id="f6474-125">Na página centro de tópicos gerenciar tópicos, os tópicos que foram descobertos em seus locais de origem do SharePoint especificados serão listados na guia **sugerida** . Um gerente de conhecimento pode analisar os tópicos não confirmados e optar por confirmá-los ou rejeitá-los.</span><span class="sxs-lookup"><span data-stu-id="f6474-125">On the Topic center Manage Topics page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. A knowledge manager can review unconfirmed topics and choose to confirm or reject them.</span></span>

<span data-ttu-id="f6474-126">Para revisar um tópico sugerido:</span><span class="sxs-lookup"><span data-stu-id="f6474-126">To review a suggested topic:</span></span>

1. <span data-ttu-id="f6474-127">Na página **gerenciar tópicos** , selecione a guia **sugerida** e selecione o tópico para abrir a página de tópico.</span><span class="sxs-lookup"><span data-stu-id="f6474-127">On the **Manage topics** page, select the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="f6474-128">Na página tópico, revise a página de tópico e selecione **Editar** se precisar fazer qualquer alteração na página.</span><span class="sxs-lookup"><span data-stu-id="f6474-128">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

3. <span data-ttu-id="f6474-129">Após revisar o tópico, volte para a página Gerenciar tópicos.</span><span class="sxs-lookup"><span data-stu-id="f6474-129">After reviewing the topic, go back to the Manage topics page.</span></span> <span data-ttu-id="f6474-130">Para o tópico selecionado, você pode:</span><span class="sxs-lookup"><span data-stu-id="f6474-130">For the selected topic, you can:</span></span>

   - <span data-ttu-id="f6474-131">Selecione a marca de seleção para confirmar o tópico.</span><span class="sxs-lookup"><span data-stu-id="f6474-131">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="f6474-132">Selecione o **x** se você quiser rejeitar o tópico.</span><span class="sxs-lookup"><span data-stu-id="f6474-132">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="f6474-133">Os tópicos confirmados serão removidos da lista **sugerida** e agora serão exibidos na lista **confirmada** .</span><span class="sxs-lookup"><span data-stu-id="f6474-133">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="f6474-134">Os tópicos rejeitados serão removidos da lista **sugerida** e agora serão exibidos na guia **removido** .</span><span class="sxs-lookup"><span data-stu-id="f6474-134">Rejected topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

   </br> 

## <a name="confirmed-topics"></a><span data-ttu-id="f6474-135">Tópicos confirmados</span><span class="sxs-lookup"><span data-stu-id="f6474-135">Confirmed topics</span></span>

<span data-ttu-id="f6474-136">Na página Gerenciar tópicos, os tópicos que foram descobertos em seus locais de origem do SharePoint especificados e foram confirmados por um gerente de conhecimento ou "de alta origem" confirmado por duas ou mais pessoas pelo mecanismo de comentários do cartão serão listados na guia **confirmado** . Se necessário, um usuário com permissões para gerenciar tópicos pode examinar tópicos confirmados e optar por rejeitá-los.</span><span class="sxs-lookup"><span data-stu-id="f6474-136">On the Manage topics page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowd-sourced" confirmed by two or more people through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="f6474-137">Para revisar um tópico confirmado:</span><span class="sxs-lookup"><span data-stu-id="f6474-137">To review a confirmed topic:</span></span>

1. <span data-ttu-id="f6474-138">Na guia **confirmado** , selecione o tópico para abrir a página de tópico.</span><span class="sxs-lookup"><span data-stu-id="f6474-138">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="f6474-139">Na página tópico, revise a página de tópico e selecione **Editar** se precisar fazer qualquer alteração na página.</span><span class="sxs-lookup"><span data-stu-id="f6474-139">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="f6474-140">Observe que você ainda pode optar por rejeitar um tópico confirmado.</span><span class="sxs-lookup"><span data-stu-id="f6474-140">Note that you can still chose to reject a confirmed topic.</span></span>  <span data-ttu-id="f6474-141">Para fazer isso, vá para o tópico selecionado na lista confirmada e selecione **x** se quiser rejeitar o tópico.</span><span class="sxs-lookup"><span data-stu-id="f6474-141">To do this, go to the selected topic in the Confirmed list, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="f6474-142">Tópicos publicados</span><span class="sxs-lookup"><span data-stu-id="f6474-142">Published topics</span></span>
<span data-ttu-id="f6474-143">Tópicos publicados foram editados de modo que as informações específicas sempre apareçam para qualquer pessoa que encontre a página.</span><span class="sxs-lookup"><span data-stu-id="f6474-143">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="f6474-144">Os tópicos criados manualmente estão listados aqui.</span><span class="sxs-lookup"><span data-stu-id="f6474-144">Manually created topics are listed here.</span></span>




