---
title: Gerenciar tópicos no centro de tópicos no Microsoft Viva Topics
description: Como gerenciar tópicos no centro de tópicos.
author: chuckedmonson
ms.author: chucked
manager: pamgreen
ms.reviewer: ergradel
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: 2c29cdb6823e695cb9c96a4f51ef7b1c41642ac9
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333621"
---
# <a name="manage-topics-in-the-topic-center-in-microsoft-viva-topics"></a><span data-ttu-id="7af8b-103">Gerenciar tópicos no centro de tópicos no Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="7af8b-103">Manage topics in the topic center in Microsoft Viva Topics</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>

<span data-ttu-id="7af8b-104">No centro de tópicos Tópicos do Viva, um gerente de conhecimento pode exibir a página Gerenciar tópicos para revisar **tópicos** identificados nos locais de origem conforme especificado pelo administrador de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="7af8b-104">In the Viva Topics topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in the source locations as specified by your knowledge admin.</span></span>  

   ![Central de Tópicos](../media/knowledge-management/topic-center.png)  

## <a name="topic-stages"></a><span data-ttu-id="7af8b-106">Estágios do tópico</span><span class="sxs-lookup"><span data-stu-id="7af8b-106">Topic stages</span></span>

<span data-ttu-id="7af8b-107">Os gerentes de conhecimento ajudam a orientar tópicos descobertos por meio dos vários estágios de ciclo de vida de tópicos: **Sugerido** **,** Confirmado, **Publicado** e **Removido.**</span><span class="sxs-lookup"><span data-stu-id="7af8b-107">Knowledge managers help to guide discovered topics through the various topic lifecycle stages: **Suggested**, **Confirmed**, **Published**, and **Removed**.</span></span>

   ![Gráfico de ciclo de vida do tópico](../media/knowledge-management/topic-lifecycle.png) 

- <span data-ttu-id="7af8b-109">**Sugerido**: um tópico foi identificado pela IA e tem recursos, conexões e propriedades de suporte suficientes.</span><span class="sxs-lookup"><span data-stu-id="7af8b-109">**Suggested**: A topic has been identified by AI and has enough supporting resources, connections, and properties.</span></span> <span data-ttu-id="7af8b-110">(Eles são marcados como **um Tópico Sugerido** na interface do usuário.)</span><span class="sxs-lookup"><span data-stu-id="7af8b-110">(These are marked as a **Suggested Topic** in the UI.)</span></span>

- <span data-ttu-id="7af8b-111">**Confirmado**:um tópico sugerido pela IA é validado.</span><span class="sxs-lookup"><span data-stu-id="7af8b-111">**Confirmed**: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="7af8b-112">A validação do tópico deve ser confirmada por um gerente de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="7af8b-112">Topic validation must be confirmed by a knowledge manager.</span></span> <span data-ttu-id="7af8b-113">Para que um tópico seja confirmado, deve haver uma rede de dois votos positivos recebidos dos usuários que votaram usando o mecanismo de comentários no cartão de tópico.</span><span class="sxs-lookup"><span data-stu-id="7af8b-113">For a topic to be confirmed, there must be a net of two positive votes received from users who voted using the feedback mechanism on the topic card.</span></span> <span data-ttu-id="7af8b-114">Por exemplo, se um usuário votou positivo e um usuário votou negativo para um tópico específico, você ainda precisaria de mais dois votos positivos para que o tópico fosse confirmado.</span><span class="sxs-lookup"><span data-stu-id="7af8b-114">For example, if one user voted positive and one user voted negative for a particular topic, you would still need two more positive votes for the topic to be confirmed.</span></span>
 
- <span data-ttu-id="7af8b-115">**Publicado**: Um tópico confirmado que foi abordado: foram feitas edições manuais para melhorar sua qualidade.</span><span class="sxs-lookup"><span data-stu-id="7af8b-115">**Published**: A confirmed topic that has been curated: manual edits have been made to improve its quality.</span></span>

