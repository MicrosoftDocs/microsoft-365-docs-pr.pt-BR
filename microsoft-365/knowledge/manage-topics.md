---
title: 'Gerenciar tópicos no Centro de Tópicos em Experiências de Tópico (Visualização) '
description: Como gerenciar tópicos na Central de Tópicos.
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 371ccc16e787b331f42026dec48e5e3113b2b172
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976186"
---
# <a name="manage-topics-in-the-topic-center-preview"></a><span data-ttu-id="5ebce-103">Gerenciar tópicos no Centro de Tópicos (Visualização)</span><span class="sxs-lookup"><span data-stu-id="5ebce-103">Manage topics in the Topic center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="5ebce-104">O conteúdo deste artigo é para o Project Cortex Private Preview.</span><span class="sxs-lookup"><span data-stu-id="5ebce-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="5ebce-105">[Mais informações sobre o Projeto Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="5ebce-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


<span data-ttu-id="5ebce-106">No Centro de tópicos, um gerente de conhecimento pode exibir a página Gerenciar tópicos para revisar **tópicos** que foram identificados nos locais de origem do SharePoint, conforme especificado pelo administrador de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="5ebce-106">In the Topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in SharePoint source locations as specified by your knowledge admin.</span></span>  

   ![Central de Tópicos](../media/knowledge-management/topic-center.png) </br> 



<span data-ttu-id="5ebce-108">Os gerentes de conhecimento ajudam a orientar tópicos descobertos pelo ciclo de vida do tópico no qual os tópicos são:</span><span class="sxs-lookup"><span data-stu-id="5ebce-108">Knowledge managers help to guide discovered topics through the topic lifecycle in which topics are:</span></span>

- <span data-ttu-id="5ebce-109">Sugerido: um tópico foi identificado pela IA e tem recursos, conexões e propriedades de suporte suficientes para atender ao limite do tópico.</span><span class="sxs-lookup"><span data-stu-id="5ebce-109">Suggested: A topic has been identified by AI and has enough supporting resources, connections, and properties to meet the topic threshold.</span></span>
- <span data-ttu-id="5ebce-110">Confirmado: Um tópico sugerido pela IA é validado.</span><span class="sxs-lookup"><span data-stu-id="5ebce-110">Confirmed: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="5ebce-111">A validação é feita por confirmação de um administrador de conhecimento. Além disso, um tópico pode ser confirmado se pelo menos dois usuários daem comentários positivos por meio de comentários de tópicos de que o tópico é válido.</span><span class="sxs-lookup"><span data-stu-id="5ebce-111">Validation is done by confirmation from a knowledge admin. Additionally, a topic can be confirmed if at least two users give positive feedback through topic feedback that the topic is valid.</span></span>
- <span data-ttu-id="5ebce-112">Removido: um tópico é rejeitado por um administrador de conhecimento e não estará mais visível para os visitantes.</span><span class="sxs-lookup"><span data-stu-id="5ebce-112">Removed: A topic is rejected by a knowledge admin and will no longer be visible to viewers.</span></span> <span data-ttu-id="5ebce-113">O tópico pode estar em qualquer estado quando é removido (sugerido ou confirmado).</span><span class="sxs-lookup"><span data-stu-id="5ebce-113">The topic can be in any state when it is removed (suggested or confirmed).</span></span> 
- <span data-ttu-id="5ebce-114">Publicado: um tópico confirmado que foi atualizado manualmente.</span><span class="sxs-lookup"><span data-stu-id="5ebce-114">Published: A confirmed topic that has been manually updated.</span></span>

   ![Gráfico do Ciclo de Vida do Tópico](../media/knowledge-management/topic-lifecycle.png) </br> 

## <a name="requirements"></a><span data-ttu-id="5ebce-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5ebce-116">Requirements</span></span>

<span data-ttu-id="5ebce-117">Para gerenciar tópicos na Central de Tópicos, você precisa:</span><span class="sxs-lookup"><span data-stu-id="5ebce-117">To manage topics in the Topic center, you need to:</span></span>
- <span data-ttu-id="5ebce-118">Ter uma licença de Experiências de Tópico.</span><span class="sxs-lookup"><span data-stu-id="5ebce-118">Have a Topic Experiences license.</span></span>
- <span data-ttu-id="5ebce-119">Ter permissões para [**Quem pode gerenciar tópicos.**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions)</span><span class="sxs-lookup"><span data-stu-id="5ebce-119">Have permissions to [**Who can manage topics**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions).</span></span> <span data-ttu-id="5ebce-120">Os administradores de conhecimento podem dar aos usuários essa permissão nas configurações de permissões do tópico Rede de Conhecimento.</span><span class="sxs-lookup"><span data-stu-id="5ebce-120">Knowledge admins can give users this permission in the Knowledge Network topic permissions settings.</span></span> 

<span data-ttu-id="5ebce-121">Você não poderá exibir a página Gerenciar Tópicos na Central de Tópicos, a menos que tenha a permissão Quem pode gerenciar **tópicos.**</span><span class="sxs-lookup"><span data-stu-id="5ebce-121">You will not be able to view the Manage Topics page in the Topic Center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="5ebce-122">No centro de tópicos, um gerente de conhecimento pode revisar tópicos que foram identificados nos locais de origem do SharePoint especificados e pode confirmá-los ou rejeitá-los.</span><span class="sxs-lookup"><span data-stu-id="5ebce-122">In the topic center, a knowledge manager can review topics that have been identified in the SharePoint source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="5ebce-123">Um gerente de conhecimento também pode criar e publicar novas páginas de tópico se uma não foi encontrada na descoberta de tópicos ou editar as existentes se elas precisam ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="5ebce-123">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="5ebce-124">Revisar tópicos sugeridos</span><span class="sxs-lookup"><span data-stu-id="5ebce-124">Review suggested topics</span></span>

