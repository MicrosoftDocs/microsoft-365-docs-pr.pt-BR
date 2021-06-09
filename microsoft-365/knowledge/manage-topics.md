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
ms.openlocfilehash: f2429b0ffdd4a238bc9322ae9199eebbbfd407b5
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651147"
---
# <a name="manage-topics-in-the-topic-center-in-microsoft-viva-topics"></a><span data-ttu-id="c818b-103">Gerenciar tópicos no centro de tópicos no Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="c818b-103">Manage topics in the topic center in Microsoft Viva Topics</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>

<span data-ttu-id="c818b-104">No centro de tópicos Tópicos do Viva, um gerente de conhecimento pode exibir a página Gerenciar tópicos para revisar **tópicos** identificados nos locais de origem conforme especificado pelo administrador de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="c818b-104">In the Viva Topics topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in the source locations as specified by your knowledge admin.</span></span>  

   ![Central de Tópicos](../media/knowledge-management/topic-center.png)  

## <a name="topic-stages"></a><span data-ttu-id="c818b-106">Estágios do tópico</span><span class="sxs-lookup"><span data-stu-id="c818b-106">Topic stages</span></span>

<span data-ttu-id="c818b-107">Os gerentes de conhecimento ajudam a orientar tópicos descobertos por meio dos vários estágios de ciclo de vida de tópicos: **Sugerido** **,** Confirmado, **Publicado** e **Removido.**</span><span class="sxs-lookup"><span data-stu-id="c818b-107">Knowledge managers help to guide discovered topics through the various topic lifecycle stages: **Suggested**, **Confirmed**, **Published**, and **Removed**.</span></span>

   ![Gráfico de ciclo de vida do tópico](../media/knowledge-management/topic-lifecycle.png) 

- <span data-ttu-id="c818b-109">**Sugerido**: um tópico foi identificado pela IA e tem recursos, conexões e propriedades de suporte suficientes.</span><span class="sxs-lookup"><span data-stu-id="c818b-109">**Suggested**: A topic has been identified by AI and has enough supporting resources, connections, and properties.</span></span> <span data-ttu-id="c818b-110">(Eles são marcados como **um Tópico Sugerido** na interface do usuário.)</span><span class="sxs-lookup"><span data-stu-id="c818b-110">(These are marked as a **Suggested Topic** in the UI.)</span></span>

