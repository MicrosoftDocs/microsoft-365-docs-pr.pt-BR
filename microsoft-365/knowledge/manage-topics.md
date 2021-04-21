---
title: Gerenciar tópicos no centro de tópicos no Microsoft Viva Topics
description: Como gerenciar tópicos na Central de Tópicos.
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
ms.openlocfilehash: 4532f5685fdde7c89ca59e5c22e1ad8afdf2b112
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904029"
---
# <a name="manage-topics-in-the-topic-center-in-microsoft-viva-topics"></a><span data-ttu-id="5e250-103">Gerenciar tópicos no centro de tópicos no Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="5e250-103">Manage topics in the topic center in Microsoft Viva Topics</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


<span data-ttu-id="5e250-104">No centro de tópicos Tópicos do Viva, um gerente de conhecimento pode exibir a página Gerenciar tópicos para revisar **tópicos** identificados nos locais de origem conforme especificado pelo administrador de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="5e250-104">In the Viva Topics topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in the source locations as specified by your knowledge admin.</span></span>  

   ![Central de Tópicos](../media/knowledge-management/topic-center.png) </br> 



<span data-ttu-id="5e250-106">Os gerentes de conhecimento ajudam a orientar tópicos descobertos por meio dos vários estágios de ciclo de vida de tópicos:</span><span class="sxs-lookup"><span data-stu-id="5e250-106">Knowledge managers help to guide discovered topics through the various topic lifecycle stages:</span></span>

- <span data-ttu-id="5e250-107">**Sugerido**: um tópico foi identificado pela AI e tem recursos de suporte suficientes, conexões e propriedades.</span><span class="sxs-lookup"><span data-stu-id="5e250-107">**Suggested**: A topic has been identified by AI and has enough supporting resources, connections, and properties.</span></span>
- <span data-ttu-id="5e250-108">**Confirmado**: Um tópico sugerido pela AI é validado.</span><span class="sxs-lookup"><span data-stu-id="5e250-108">**Confirmed**: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="5e250-109">A validação é feita por confirmação de um gerente de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="5e250-109">Validation is done by confirmation from a knowledge manager.</span></span> <span data-ttu-id="5e250-110">Além disso, um tópico pode ser confirmado se houver 2 votos positivos líquidos dos usuários finais recebidos por meio dos mecanismos de feedback no cartão de tópico.</span><span class="sxs-lookup"><span data-stu-id="5e250-110">Additionally, a topic can be confirmed if there is a net positive 2 votes from end users received via the feedback mechanisms on the topic card.</span></span>
- <span data-ttu-id="5e250-111">**Publicado**: Um tópico confirmado que foi abordado: foram feitas edições manuais para melhorar sua qualidade.</span><span class="sxs-lookup"><span data-stu-id="5e250-111">**Published**: A confirmed topic that has been curated: manual edits have been made to improve its quality.</span></span>
- <span data-ttu-id="5e250-112">**Removido**: um tópico é rejeitado por um gerente de conhecimento e não será mais visível para os visualizadores.</span><span class="sxs-lookup"><span data-stu-id="5e250-112">**Removed**: A topic is rejected by a knowledge manager and will no longer be visible to viewers.</span></span> <span data-ttu-id="5e250-113">O tópico pode estar em qualquer estado quando é removido (sugerido, confirmado ou publicado).</span><span class="sxs-lookup"><span data-stu-id="5e250-113">The topic can be in any state when it is removed (suggested, confirmed, or published).</span></span> <span data-ttu-id="5e250-114">Quando um tópico publicado é removido, a página com os detalhes de cura precisará ser excluída manualmente por meio da Biblioteca de Páginas do centro de tópicos.</span><span class="sxs-lookup"><span data-stu-id="5e250-114">When a published topic is removed, the page with the curated details will need to be deleted manually through the Pages Library of the topic center.</span></span>

   ![Gráfico de ciclo de vida do tópico](../media/knowledge-management/topic-lifecycle.png) </br> 