- <span data-ttu-id="7af8b-116">**Removido**: um tópico é rejeitado por um gerente de conhecimento e não será mais visível para os visualizadores.</span><span class="sxs-lookup"><span data-stu-id="7af8b-116">**Removed**: A topic is rejected by a knowledge manager and will no longer be visible to viewers.</span></span> <span data-ttu-id="7af8b-117">Um tópico pode ser removido em qualquer estado (sugerido, confirmado ou publicado).</span><span class="sxs-lookup"><span data-stu-id="7af8b-117">A topic can be removed in any state (suggested, confirmed, or published).</span></span> <span data-ttu-id="7af8b-118">Para que um tópico seja removido, deve haver uma rede de dois votos negativos recebidos dos usuários que votaram usando os mecanismos de feedback no cartão de tópico.</span><span class="sxs-lookup"><span data-stu-id="7af8b-118">For a topic to be removed, there must be a net of two negative votes received from users who voted using the feedback mechanisms on the topic card.</span></span> <span data-ttu-id="7af8b-119">Por exemplo, se um usuário votou negativo e um usuário votou positivo para um tópico específico, você ainda precisaria de mais dois votos negativos para que o tópico fosse removido.</span><span class="sxs-lookup"><span data-stu-id="7af8b-119">For example, if one user voted negative and one user voted positive for a particular topic, you would still need two more negative votes for the topic to be removed.</span></span> <span data-ttu-id="7af8b-120">Quando um tópico publicado é removido, a página com os detalhes de cura precisará ser excluída manualmente por meio da Biblioteca de Páginas do centro de tópicos.</span><span class="sxs-lookup"><span data-stu-id="7af8b-120">When a published topic is removed, the page with the curated details will need to be deleted manually through the Pages Library of the topic center.</span></span>

> [!Note] 
> <span data-ttu-id="7af8b-121">Na página **Gerenciar tópicos,** cada gerente de conhecimento só poderá ver tópicos em que eles tenham acesso aos arquivos e páginas subjacentes conectados ao tópico.</span><span class="sxs-lookup"><span data-stu-id="7af8b-121">On the **Manage topics** page, each knowledge manager will only be able to see topics where they have access to the underlying files and pages connected to the topic.</span></span> <span data-ttu-id="7af8b-122">Essa aparação de permissão será refletida na lista de tópicos que aparecem nas guias **Sugeridas** **,** **Confirmadas,** Publicadas e **Removidas.**</span><span class="sxs-lookup"><span data-stu-id="7af8b-122">This permission trimming will be reflected in the list of topics that appear in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs.</span></span> <span data-ttu-id="7af8b-123">O tópico conta, no entanto, mostrar o total de contagens na organização, independentemente das permissões.</span><span class="sxs-lookup"><span data-stu-id="7af8b-123">The topic counts, however, show the total counts in the organization regardless of permissions.</span></span>

## <a name="requirements"></a><span data-ttu-id="7af8b-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7af8b-124">Requirements</span></span>

<span data-ttu-id="7af8b-125">Para gerenciar tópicos no centro de tópicos, você precisa:</span><span class="sxs-lookup"><span data-stu-id="7af8b-125">To manage topics in the topic center, you need to:</span></span>
- <span data-ttu-id="7af8b-126">Ter uma licença do Viva Topics.</span><span class="sxs-lookup"><span data-stu-id="7af8b-126">Have a Viva Topics license.</span></span>

- <span data-ttu-id="7af8b-127">Ter a [**Who pode gerenciar a permissão de**](./topic-experiences-user-permissions.md) tópicos.</span><span class="sxs-lookup"><span data-stu-id="7af8b-127">Have the [**Who can manage topics**](./topic-experiences-user-permissions.md) permission.</span></span> <span data-ttu-id="7af8b-128">Os Administradores de conhecimento podem dar aos usuários essa permissão nas configurações de permissões do tópico do Viva Topics.</span><span class="sxs-lookup"><span data-stu-id="7af8b-128">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

<span data-ttu-id="7af8b-129">Você não poderá exibir a página Gerenciar tópicos no centro de **tópicos,** a menos que você tenha a permissão Who **possa gerenciar tópicos.**</span><span class="sxs-lookup"><span data-stu-id="7af8b-129">You will not be able to view the **Manage topics** page in the topic center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="7af8b-130">No centro de tópicos, um gerente de conhecimento pode revisar tópicos que foram identificados nos locais de origem especificados e podem confirmá-los ou removê-los.</span><span class="sxs-lookup"><span data-stu-id="7af8b-130">In the topic center, a knowledge manager can review topics that have been identified in the source locations you specified, and can either confirm or remove them.</span></span> <span data-ttu-id="7af8b-131">Um gerente de conhecimento também pode criar e publicar novas páginas de tópicos se uma não foi encontrada na descoberta de tópicos ou editar as existentes, caso precisem ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="7af8b-131">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>

## <a name="review-suggested-topics"></a><span data-ttu-id="7af8b-132">Revisar tópicos sugeridos</span><span class="sxs-lookup"><span data-stu-id="7af8b-132">Review suggested topics</span></span>

