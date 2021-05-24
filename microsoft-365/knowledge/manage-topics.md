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
ms.openlocfilehash: ba8f27c90f9c84729a10f461e85b2e1441b49549
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625396"
---
# <a name="manage-topics-in-the-topic-center-in-microsoft-viva-topics"></a><span data-ttu-id="a55cb-103">Gerenciar tópicos no centro de tópicos no Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="a55cb-103">Manage topics in the topic center in Microsoft Viva Topics</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>

<span data-ttu-id="a55cb-104">No centro de tópicos Tópicos do Viva, um gerente de conhecimento pode exibir a página Gerenciar tópicos para revisar **tópicos** identificados nos locais de origem conforme especificado pelo administrador de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="a55cb-104">In the Viva Topics topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in the source locations as specified by your knowledge admin.</span></span>  

   ![Central de Tópicos](../media/knowledge-management/topic-center.png)  

## <a name="topic-stages"></a><span data-ttu-id="a55cb-106">Estágios do tópico</span><span class="sxs-lookup"><span data-stu-id="a55cb-106">Topic stages</span></span>

<span data-ttu-id="a55cb-107">Os gerentes de conhecimento ajudam a orientar tópicos descobertos por meio dos vários estágios de ciclo de vida de tópicos: **Sugerido** **,** Confirmado, **Publicado** e **Removido.**</span><span class="sxs-lookup"><span data-stu-id="a55cb-107">Knowledge managers help to guide discovered topics through the various topic lifecycle stages: **Suggested**, **Confirmed**, **Published**, and **Removed**.</span></span>

   ![Gráfico de ciclo de vida do tópico](../media/knowledge-management/topic-lifecycle.png) 

- <span data-ttu-id="a55cb-109">**Sugerido**: um tópico foi identificado pela IA e tem recursos, conexões e propriedades de suporte suficientes.</span><span class="sxs-lookup"><span data-stu-id="a55cb-109">**Suggested**: A topic has been identified by AI and has enough supporting resources, connections, and properties.</span></span> <span data-ttu-id="a55cb-110">(Eles são marcados como **um Tópico Sugerido** na interface do usuário.)</span><span class="sxs-lookup"><span data-stu-id="a55cb-110">(These are marked as a **Suggested Topic** in the UI.)</span></span>