> [!Note] 
> <span data-ttu-id="5e250-116">Na página Gerenciar Tópicos, cada gerente de conhecimento só poderá ver tópicos em que eles tenham acesso aos arquivos e páginas subjacentes conectados ao tópico.</span><span class="sxs-lookup"><span data-stu-id="5e250-116">On the Manage Topics page, each knowledge manager will only be able to see topics where they have access to the underlying files and pages connected to the topic.</span></span> <span data-ttu-id="5e250-117">Essa aparação de permissão será refletida na lista de tópicos que aparecem nas guias **Sugeridas** **,** **Confirmadas,** Removidas e **Publicadas.**</span><span class="sxs-lookup"><span data-stu-id="5e250-117">This permission trimming will be reflected in the list of topics that appear in the **Suggested**, **Confirmed**, **Removed**, and **Published** tabs.</span></span> <span data-ttu-id="5e250-118">O tópico conta, no entanto, mostrar o total de contagens na organização, independentemente das permissões.</span><span class="sxs-lookup"><span data-stu-id="5e250-118">The topic counts, however, show the total counts in the organization regardless of permissions.</span></span>

## <a name="requirements"></a><span data-ttu-id="5e250-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5e250-119">Requirements</span></span>

<span data-ttu-id="5e250-120">Para gerenciar tópicos no centro de tópicos, você precisa:</span><span class="sxs-lookup"><span data-stu-id="5e250-120">To manage topics in the topic center, you need to:</span></span>
- <span data-ttu-id="5e250-121">Tenha uma licença de Tópicos do Viva.</span><span class="sxs-lookup"><span data-stu-id="5e250-121">Have a Viva Topics license.</span></span>