- <span data-ttu-id="c818b-111">**Confirmado**: um tópico que foi descoberto pela AI e foi validado.</span><span class="sxs-lookup"><span data-stu-id="c818b-111">**Confirmed**: A topic that has been discovered by AI and has been validated.</span></span> <span data-ttu-id="c818b-112">A validação de tópico ocorre quando:</span><span class="sxs-lookup"><span data-stu-id="c818b-112">Topic validation occurs when either:</span></span>

   - <span data-ttu-id="c818b-113">Um gerente de conhecimento confirma um tópico.</span><span class="sxs-lookup"><span data-stu-id="c818b-113">A knowledge manager confirms a topic.</span></span> <span data-ttu-id="c818b-114">Um gerente de [conhecimento confirma um tópico na](manage-topics.md#confirmed-topics) página Gerenciar **tópicos.**</span><span class="sxs-lookup"><span data-stu-id="c818b-114">A knowledge manager [confirms a topic](manage-topics.md#confirmed-topics) on the **Manage topics** page.</span></span>

   - <span data-ttu-id="c818b-115">Vários usuários confirmam um tópico.</span><span class="sxs-lookup"><span data-stu-id="c818b-115">Multiple users confirm a topic.</span></span> <span data-ttu-id="c818b-116">Deve haver uma rede de dois votos positivos recebidos dos usuários que votaram usando o mecanismo de comentários no cartão de tópico.</span><span class="sxs-lookup"><span data-stu-id="c818b-116">There must be a net of two positive votes received from users who voted using the feedback mechanism on the topic card.</span></span> <span data-ttu-id="c818b-117">Por exemplo, se um usuário votou positivo e um usuário votou negativo para um tópico específico, você ainda precisaria de mais dois votos positivos para que o tópico fosse confirmado.</span><span class="sxs-lookup"><span data-stu-id="c818b-117">For example, if one user voted positive and one user voted negative for a particular topic, you would still need two more positive votes for the topic to be confirmed.</span></span>
 
- <span data-ttu-id="c818b-118">**Publicado**: um tópico que foi abordado.</span><span class="sxs-lookup"><span data-stu-id="c818b-118">**Published**: A topic that has been curated.</span></span> <span data-ttu-id="c818b-119">As edições manuais foram feitas para melhorar sua qualidade ou foram criadas por um usuário.</span><span class="sxs-lookup"><span data-stu-id="c818b-119">Manual edits have been made to improve its quality, or it has been created by a user.</span></span>

- <span data-ttu-id="c818b-120">**Removido**: um tópico que foi rejeitado e não estará mais visível para os visualizadores.</span><span class="sxs-lookup"><span data-stu-id="c818b-120">**Removed**: A topic that has been rejected and will no longer be visible to viewers.</span></span> <span data-ttu-id="c818b-121">Um tópico pode ser removido em qualquer estado (sugerido, confirmado ou publicado).</span><span class="sxs-lookup"><span data-stu-id="c818b-121">A topic can be removed in any state (suggested, confirmed, or published).</span></span> <span data-ttu-id="c818b-122">A remoção de tópico ocorre quando:</span><span class="sxs-lookup"><span data-stu-id="c818b-122">Topic removal occurs when either:</span></span>

   - <span data-ttu-id="c818b-123">Um gerente de conhecimento remove um tópico.</span><span class="sxs-lookup"><span data-stu-id="c818b-123">A knowledge manager removes a topic.</span></span> <span data-ttu-id="c818b-124">Um gerente de conhecimento remove um tópico na página **Gerenciar** tópicos.</span><span class="sxs-lookup"><span data-stu-id="c818b-124">A knowledge manager removes a topic on the **Manage topics** page.</span></span>

   - <span data-ttu-id="c818b-125">Vários usuários lançam votos negativos usando o mecanismo de comentários no cartão de tópico.</span><span class="sxs-lookup"><span data-stu-id="c818b-125">Multiple users cast negative votes using the feedback mechanism on the topic card.</span></span> <span data-ttu-id="c818b-126">Para que um tópico seja removido, deve haver uma rede de dois votos negativos recebidos dos usuários.</span><span class="sxs-lookup"><span data-stu-id="c818b-126">For a topic to be removed, there must be a net of two negative votes received from users.</span></span> <span data-ttu-id="c818b-127">Por exemplo, se um usuário votou negativo e um usuário votou positivo para um tópico específico, você ainda precisaria de mais dois votos negativos para que o tópico fosse removido.</span><span class="sxs-lookup"><span data-stu-id="c818b-127">For example, if one user voted negative and one user voted positive for a particular topic, you would still need two more negative votes for the topic to be removed.</span></span>

  <span data-ttu-id="c818b-128">Quando um tópico publicado é removido, a página com os detalhes de cura precisará ser excluída manualmente por meio da Biblioteca de Páginas do centro de tópicos.</span><span class="sxs-lookup"><span data-stu-id="c818b-128">When a published topic is removed, the page with the curated details will need to be deleted manually through the Pages Library of the topic center.</span></span>

> [!Note] 
> <span data-ttu-id="c818b-129">Na página **Gerenciar tópicos,** cada gerente de conhecimento só poderá ver tópicos em que eles tenham acesso aos arquivos e páginas subjacentes conectados ao tópico.</span><span class="sxs-lookup"><span data-stu-id="c818b-129">On the **Manage topics** page, each knowledge manager will only be able to see topics where they have access to the underlying files and pages connected to the topic.</span></span> <span data-ttu-id="c818b-130">Essa aparação de permissão será refletida na lista de tópicos que aparecem nas guias **Sugeridas** **,** **Confirmadas,** Publicadas e **Removidas.**</span><span class="sxs-lookup"><span data-stu-id="c818b-130">This permission trimming will be reflected in the list of topics that appear in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs.</span></span> <span data-ttu-id="c818b-131">O tópico conta, no entanto, mostrar o total de contagens na organização, independentemente das permissões.</span><span class="sxs-lookup"><span data-stu-id="c818b-131">The topic counts, however, show the total counts in the organization regardless of permissions.</span></span>

## <a name="requirements"></a><span data-ttu-id="c818b-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c818b-132">Requirements</span></span>

<span data-ttu-id="c818b-133">Para gerenciar tópicos no centro de tópicos, você precisa:</span><span class="sxs-lookup"><span data-stu-id="c818b-133">To manage topics in the topic center, you need to:</span></span>
- <span data-ttu-id="c818b-134">Ter uma licença do Viva Topics.</span><span class="sxs-lookup"><span data-stu-id="c818b-134">Have a Viva Topics license.</span></span>

- <span data-ttu-id="c818b-135">Ter a [**Who pode gerenciar a permissão de**](./topic-experiences-user-permissions.md) tópicos.</span><span class="sxs-lookup"><span data-stu-id="c818b-135">Have the [**Who can manage topics**](./topic-experiences-user-permissions.md) permission.</span></span> <span data-ttu-id="c818b-136">Os Administradores de conhecimento podem dar aos usuários essa permissão nas configurações de permissões do tópico do Viva Topics.</span><span class="sxs-lookup"><span data-stu-id="c818b-136">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

<span data-ttu-id="c818b-137">Você não poderá exibir a página Gerenciar tópicos no centro de **tópicos,** a menos que você tenha a permissão Who **possa gerenciar tópicos.**</span><span class="sxs-lookup"><span data-stu-id="c818b-137">You will not be able to view the **Manage topics** page in the topic center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="c818b-138">No centro de tópicos, um gerente de conhecimento pode revisar tópicos que foram identificados nos locais de origem especificados e podem confirmá-los ou removê-los.</span><span class="sxs-lookup"><span data-stu-id="c818b-138">In the topic center, a knowledge manager can review topics that have been identified in the source locations you specified, and can either confirm or remove them.</span></span> <span data-ttu-id="c818b-139">Um gerente de conhecimento também pode criar e publicar novas páginas de tópicos se uma não foi encontrada na descoberta de tópicos ou editar as existentes, caso precisem ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="c818b-139">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>

## <a name="review-suggested-topics"></a><span data-ttu-id="c818b-140">Revisar tópicos sugeridos</span><span class="sxs-lookup"><span data-stu-id="c818b-140">Review suggested topics</span></span>

<span data-ttu-id="c818b-141">Na página **Gerenciar tópicos,** os tópicos que foram descobertos em seus locais SharePoint de origem especificados serão listados na **guia Sugerido.** Se necessário, um gerente de conhecimento pode revisar tópicos não confirmados e optar por confirmá-los ou removê-los.</span><span class="sxs-lookup"><span data-stu-id="c818b-141">On the **Manage topics** page, topics that were discovered in your specified SharePoint source locations will be listed on the **Suggested** tab. If needed, a knowledge manager can review unconfirmed topics and choose to confirm or remove them.</span></span>

   ![Tópicos sugeridos](../media/knowledge-management/quality-score.png) 

<span data-ttu-id="c818b-143">Para revisar um tópico sugerido:</span><span class="sxs-lookup"><span data-stu-id="c818b-143">To review a suggested topic:</span></span>

1. <span data-ttu-id="c818b-144">Na página **Gerenciar tópicos,** selecione a guia **Sugerido** e selecione o tópico para abrir a página de tópicos.</span><span class="sxs-lookup"><span data-stu-id="c818b-144">On the **Manage topics** page, select the **Suggested** tab, and then select the topic to open the topic page.</span></span>

2. <span data-ttu-id="c818b-145">Na página de tópicos, revise a página de tópicos e selecione **Editar** se precisar fazer alterações na página.</span><span class="sxs-lookup"><span data-stu-id="c818b-145">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span> <span data-ttu-id="c818b-146">A publicação de todas as edições moverá este tópico para a **guia Publicado.**</span><span class="sxs-lookup"><span data-stu-id="c818b-146">Publishing any edits will move this topic to the **Published** tab.</span></span>

3. <span data-ttu-id="c818b-147">Depois de revisar o tópico, volte para a **página Gerenciar tópicos.**</span><span class="sxs-lookup"><span data-stu-id="c818b-147">After reviewing the topic, go back to the **Manage topics** page.</span></span> <span data-ttu-id="c818b-148">Para o tópico selecionado, você pode:</span><span class="sxs-lookup"><span data-stu-id="c818b-148">For the selected topic, you can:</span></span>

   - <span data-ttu-id="c818b-149">Selecionar a marca de seleção para confirmar o tópico.</span><span class="sxs-lookup"><span data-stu-id="c818b-149">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="c818b-150">Selecione **o x** se quiser remover o tópico.</span><span class="sxs-lookup"><span data-stu-id="c818b-150">Select the **x** if you want to remove the topic.</span></span>

    <span data-ttu-id="c818b-151">Os tópicos confirmados serão removidos da **lista Sugerida** e agora serão exibidos na **lista Confirmado.**</span><span class="sxs-lookup"><span data-stu-id="c818b-151">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="c818b-152">Os tópicos removidos serão removidos da lista **Sugerida** e agora serão exibidos na **guia Removido.**</span><span class="sxs-lookup"><span data-stu-id="c818b-152">Removed topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

### <a name="quality-score"></a><span data-ttu-id="c818b-153">Pontuação de qualidade</span><span class="sxs-lookup"><span data-stu-id="c818b-153">Quality score</span></span>

<span data-ttu-id="c818b-154">Cada tópico que aparece na página **Tópicos** Sugeridos tem uma pontuação de qualidade atribuída a ele.</span><span class="sxs-lookup"><span data-stu-id="c818b-154">Each topic that appears on the **Suggested** topics page has a quality score assigned to it.</span></span> <span data-ttu-id="c818b-155">A pontuação de qualidade é um reflexo da quantidade de informações que o usuário médio verá para obter as informações sobre o tópico, tendo em mente que cada usuário pode ver mais ou menos informações devido às permissões que podem ou não ter sobre as informações em um tópico.</span><span class="sxs-lookup"><span data-stu-id="c818b-155">The quality score is a reflection of the amount of information that the average user will see for the information on the topic, keeping in mind that each user might see more or less information because of the permissions they might or might not have on the information in a topic.</span></span> 

<span data-ttu-id="c818b-156">A pontuação de qualidade pode ajudar a dar informações sobre os tópicos com mais informações e pode ser útil para encontrar tópicos que podem precisar ser editados manualmente.</span><span class="sxs-lookup"><span data-stu-id="c818b-156">The quality score can help give insight to the topics with the most information and can be useful for finding topics that may need to be manually edited.</span></span> <span data-ttu-id="c818b-157">Por exemplo, um tópico com uma pontuação de qualidade menor pode ser o resultado de alguns usuários não terem SharePoint permissões para arquivos ou sites pertinentes que a AI incluiu no tópico.</span><span class="sxs-lookup"><span data-stu-id="c818b-157">For example, a topic with a lower quality score might be the result of some users not having SharePoint permissions to pertinent files or sites that AI has included in the topic.</span></span> <span data-ttu-id="c818b-158">Um colaborador poderá, em seguida, editar o tópico para incluir as informações (quando apropriado), que poderão ser visualizadas para todos os usuários que podem exibir o tópico.</span><span class="sxs-lookup"><span data-stu-id="c818b-158">A contributor could then edit the topic to include the information (when appropriate), which will then be viewable to all users who can view the topic.</span></span>

### <a name="impressions"></a><span data-ttu-id="c818b-159">Impressões</span><span class="sxs-lookup"><span data-stu-id="c818b-159">Impressions</span></span>

<span data-ttu-id="c818b-160">A **coluna Impressões** exibe o número de vezes que um tópico foi mostrado aos usuários finais.</span><span class="sxs-lookup"><span data-stu-id="c818b-160">The **Impressions** column displays the number of times a topic has been shown to end users.</span></span> <span data-ttu-id="c818b-161">Isso inclui exibições por meio de cartões de resposta de tópicos na pesquisa e nos destaques do tópico.</span><span class="sxs-lookup"><span data-stu-id="c818b-161">This includes views through topic answer cards in search and through topic highlights.</span></span> <span data-ttu-id="c818b-162">Ele não reflete o clique sobre esses tópicos, mas que o tópico foi exibido.</span><span class="sxs-lookup"><span data-stu-id="c818b-162">It does not reflect the click-through on these topics, but that the topic has been displayed.</span></span> <span data-ttu-id="c818b-163">A **coluna Impressões** mostrará tópicos nas guias **Sugeridas** **,** Confirmadas, Publicadas e Removidas na página **Gerenciar** tópicos. </span><span class="sxs-lookup"><span data-stu-id="c818b-163">The **Impressions** column will show for topics in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs on the **Manage topics** page.</span></span>

## <a name="confirmed-topics"></a><span data-ttu-id="c818b-164">Tópicos confirmados</span><span class="sxs-lookup"><span data-stu-id="c818b-164">Confirmed topics</span></span>

<span data-ttu-id="c818b-165">Na página Gerenciar **tópicos,** os tópicos que foram descobertos em seus locais de origem do SharePoint especificados e foram confirmados por um gerente de conhecimento ou "crowdsourced"  confirmados por uma rede de duas ou mais pessoas (balanceando votos de usuários negativos contra votos positivos de usuários) por meio do mecanismo de feedback de cartão serão listados na guia Confirmado. Se necessário, um usuário com permissões para gerenciar tópicos pode revisar tópicos confirmados e optar por rejeitá-los.</span><span class="sxs-lookup"><span data-stu-id="c818b-165">On the **Manage topics** page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowdsourced" confirmed by a net two or more people (balancing negative user votes against positive user votes) through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="c818b-166">Para revisar um tópico confirmado:</span><span class="sxs-lookup"><span data-stu-id="c818b-166">To review a confirmed topic:</span></span>

1. <span data-ttu-id="c818b-167">Na guia **Confirmados**, selecione o tópico para abrir a página de tópicos.</span><span class="sxs-lookup"><span data-stu-id="c818b-167">On the **Confirmed** tab, select the topic to open the topic page.</span></span>

2. <span data-ttu-id="c818b-168">Na página de tópicos, revise a página de tópicos e selecione **Editar** se precisar fazer alterações na página.</span><span class="sxs-lookup"><span data-stu-id="c818b-168">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="c818b-169">Observe que você ainda pode optar por rejeitar um tópico confirmado.</span><span class="sxs-lookup"><span data-stu-id="c818b-169">Note that you can still choose to reject a confirmed topic.</span></span> <span data-ttu-id="c818b-170">Para fazer isso, vá para  o tópico selecionado na guia Confirmado e selecione **o x** se quiser rejeitar o tópico.</span><span class="sxs-lookup"><span data-stu-id="c818b-170">To do this, go to the selected topic on the **Confirmed** tab, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="c818b-171">Tópicos publicados</span><span class="sxs-lookup"><span data-stu-id="c818b-171">Published topics</span></span>

<span data-ttu-id="c818b-172">Os tópicos publicados foram editados para que informações específicas sempre apareçam para quem encontrar a página.</span><span class="sxs-lookup"><span data-stu-id="c818b-172">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="c818b-173">Os tópicos criados manualmente também são listados aqui.</span><span class="sxs-lookup"><span data-stu-id="c818b-173">Manually created topics are listed here as well.</span></span>

   ![Gerenciar tópicos](../media/knowledge-management/manage-topics-new.png)

## <a name="topic-count-dashboard"></a><span data-ttu-id="c818b-175">Painel de contagem de tópicos</span><span class="sxs-lookup"><span data-stu-id="c818b-175">Topic count dashboard</span></span>

<span data-ttu-id="c818b-176">Este gráfico no painel de exibição permite que você veja o número de tópicos no centro de tópicos do Viva Tópicos.</span><span class="sxs-lookup"><span data-stu-id="c818b-176">This chart in the dashboard view lets you see the number of topics in your Viva Topics topic center.</span></span> <span data-ttu-id="c818b-177">O gráfico mostra as contagens de tópicos por estágio de ciclo de vida de tópicos e também mostra como as contagens de tópicos têm tendência ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="c818b-177">The chart shows the topic counts per topic lifecycle stage and also shows how topic counts have trended over time.</span></span> <span data-ttu-id="c818b-178">Os gerentes de conhecimento podem monitorar visualmente a taxa na qual novos tópicos estão sendo descobertos pela AI e a taxa na qual os tópicos estão sendo confirmados ou publicados pelo gerente de conhecimento ou pelas ações do usuário.</span><span class="sxs-lookup"><span data-stu-id="c818b-178">Knowledge managers can visually monitor the rate at which new topics are being discovered by AI and the rate at which topics are getting confirmed or published by the knowledge manager or user actions.</span></span>

<span data-ttu-id="c818b-179">Os gerentes de conhecimento podem ver uma contagem diferente de tópicos representados na lista de tópicos na página Gerenciar **tópicos** do que eles veem no painel.</span><span class="sxs-lookup"><span data-stu-id="c818b-179">Knowledge managers might see a different count of topics represented in the list of topics on the **Manage topics** page than they see in the dashboard.</span></span> <span data-ttu-id="c818b-180">Isso porque um gerente de conhecimento pode não ter acesso a todos os tópicos.</span><span class="sxs-lookup"><span data-stu-id="c818b-180">This is because a knowledge manager might not have access to all topics.</span></span> <span data-ttu-id="c818b-181">A contagem apresentada no exibição do painel é feita antes da aplicação de corte de permissão.</span><span class="sxs-lookup"><span data-stu-id="c818b-181">The count presented in the dashboard view is taken before applying permission-trimming.</span></span> 

   ![Captura de tela do painel de contagem de tópicos](../media/knowledge-management/topic-count-dashboard.png)