- <span data-ttu-id="a55cb-111">**Confirmado**: um tópico que foi descoberto pela AI e foi validado.</span><span class="sxs-lookup"><span data-stu-id="a55cb-111">**Confirmed**: A topic that has been discovered by AI and has been validated.</span></span> <span data-ttu-id="a55cb-112">A validação de tópico ocorre quando:</span><span class="sxs-lookup"><span data-stu-id="a55cb-112">Topic validation occurs when either:</span></span>

   - <span data-ttu-id="a55cb-113">Um gerente de conhecimento confirma um tópico.</span><span class="sxs-lookup"><span data-stu-id="a55cb-113">A knowledge manager confirms a topic.</span></span> <span data-ttu-id="a55cb-114">Um gerente de [conhecimento confirma um tópico na](manage-topics.md#confirmed-topics) página Gerenciar **tópicos.**</span><span class="sxs-lookup"><span data-stu-id="a55cb-114">A knowledge manager [confirms a topic](manage-topics.md#confirmed-topics) on the **Manage topics** page.</span></span>

   - <span data-ttu-id="a55cb-115">Vários usuários confirmam um tópico.</span><span class="sxs-lookup"><span data-stu-id="a55cb-115">Multiple users confirm a topic.</span></span> <span data-ttu-id="a55cb-116">Deve haver uma rede de dois votos positivos recebidos dos usuários que votaram usando o mecanismo de comentários no cartão de tópico.</span><span class="sxs-lookup"><span data-stu-id="a55cb-116">There must be a net of two positive votes received from users who voted using the feedback mechanism on the topic card.</span></span> <span data-ttu-id="a55cb-117">Por exemplo, se um usuário votou positivo e um usuário votou negativo para um tópico específico, você ainda precisaria de mais dois votos positivos para que o tópico fosse confirmado.</span><span class="sxs-lookup"><span data-stu-id="a55cb-117">For example, if one user voted positive and one user voted negative for a particular topic, you would still need two more positive votes for the topic to be confirmed.</span></span>
 
- <span data-ttu-id="a55cb-118">**Publicado**: um tópico que foi abordado.</span><span class="sxs-lookup"><span data-stu-id="a55cb-118">**Published**: A topic that has been curated.</span></span> <span data-ttu-id="a55cb-119">As edições manuais foram feitas para melhorar sua qualidade ou foram criadas por um usuário.</span><span class="sxs-lookup"><span data-stu-id="a55cb-119">Manual edits have been made to improve its quality, or it has been created by a user.</span></span>

- <span data-ttu-id="a55cb-120">**Removido**: um tópico que foi rejeitado e não estará mais visível para os visualizadores.</span><span class="sxs-lookup"><span data-stu-id="a55cb-120">**Removed**: A topic that has been rejected and will no longer be visible to viewers.</span></span> <span data-ttu-id="a55cb-121">Um tópico pode ser removido em qualquer estado (sugerido, confirmado ou publicado).</span><span class="sxs-lookup"><span data-stu-id="a55cb-121">A topic can be removed in any state (suggested, confirmed, or published).</span></span> <span data-ttu-id="a55cb-122">A remoção de tópico ocorre quando:</span><span class="sxs-lookup"><span data-stu-id="a55cb-122">Topic removal occurs when either:</span></span>

   - <span data-ttu-id="a55cb-123">Um gerente de conhecimento remove um tópico.</span><span class="sxs-lookup"><span data-stu-id="a55cb-123">A knowledge manager removes a topic.</span></span> <span data-ttu-id="a55cb-124">Um gerente de conhecimento remove um tópico na página **Gerenciar** tópicos.</span><span class="sxs-lookup"><span data-stu-id="a55cb-124">A knowledge manager removes a topic on the **Manage topics** page.</span></span>

   - <span data-ttu-id="a55cb-125">Vários usuários lançam votos negativos usando o mecanismo de comentários no cartão de tópico.</span><span class="sxs-lookup"><span data-stu-id="a55cb-125">Multiple users cast negative votes using the feedback mechanism on the topic card.</span></span> <span data-ttu-id="a55cb-126">Para que um tópico seja removido, deve haver uma rede de dois votos negativos recebidos dos usuários.</span><span class="sxs-lookup"><span data-stu-id="a55cb-126">For a topic to be removed, there must be a net of two negative votes received from users.</span></span> <span data-ttu-id="a55cb-127">Por exemplo, se um usuário votou negativo e um usuário votou positivo para um tópico específico, você ainda precisaria de mais dois votos negativos para que o tópico fosse removido.</span><span class="sxs-lookup"><span data-stu-id="a55cb-127">For example, if one user voted negative and one user voted positive for a particular topic, you would still need two more negative votes for the topic to be removed.</span></span>

  <span data-ttu-id="a55cb-128">Quando um tópico publicado é removido, a página com os detalhes de cura precisará ser excluída manualmente por meio da Biblioteca de Páginas do centro de tópicos.</span><span class="sxs-lookup"><span data-stu-id="a55cb-128">When a published topic is removed, the page with the curated details will need to be deleted manually through the Pages Library of the topic center.</span></span>

> [!Note] 
> <span data-ttu-id="a55cb-129">Na página **Gerenciar tópicos,** cada gerente de conhecimento só poderá ver tópicos em que eles tenham acesso aos arquivos e páginas subjacentes conectados ao tópico.</span><span class="sxs-lookup"><span data-stu-id="a55cb-129">On the **Manage topics** page, each knowledge manager will only be able to see topics where they have access to the underlying files and pages connected to the topic.</span></span> <span data-ttu-id="a55cb-130">Essa aparação de permissão será refletida na lista de tópicos que aparecem nas guias **Sugeridas** **,** **Confirmadas,** Publicadas e **Removidas.**</span><span class="sxs-lookup"><span data-stu-id="a55cb-130">This permission trimming will be reflected in the list of topics that appear in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs.</span></span> <span data-ttu-id="a55cb-131">O tópico conta, no entanto, mostrar o total de contagens na organização, independentemente das permissões.</span><span class="sxs-lookup"><span data-stu-id="a55cb-131">The topic counts, however, show the total counts in the organization regardless of permissions.</span></span>

## <a name="requirements"></a><span data-ttu-id="a55cb-132">Requirements</span><span class="sxs-lookup"><span data-stu-id="a55cb-132">Requirements</span></span>

<span data-ttu-id="a55cb-133">Para gerenciar tópicos no centro de tópicos, você precisa:</span><span class="sxs-lookup"><span data-stu-id="a55cb-133">To manage topics in the topic center, you need to:</span></span>
- <span data-ttu-id="a55cb-134">Ter uma licença do Viva Topics.</span><span class="sxs-lookup"><span data-stu-id="a55cb-134">Have a Viva Topics license.</span></span>

- <span data-ttu-id="a55cb-135">Ter a [**Who pode gerenciar a permissão de**](./topic-experiences-user-permissions.md) tópicos.</span><span class="sxs-lookup"><span data-stu-id="a55cb-135">Have the [**Who can manage topics**](./topic-experiences-user-permissions.md) permission.</span></span> <span data-ttu-id="a55cb-136">Os administradores de conhecimento podem dar aos usuários essa permissão nas configurações de permissões do tópico do Viva Topics.</span><span class="sxs-lookup"><span data-stu-id="a55cb-136">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

<span data-ttu-id="a55cb-137">Você não poderá exibir a página Gerenciar tópicos no centro de **tópicos,** a menos que você tenha a permissão Who **possa gerenciar tópicos.**</span><span class="sxs-lookup"><span data-stu-id="a55cb-137">You will not be able to view the **Manage topics** page in the topic center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="a55cb-138">No centro de tópicos, um gerente de conhecimento pode revisar tópicos que foram identificados nos locais de origem especificados e podem confirmá-los ou removê-los.</span><span class="sxs-lookup"><span data-stu-id="a55cb-138">In the topic center, a knowledge manager can review topics that have been identified in the source locations you specified, and can either confirm or remove them.</span></span> <span data-ttu-id="a55cb-139">Um gerente de conhecimento também pode criar e publicar novas páginas de tópicos se uma não foi encontrada na descoberta de tópicos ou editar as existentes, caso precisem ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="a55cb-139">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>

## <a name="review-suggested-topics"></a><span data-ttu-id="a55cb-140">Revisar tópicos sugeridos</span><span class="sxs-lookup"><span data-stu-id="a55cb-140">Review suggested topics</span></span>

<span data-ttu-id="a55cb-141">Na página **Gerenciar tópicos,** os tópicos que foram descobertos em seus locais SharePoint de origem especificados serão listados na **guia Sugerido.** Se necessário, um gerente de conhecimento pode revisar tópicos não confirmados e optar por confirmá-los ou removê-los.</span><span class="sxs-lookup"><span data-stu-id="a55cb-141">On the **Manage topics** page, topics that were discovered in your specified SharePoint source locations will be listed on the **Suggested** tab. If needed, a knowledge manager can review unconfirmed topics and choose to confirm or remove them.</span></span>

   ![Tópicos sugeridos](../media/knowledge-management/quality-score.png) 

<span data-ttu-id="a55cb-143">Para revisar um tópico sugerido:</span><span class="sxs-lookup"><span data-stu-id="a55cb-143">To review a suggested topic:</span></span>

1. <span data-ttu-id="a55cb-144">Na página **Gerenciar tópicos,** selecione a guia **Sugerido** e selecione o tópico para abrir a página de tópicos.</span><span class="sxs-lookup"><span data-stu-id="a55cb-144">On the **Manage topics** page, select the **Suggested** tab, and then select the topic to open the topic page.</span></span>

2. <span data-ttu-id="a55cb-145">Na página de tópicos, revise a página de tópicos e selecione **Editar** se precisar fazer alterações na página.</span><span class="sxs-lookup"><span data-stu-id="a55cb-145">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span> <span data-ttu-id="a55cb-146">A publicação de todas as edições moverá este tópico para a **guia Publicado.**</span><span class="sxs-lookup"><span data-stu-id="a55cb-146">Publishing any edits will move this topic to the **Published** tab.</span></span>

3. <span data-ttu-id="a55cb-147">Depois de revisar o tópico, volte para a **página Gerenciar tópicos.**</span><span class="sxs-lookup"><span data-stu-id="a55cb-147">After reviewing the topic, go back to the **Manage topics** page.</span></span> <span data-ttu-id="a55cb-148">Para o tópico selecionado, você pode:</span><span class="sxs-lookup"><span data-stu-id="a55cb-148">For the selected topic, you can:</span></span>

   - <span data-ttu-id="a55cb-149">Selecionar a marca de seleção para confirmar o tópico.</span><span class="sxs-lookup"><span data-stu-id="a55cb-149">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="a55cb-150">Selecione **o x** se quiser remover o tópico.</span><span class="sxs-lookup"><span data-stu-id="a55cb-150">Select the **x** if you want to remove the topic.</span></span>

    <span data-ttu-id="a55cb-151">Os tópicos confirmados serão removidos da **lista Sugerida** e agora serão exibidos na **lista Confirmado.**</span><span class="sxs-lookup"><span data-stu-id="a55cb-151">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="a55cb-152">Os tópicos removidos serão removidos da lista **Sugerida** e agora serão exibidos na **guia Removido.**</span><span class="sxs-lookup"><span data-stu-id="a55cb-152">Removed topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

### <a name="quality-score"></a><span data-ttu-id="a55cb-153">Pontuação de qualidade</span><span class="sxs-lookup"><span data-stu-id="a55cb-153">Quality score</span></span>

<span data-ttu-id="a55cb-154">Cada tópico que aparece na página **Tópicos** Sugeridos tem uma pontuação de qualidade atribuída a ele.</span><span class="sxs-lookup"><span data-stu-id="a55cb-154">Each topic that appears on the **Suggested** topics page has a quality score assigned to it.</span></span> <span data-ttu-id="a55cb-155">A pontuação de qualidade é um reflexo da quantidade de informações que o usuário médio verá para obter as informações sobre o tópico, tendo em mente que cada usuário pode ver mais ou menos informações devido às permissões que podem ou não ter sobre as informações em um tópico.</span><span class="sxs-lookup"><span data-stu-id="a55cb-155">The quality score is a reflection of the amount of information that the average user will see for the information on the topic, keeping in mind that each user might see more or less information because of the permissions they might or might not have on the information in a topic.</span></span> 

<span data-ttu-id="a55cb-156">A pontuação de qualidade pode ajudar a dar informações sobre os tópicos com mais informações e pode ser útil para encontrar tópicos que podem precisar ser editados manualmente.</span><span class="sxs-lookup"><span data-stu-id="a55cb-156">The quality score can help give insight to the topics with the most information and can be useful for finding topics that may need to be manually edited.</span></span> <span data-ttu-id="a55cb-157">Por exemplo, um tópico com uma pontuação de qualidade menor pode ser o resultado de alguns usuários não terem SharePoint permissões para arquivos ou sites pertinentes que a AI incluiu no tópico.</span><span class="sxs-lookup"><span data-stu-id="a55cb-157">For example, a topic with a lower quality score might be the result of some users not having SharePoint permissions to pertinent files or sites that AI has included in the topic.</span></span> <span data-ttu-id="a55cb-158">Um colaborador poderá, em seguida, editar o tópico para incluir as informações (quando apropriado), que poderão ser visualizadas para todos os usuários que podem exibir o tópico.</span><span class="sxs-lookup"><span data-stu-id="a55cb-158">A contributor could then edit the topic to include the information (when appropriate), which will then be viewable to all users who can view the topic.</span></span>

### <a name="impressions"></a><span data-ttu-id="a55cb-159">Impressões</span><span class="sxs-lookup"><span data-stu-id="a55cb-159">Impressions</span></span>

<span data-ttu-id="a55cb-160">A **coluna Impressões** exibe o número de vezes que um tópico foi mostrado aos usuários finais.</span><span class="sxs-lookup"><span data-stu-id="a55cb-160">The **Impressions** column displays the number of times a topic has been shown to end users.</span></span> <span data-ttu-id="a55cb-161">Isso inclui exibições por meio de cartões de resposta de tópicos na pesquisa e nos destaques do tópico.</span><span class="sxs-lookup"><span data-stu-id="a55cb-161">This includes views through topic answer cards in search and through topic highlights.</span></span> <span data-ttu-id="a55cb-162">Ele não reflete o clique sobre esses tópicos, mas que o tópico foi exibido.</span><span class="sxs-lookup"><span data-stu-id="a55cb-162">It does not reflect the click-through on these topics, but that the topic has been displayed.</span></span> <span data-ttu-id="a55cb-163">A **coluna Impressões** mostrará tópicos nas guias **Sugeridas** **,** Confirmadas, Publicadas e Removidas na página **Gerenciar** tópicos. </span><span class="sxs-lookup"><span data-stu-id="a55cb-163">The **Impressions** column will show for topics in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs on the **Manage topics** page.</span></span>

## <a name="confirmed-topics"></a><span data-ttu-id="a55cb-164">Tópicos confirmados</span><span class="sxs-lookup"><span data-stu-id="a55cb-164">Confirmed topics</span></span>

<span data-ttu-id="a55cb-165">Na página Gerenciar **tópicos,** os tópicos que foram descobertos em seus locais de origem do SharePoint especificados e foram confirmados por um gerente de conhecimento ou "crowdsourced"  confirmados por uma rede de duas ou mais pessoas (balanceando votos de usuários negativos contra votos positivos de usuários) por meio do mecanismo de feedback de cartão serão listados na guia Confirmado. Se necessário, um usuário com permissões para gerenciar tópicos pode revisar tópicos confirmados e optar por rejeitá-los.</span><span class="sxs-lookup"><span data-stu-id="a55cb-165">On the **Manage topics** page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowdsourced" confirmed by a net two or more people (balancing negative user votes against positive user votes) through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="a55cb-166">Para revisar um tópico confirmado:</span><span class="sxs-lookup"><span data-stu-id="a55cb-166">To review a confirmed topic:</span></span>

1. <span data-ttu-id="a55cb-167">Na guia **Confirmados**, selecione o tópico para abrir a página de tópicos.</span><span class="sxs-lookup"><span data-stu-id="a55cb-167">On the **Confirmed** tab, select the topic to open the topic page.</span></span>

2. <span data-ttu-id="a55cb-168">Na página de tópicos, revise a página de tópicos e selecione **Editar** se precisar fazer alterações na página.</span><span class="sxs-lookup"><span data-stu-id="a55cb-168">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="a55cb-169">Observe que você ainda pode optar por rejeitar um tópico confirmado.</span><span class="sxs-lookup"><span data-stu-id="a55cb-169">Note that you can still choose to reject a confirmed topic.</span></span> <span data-ttu-id="a55cb-170">Para fazer isso, vá para  o tópico selecionado na guia Confirmado e selecione **o x** se quiser rejeitar o tópico.</span><span class="sxs-lookup"><span data-stu-id="a55cb-170">To do this, go to the selected topic on the **Confirmed** tab, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="a55cb-171">Tópicos publicados</span><span class="sxs-lookup"><span data-stu-id="a55cb-171">Published topics</span></span>

<span data-ttu-id="a55cb-172">Os tópicos publicados foram editados para que informações específicas sempre apareçam para quem encontrar a página.</span><span class="sxs-lookup"><span data-stu-id="a55cb-172">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="a55cb-173">Os tópicos criados manualmente também são listados aqui.</span><span class="sxs-lookup"><span data-stu-id="a55cb-173">Manually created topics are listed here as well.</span></span>

   ![Gerenciar tópicos](../media/knowledge-management/manage-topics-new.png)