- <span data-ttu-id="5e250-122">Tenha a [**permissão Quem pode gerenciar tópicos.**](./topic-experiences-user-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="5e250-122">Have the [**Who can manage topics**](./topic-experiences-user-permissions.md) permission.</span></span> <span data-ttu-id="5e250-123">Os administradores de conhecimento podem dar aos usuários essa permissão nas configurações de permissões do tópico Tópicos do Viva.</span><span class="sxs-lookup"><span data-stu-id="5e250-123">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

<span data-ttu-id="5e250-124">Você não poderá exibir a página Gerenciar Tópicos no centro de tópicos, a menos que você tenha a permissão **Quem pode gerenciar tópicos.**</span><span class="sxs-lookup"><span data-stu-id="5e250-124">You will not be able to view the Manage Topics page in the topic center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="5e250-125">No centro de tópicos, um gerente de conhecimento pode revisar tópicos que foram identificados nos locais de origem especificados e podem confirmá-los ou rejeitá-los.</span><span class="sxs-lookup"><span data-stu-id="5e250-125">In the topic center, a knowledge manager can review topics that have been identified in the source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="5e250-126">Um gerente de conhecimento também pode criar e publicar novas páginas de tópicos se uma não foi encontrada na descoberta de tópicos ou editar as existentes, caso precisem ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="5e250-126">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="5e250-127">Revisar tópicos sugeridos</span><span class="sxs-lookup"><span data-stu-id="5e250-127">Review suggested topics</span></span>

<span data-ttu-id="5e250-128">Na página Gerenciar Tópicos do centro de tópicos, os tópicos que foram descobertos em seus locais de origem especificados do SharePoint serão listados na **guia Sugerido.** Se necessário, um gerente de conhecimento pode revisar tópicos não confirmados e optar por confirmá-los ou rejeitá-los.</span><span class="sxs-lookup"><span data-stu-id="5e250-128">On the topic center Manage Topics page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. If needed, a knowledge manager can review unconfirmed topics and choose to confirm or reject them.</span></span>

   ![Tópicos sugeridos](../media/knowledge-management/quality-score.png) </br> 

<span data-ttu-id="5e250-130">Para revisar um tópico sugerido:</span><span class="sxs-lookup"><span data-stu-id="5e250-130">To review a suggested topic:</span></span>

1. <span data-ttu-id="5e250-131">Na página **Gerenciar tópicos,** selecione a **guia Sugerido,** selecione o tópico para abrir a página de tópicos.</span><span class="sxs-lookup"><span data-stu-id="5e250-131">On the **Manage topics** page, select the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="5e250-132">Na página de tópicos, revise a página de tópicos e selecione **Editar** se precisar fazer alterações na página.</span><span class="sxs-lookup"><span data-stu-id="5e250-132">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span> <span data-ttu-id="5e250-133">A publicação de todas as edições moverá este tópico para a **guia Publicado.**</span><span class="sxs-lookup"><span data-stu-id="5e250-133">Publishing any edits will move this topic to the **Published** tab.</span></span>

3. <span data-ttu-id="5e250-134">Depois de revisar o tópico, volte para a página Gerenciar Tópicos.</span><span class="sxs-lookup"><span data-stu-id="5e250-134">After reviewing the topic, go back to the Manage Topics page.</span></span> <span data-ttu-id="5e250-135">Para o tópico selecionado, você pode:</span><span class="sxs-lookup"><span data-stu-id="5e250-135">For the selected topic, you can:</span></span>

   - <span data-ttu-id="5e250-136">Selecione a marca de seleção para confirmar o tópico.</span><span class="sxs-lookup"><span data-stu-id="5e250-136">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="5e250-137">Selecione **o x** se quiser rejeitar o tópico.</span><span class="sxs-lookup"><span data-stu-id="5e250-137">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="5e250-138">Os tópicos confirmados serão removidos da **lista Sugerida** e agora serão exibidos na **lista Confirmado.**</span><span class="sxs-lookup"><span data-stu-id="5e250-138">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="5e250-139">Os tópicos rejeitados serão removidos da lista **Sugerida** e agora serão exibidos na **guia Removido.**</span><span class="sxs-lookup"><span data-stu-id="5e250-139">Rejected topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

   </br> 

### <a name="quality-score"></a><span data-ttu-id="5e250-140">Pontuação de qualidade</span><span class="sxs-lookup"><span data-stu-id="5e250-140">Quality score</span></span>

<span data-ttu-id="5e250-141">Cada tópico que aparece na página Tópicos Sugeridos tem uma pontuação de qualidade atribuída a ele.</span><span class="sxs-lookup"><span data-stu-id="5e250-141">Each topic that appears on your Suggested Topics page has a quality score assigned to it.</span></span> <span data-ttu-id="5e250-142">A pontuação de qualidade é um reflexo da quantidade de informações que o usuário médio verá para obter as informações sobre o tópico, tendo em mente que cada usuário pode ver mais ou menos informações devido às permissões que podem ou não ter sobre as informações em um tópico.</span><span class="sxs-lookup"><span data-stu-id="5e250-142">The quality score is a reflection of the amount of information that the average user will see for the information on the topic, keeping in mind that each user might see more or less information because of the permissions they might or might not have on the information in a topic.</span></span> 

<span data-ttu-id="5e250-143">A pontuação de qualidade pode ajudar a dar informações sobre os tópicos com mais informações e pode ser útil para encontrar tópicos que podem precisar ser editados manualmente.</span><span class="sxs-lookup"><span data-stu-id="5e250-143">The quality score can help give insight to the topics with the most information and can be useful for finding topics that may need to be manually edited.</span></span> <span data-ttu-id="5e250-144">Por exemplo, um tópico com uma pontuação de qualidade menor pode ser o resultado de alguns usuários não terem permissões do SharePoint para arquivos ou sites pertinentes que a AI incluiu no tópico.</span><span class="sxs-lookup"><span data-stu-id="5e250-144">For example, a topic with a lower quality score might be the result of some users not having SharePoint permissions to pertinent files or sites that AI has included in the topic.</span></span> <span data-ttu-id="5e250-145">Em seguida, um colaborador pode editar o tópico para incluir as informações (quando apropriado), que serão visualizadas para todos os usuários que podem exibir o tópico.</span><span class="sxs-lookup"><span data-stu-id="5e250-145">A contributor could then edit the topic to include the information (when appropriate), which will then be viewable to all users who can view the topic.</span></span>

### <a name="impressions"></a><span data-ttu-id="5e250-146">Impressões</span><span class="sxs-lookup"><span data-stu-id="5e250-146">Impressions</span></span>

<span data-ttu-id="5e250-147">A **coluna Impressões** exibe o número de vezes que um tópico foi mostrado aos usuários finais.</span><span class="sxs-lookup"><span data-stu-id="5e250-147">The **Impressions** column displays the number of times a topic has been shown to end users.</span></span> <span data-ttu-id="5e250-148">Isso inclui exibições por meio de cartões de resposta de tópicos na pesquisa e nos destaques do tópico.</span><span class="sxs-lookup"><span data-stu-id="5e250-148">This includes views through topic answer cards in search and through topic highlights.</span></span> <span data-ttu-id="5e250-149">Ele não reflete o clique sobre esses tópicos, mas que o tópico foi exibido.</span><span class="sxs-lookup"><span data-stu-id="5e250-149">It does not reflect the click-through on these topics, but that the topic has been displayed.</span></span> <span data-ttu-id="5e250-150">A **coluna Impressões** mostrará tópicos nas guias **Sugeridas** **,** Confirmadas, Publicadas e Removidas na página Gerenciar Tópicos. </span><span class="sxs-lookup"><span data-stu-id="5e250-150">The **Impressions** column will show for topics in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs on the Manage Topics page.</span></span>

## <a name="confirmed-topics"></a><span data-ttu-id="5e250-151">Tópicos confirmados</span><span class="sxs-lookup"><span data-stu-id="5e250-151">Confirmed topics</span></span>

<span data-ttu-id="5e250-152">Na página Gerenciar Tópicos, os tópicos que foram descobertos em seus locais de origem especificados do SharePoint e foram confirmados por um gerente de conhecimento ou "crowdsourced" confirmados por uma rede de duas ou mais pessoas (balanceamento de votos de usuários negativos contra votos positivos de usuários) por meio do mecanismo de feedback de cartão serão listados na guia Confirmado.  Se necessário, um usuário com permissões para gerenciar tópicos pode revisar tópicos confirmados e optar por rejeitá-los.</span><span class="sxs-lookup"><span data-stu-id="5e250-152">On the Manage Topics page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowdsourced" confirmed by a net two or more people (balancing negative user votes against positive user votes) through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="5e250-153">Para revisar um tópico confirmado:</span><span class="sxs-lookup"><span data-stu-id="5e250-153">To review a confirmed topic:</span></span>

1. <span data-ttu-id="5e250-154">Na guia **Confirmado,** selecione o tópico para abrir a página de tópicos.</span><span class="sxs-lookup"><span data-stu-id="5e250-154">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="5e250-155">Na página de tópicos, revise a página de tópicos e selecione **Editar** se precisar fazer alterações na página.</span><span class="sxs-lookup"><span data-stu-id="5e250-155">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="5e250-156">Observe que você ainda pode optar por rejeitar um tópico confirmado.</span><span class="sxs-lookup"><span data-stu-id="5e250-156">Note that you can still choose to reject a confirmed topic.</span></span> <span data-ttu-id="5e250-157">Para fazer isso, vá para  o tópico selecionado na guia Confirmado e selecione **o x** se quiser rejeitar o tópico.</span><span class="sxs-lookup"><span data-stu-id="5e250-157">To do this, go to the selected topic on the **Confirmed** tab, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="5e250-158">Tópicos publicados</span><span class="sxs-lookup"><span data-stu-id="5e250-158">Published topics</span></span>
<span data-ttu-id="5e250-159">Os tópicos publicados foram editados para que informações específicas sempre apareçam para quem encontrar a página.</span><span class="sxs-lookup"><span data-stu-id="5e250-159">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="5e250-160">Os tópicos criados manualmente também estão listados aqui.</span><span class="sxs-lookup"><span data-stu-id="5e250-160">Manually created topics are listed here as well.</span></span>

   ![Gerenciar tópicos](../media/knowledge-management/manage-topics-new.png) </br>