<span data-ttu-id="5ebce-125">Na página Gerenciar Tópicos da Central de Tópicos, os tópicos descobertos nos locais de origem especificados do SharePoint serão listados na **guia Sugeridos.** Um gerente de conhecimento pode revisar tópicos não confirmados e optar por confirmá-los ou rejeitá-los.</span><span class="sxs-lookup"><span data-stu-id="5ebce-125">On the Topic center Manage Topics page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. A knowledge manager can review unconfirmed topics and choose to confirm or reject them.</span></span>

<span data-ttu-id="5ebce-126">Para revisar um tópico sugerido:</span><span class="sxs-lookup"><span data-stu-id="5ebce-126">To review a suggested topic:</span></span>

1. <span data-ttu-id="5ebce-127">Na página **Gerenciar tópicos,** selecione a **guia Sugerido,** selecione o tópico para abrir a página de tópicos.</span><span class="sxs-lookup"><span data-stu-id="5ebce-127">On the **Manage topics** page, select the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="5ebce-128">Na página de tópicos, revise a página de tópico e selecione **Editar** se precisar fazer alterações na página.</span><span class="sxs-lookup"><span data-stu-id="5ebce-128">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

3. <span data-ttu-id="5ebce-129">Depois de analisar o tópico, volte para a página Gerenciar tópicos.</span><span class="sxs-lookup"><span data-stu-id="5ebce-129">After reviewing the topic, go back to the Manage topics page.</span></span> <span data-ttu-id="5ebce-130">Para o tópico selecionado, você pode:</span><span class="sxs-lookup"><span data-stu-id="5ebce-130">For the selected topic, you can:</span></span>

   - <span data-ttu-id="5ebce-131">Selecione a marca de seleção para confirmar o tópico.</span><span class="sxs-lookup"><span data-stu-id="5ebce-131">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="5ebce-132">Selecione o **x** se quiser rejeitar o tópico.</span><span class="sxs-lookup"><span data-stu-id="5ebce-132">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="5ebce-133">Os tópicos confirmados serão removidos **da lista Sugeridos** e agora serão exibidos na **lista Confirmado.**</span><span class="sxs-lookup"><span data-stu-id="5ebce-133">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="5ebce-134">Os tópicos rejeitados serão removidos **da lista Sugeridos** e agora serão exibidos na **guia** Removido.</span><span class="sxs-lookup"><span data-stu-id="5ebce-134">Rejected topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

   </br> 

## <a name="confirmed-topics"></a><span data-ttu-id="5ebce-135">Tópicos confirmados</span><span class="sxs-lookup"><span data-stu-id="5ebce-135">Confirmed topics</span></span>

<span data-ttu-id="5ebce-136">Na página Gerenciar tópicos, os tópicos que foram descobertos em seus locais de origem especificados do SharePoint e que foram confirmados por  um gerente de conhecimento ou "de origem de lotes" confirmados por duas ou mais pessoas por meio do mecanismo de comentários do cartão serão listados na guia Confirmado. Se necessário, um usuário com permissões para gerenciar tópicos pode revisar tópicos confirmados e optar por rejeitá-los.</span><span class="sxs-lookup"><span data-stu-id="5ebce-136">On the Manage topics page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowd-sourced" confirmed by two or more people through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="5ebce-137">Para revisar um tópico confirmado:</span><span class="sxs-lookup"><span data-stu-id="5ebce-137">To review a confirmed topic:</span></span>

1. <span data-ttu-id="5ebce-138">Na guia **Confirmado,** selecione o tópico para abrir a página de tópico.</span><span class="sxs-lookup"><span data-stu-id="5ebce-138">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="5ebce-139">Na página de tópicos, revise a página de tópico e selecione **Editar** se precisar fazer alterações na página.</span><span class="sxs-lookup"><span data-stu-id="5ebce-139">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="5ebce-140">Observe que você ainda pode optar por rejeitar um tópico confirmado.</span><span class="sxs-lookup"><span data-stu-id="5ebce-140">Note that you can still chose to reject a confirmed topic.</span></span>  <span data-ttu-id="5ebce-141">Para fazer isso, vá para o tópico selecionado na lista Confirmado e selecione **o x** se quiser rejeitar o tópico.</span><span class="sxs-lookup"><span data-stu-id="5ebce-141">To do this, go to the selected topic in the Confirmed list, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="5ebce-142">Tópicos publicados</span><span class="sxs-lookup"><span data-stu-id="5ebce-142">Published topics</span></span>
<span data-ttu-id="5ebce-143">Tópicos publicados foram editados para que informações específicas sempre apareçam para quem encontrar a página.</span><span class="sxs-lookup"><span data-stu-id="5ebce-143">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="5ebce-144">Os tópicos criados manualmente estão listados aqui.</span><span class="sxs-lookup"><span data-stu-id="5ebce-144">Manually created topics are listed here.</span></span>