<span data-ttu-id="7af8b-133">Na página **Gerenciar tópicos,** os tópicos que foram descobertos em seus locais SharePoint de origem especificados serão listados na **guia Sugerido.** Se necessário, um gerente de conhecimento pode revisar tópicos não confirmados e optar por confirmá-los ou removê-los.</span><span class="sxs-lookup"><span data-stu-id="7af8b-133">On the **Manage topics** page, topics that were discovered in your specified SharePoint source locations will be listed on the **Suggested** tab. If needed, a knowledge manager can review unconfirmed topics and choose to confirm or remove them.</span></span>

   ![Tópicos sugeridos](../media/knowledge-management/quality-score.png) 

<span data-ttu-id="7af8b-135">Para revisar um tópico sugerido:</span><span class="sxs-lookup"><span data-stu-id="7af8b-135">To review a suggested topic:</span></span>

1. <span data-ttu-id="7af8b-136">Na página **Gerenciar tópicos,** selecione a guia **Sugerido** e selecione o tópico para abrir a página de tópicos.</span><span class="sxs-lookup"><span data-stu-id="7af8b-136">On the **Manage topics** page, select the **Suggested** tab, and then select the topic to open the topic page.</span></span>

2. <span data-ttu-id="7af8b-137">Na página de tópicos, revise a página de tópicos e selecione **Editar** se precisar fazer alterações na página.</span><span class="sxs-lookup"><span data-stu-id="7af8b-137">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span> <span data-ttu-id="7af8b-138">A publicação de todas as edições moverá este tópico para a **guia Publicado.**</span><span class="sxs-lookup"><span data-stu-id="7af8b-138">Publishing any edits will move this topic to the **Published** tab.</span></span>

3. <span data-ttu-id="7af8b-139">Depois de revisar o tópico, volte para a **página Gerenciar tópicos.**</span><span class="sxs-lookup"><span data-stu-id="7af8b-139">After reviewing the topic, go back to the **Manage topics** page.</span></span> <span data-ttu-id="7af8b-140">Para o tópico selecionado, você pode:</span><span class="sxs-lookup"><span data-stu-id="7af8b-140">For the selected topic, you can:</span></span>

   - <span data-ttu-id="7af8b-141">Selecione a marca de seleção para confirmar o tópico.</span><span class="sxs-lookup"><span data-stu-id="7af8b-141">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="7af8b-142">Selecione **o x** se quiser remover o tópico.</span><span class="sxs-lookup"><span data-stu-id="7af8b-142">Select the **x** if you want to remove the topic.</span></span>

    <span data-ttu-id="7af8b-143">Os tópicos confirmados serão removidos da **lista Sugerida** e agora serão exibidos na **lista Confirmado.**</span><span class="sxs-lookup"><span data-stu-id="7af8b-143">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="7af8b-144">Os tópicos removidos serão removidos da lista **Sugerida** e agora serão exibidos na **guia Removido.**</span><span class="sxs-lookup"><span data-stu-id="7af8b-144">Removed topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

### <a name="quality-score"></a><span data-ttu-id="7af8b-145">Pontuação de qualidade</span><span class="sxs-lookup"><span data-stu-id="7af8b-145">Quality score</span></span>

<span data-ttu-id="7af8b-146">Cada tópico que aparece na página **Tópicos** Sugeridos tem uma pontuação de qualidade atribuída a ele.</span><span class="sxs-lookup"><span data-stu-id="7af8b-146">Each topic that appears on the **Suggested** topics page has a quality score assigned to it.</span></span> <span data-ttu-id="7af8b-147">A pontuação de qualidade é um reflexo da quantidade de informações que o usuário médio verá para obter as informações sobre o tópico, tendo em mente que cada usuário pode ver mais ou menos informações devido às permissões que podem ou não ter sobre as informações em um tópico.</span><span class="sxs-lookup"><span data-stu-id="7af8b-147">The quality score is a reflection of the amount of information that the average user will see for the information on the topic, keeping in mind that each user might see more or less information because of the permissions they might or might not have on the information in a topic.</span></span> 

<span data-ttu-id="7af8b-148">A pontuação de qualidade pode ajudar a dar informações sobre os tópicos com mais informações e pode ser útil para encontrar tópicos que podem precisar ser editados manualmente.</span><span class="sxs-lookup"><span data-stu-id="7af8b-148">The quality score can help give insight to the topics with the most information and can be useful for finding topics that may need to be manually edited.</span></span> <span data-ttu-id="7af8b-149">Por exemplo, um tópico com uma pontuação de qualidade menor pode ser o resultado de alguns usuários não terem SharePoint permissões para arquivos ou sites pertinentes que a AI incluiu no tópico.</span><span class="sxs-lookup"><span data-stu-id="7af8b-149">For example, a topic with a lower quality score might be the result of some users not having SharePoint permissions to pertinent files or sites that AI has included in the topic.</span></span> <span data-ttu-id="7af8b-150">Um colaborador poderá, em seguida, editar o tópico para incluir as informações (quando apropriado), que poderão ser visualizadas para todos os usuários que podem exibir o tópico.</span><span class="sxs-lookup"><span data-stu-id="7af8b-150">A contributor could then edit the topic to include the information (when appropriate), which will then be viewable to all users who can view the topic.</span></span>

### <a name="impressions"></a><span data-ttu-id="7af8b-151">Impressões</span><span class="sxs-lookup"><span data-stu-id="7af8b-151">Impressions</span></span>

<span data-ttu-id="7af8b-152">A **coluna Impressões** exibe o número de vezes que um tópico foi mostrado aos usuários finais.</span><span class="sxs-lookup"><span data-stu-id="7af8b-152">The **Impressions** column displays the number of times a topic has been shown to end users.</span></span> <span data-ttu-id="7af8b-153">Isso inclui exibições por meio de cartões de resposta de tópicos na pesquisa e nos destaques do tópico.</span><span class="sxs-lookup"><span data-stu-id="7af8b-153">This includes views through topic answer cards in search and through topic highlights.</span></span> <span data-ttu-id="7af8b-154">Ele não reflete o clique sobre esses tópicos, mas que o tópico foi exibido.</span><span class="sxs-lookup"><span data-stu-id="7af8b-154">It does not reflect the click-through on these topics, but that the topic has been displayed.</span></span> <span data-ttu-id="7af8b-155">A **coluna Impressões** mostrará tópicos nas guias **Sugeridas** **,** Confirmadas, Publicadas e Removidas na página **Gerenciar** tópicos. </span><span class="sxs-lookup"><span data-stu-id="7af8b-155">The **Impressions** column will show for topics in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs on the **Manage topics** page.</span></span>

## <a name="confirmed-topics"></a><span data-ttu-id="7af8b-156">Tópicos confirmados</span><span class="sxs-lookup"><span data-stu-id="7af8b-156">Confirmed topics</span></span>

<span data-ttu-id="7af8b-157">Na página Gerenciar **tópicos,** os tópicos que foram descobertos em seus locais de origem do SharePoint especificados e foram confirmados por um gerente de conhecimento ou "crowdsourced"  confirmados por uma rede de duas ou mais pessoas (balanceando votos de usuários negativos contra votos positivos de usuários) por meio do mecanismo de feedback de cartão serão listados na guia Confirmado. Se necessário, um usuário com permissões para gerenciar tópicos pode revisar tópicos confirmados e optar por rejeitá-los.</span><span class="sxs-lookup"><span data-stu-id="7af8b-157">On the **Manage topics** page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowdsourced" confirmed by a net two or more people (balancing negative user votes against positive user votes) through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="7af8b-158">Para revisar um tópico confirmado:</span><span class="sxs-lookup"><span data-stu-id="7af8b-158">To review a confirmed topic:</span></span>

1. <span data-ttu-id="7af8b-159">Na guia **Confirmados**, selecione o tópico para abrir a página de tópicos.</span><span class="sxs-lookup"><span data-stu-id="7af8b-159">On the **Confirmed** tab, select the topic to open the topic page.</span></span>

2. <span data-ttu-id="7af8b-160">Na página de tópicos, revise a página de tópicos e selecione **Editar** se precisar fazer alterações na página.</span><span class="sxs-lookup"><span data-stu-id="7af8b-160">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="7af8b-161">Observe que você ainda pode optar por rejeitar um tópico confirmado.</span><span class="sxs-lookup"><span data-stu-id="7af8b-161">Note that you can still choose to reject a confirmed topic.</span></span> <span data-ttu-id="7af8b-162">Para fazer isso, vá para  o tópico selecionado na guia Confirmado e selecione **o x** se quiser rejeitar o tópico.</span><span class="sxs-lookup"><span data-stu-id="7af8b-162">To do this, go to the selected topic on the **Confirmed** tab, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="7af8b-163">Tópicos publicados</span><span class="sxs-lookup"><span data-stu-id="7af8b-163">Published topics</span></span>

<span data-ttu-id="7af8b-164">Os tópicos publicados foram editados para que informações específicas sempre apareçam para quem encontrar a página.</span><span class="sxs-lookup"><span data-stu-id="7af8b-164">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="7af8b-165">Os tópicos criados manualmente também são listados aqui.</span><span class="sxs-lookup"><span data-stu-id="7af8b-165">Manually created topics are listed here as well.</span></span>

   ![Gerenciar tópicos](../media/knowledge-management/manage-topics-new.png)
