---
title: Microsoft Viva Topics security trimming
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
description: Visão geral de como a segurança é usada para exibir tópicos.
ms.openlocfilehash: 12a2ad34c55cd63468266abca1fa053048053dd2
ms.sourcegitcommit: 88820cd2536a7da868e472d10b4d265c52e5692b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "50279327"
---
# <a name="microsoft-viva-topics-security-trimming"></a><span data-ttu-id="88997-103">Microsoft Viva Topics security trimming</span><span class="sxs-lookup"><span data-stu-id="88997-103">Microsoft Viva Topics security trimming</span></span> 

<span data-ttu-id="88997-104">Os usuários de Tópicos do Viva não podem exibir informações em tópicos que suas permissões existentes do Office 365 os impedem de ver.</span><span class="sxs-lookup"><span data-stu-id="88997-104">Viva Topics users can't view information in topics that their existing Office 365 permissions prevent them from seeing.</span></span> <span data-ttu-id="88997-105">Tudo o que um usuário vê em uma página de tópico (por exemplo, sites do SharePoint, documentos, arquivos) será informações que ele já tem permissão para ver.</span><span class="sxs-lookup"><span data-stu-id="88997-105">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="88997-106">O Viva Topics não faz alterações em quaisquer permissões existentes.</span><span class="sxs-lookup"><span data-stu-id="88997-106">Viva Topics does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="88997-107">Por que dois usuários podem ter diferentes exibições do mesmo tópico</span><span class="sxs-lookup"><span data-stu-id="88997-107">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="88997-108">Quando um tópico é criado por meio de IA ou de uma correção manual, ele pode conter uma descrição do tópico, nomes alternativos, pessoas associadas ao tópico, bem como sites, páginas e arquivos relacionados ao tópico.</span><span class="sxs-lookup"><span data-stu-id="88997-108">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="88997-109">Quando essas informações são exibidas em uma página de tópico, é possível que dois usuários que estão exibindo o mesmo tópico não vejam as mesmas informações.</span><span class="sxs-lookup"><span data-stu-id="88997-109">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="88997-110">Por exemplo, quando o Usuário 1 exibir a página de tópicos Dolm, ele poderá ver essa exibição da página de tópico.</span><span class="sxs-lookup"><span data-stu-id="88997-110">For example, when User 1 views the Neptune topic page, they might see this view of the topic page.</span></span>

![Tópico de Mila para o usuário 1](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="88997-112">No entanto, quando o Usuário 2 analisa a mesma página de tópicos do Brasil, sua exibição difere do Usuário 1.</span><span class="sxs-lookup"><span data-stu-id="88997-112">However, when User 2 looks at the same Neptune topic page, their view differs from User 1.</span></span>  <span data-ttu-id="88997-113">O usuário 2 pode ver o arquivo de Visão Geral  do Produto *DG-2000* na seção Arquivos fixados e páginas da página de tópico, que não aparece para o Usuário 1.</span><span class="sxs-lookup"><span data-stu-id="88997-113">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![Tópico de Mila para o usuário 2](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="88997-115">A diferença no que os usuários podem ver no mesmo tópico é que os usuários podem não ter as permissões do Office 365 para exibir um site ou arquivo relacionado.</span><span class="sxs-lookup"><span data-stu-id="88997-115">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="88997-116">Os Tópicos do Viva respeitam as permissões definidas nos itens de um tópico e não podem alterar o acesso a elas.</span><span class="sxs-lookup"><span data-stu-id="88997-116">Viva Topics respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="88997-117">No nosso exemplo, o Usuário 1 não consegue exibir o arquivo de Visão Geral do Produto *DG-2000* na página de tópicos de Mila porque o Usuário 1 não tem permissões do Office 365 para exibir o arquivo.</span><span class="sxs-lookup"><span data-stu-id="88997-117">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="88997-118">Se um usuário não conseguir ver informações suficientes em um tópico para que ele seja útil, o tópico não estará disponível para o usuário.</span><span class="sxs-lookup"><span data-stu-id="88997-118">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="88997-119">Quando isso acontece, o usuário não verá o tópico realçado.</span><span class="sxs-lookup"><span data-stu-id="88997-119">When this happens, the user will not see the highlighted topic.</span></span> <span data-ttu-id="88997-120">Um usuário diferente que tenha permissões para obter mais informações no tópico para que ele seja útil, poderá ver o tópico.</span><span class="sxs-lookup"><span data-stu-id="88997-120">A different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="88997-121">Permissões de tópico para gerentes de conhecimento e colaboradores de tópicos</span><span class="sxs-lookup"><span data-stu-id="88997-121">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="88997-122">Os usuários que receberem permissões para gerenciar tópicos - gerentes de conhecimento - só poderão exibir informações que eles têm permissão para ver em tópicos.</span><span class="sxs-lookup"><span data-stu-id="88997-122">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="88997-123">Da mesma forma, os usuários que criaram e editaram permissões de tópico, colaboradores de tópicos, só poderão exibir as informações que têm permissão para ver nos tópicos.</span><span class="sxs-lookup"><span data-stu-id="88997-123">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="88997-124">Ia versus informações de tópicos manualmente abordados</span><span class="sxs-lookup"><span data-stu-id="88997-124">AI versus manually curated topic information</span></span>

<span data-ttu-id="88997-125">Os tópicos podem conter informações geradas pela IA e informações adicionadas ou editadas por colaboradores de tópicos ou gerentes de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="88997-125">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="88997-126">As informações em um tópico que foi adicionado pela ia só são visíveis para as pessoas que têm acesso ao conteúdo de origem.</span><span class="sxs-lookup"><span data-stu-id="88997-126">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="88997-127">A descrição do tópico e as informações de pessoas que foram adicionadas ou editadas manualmente por um colaborador de tópico ou gerente de conhecimento estão visíveis para todos que podem ver o tópico.</span><span class="sxs-lookup"><span data-stu-id="88997-127">Topic description and people information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>
 - <span data-ttu-id="88997-128">Arquivos, páginas e sites só ficam visíveis para os usuários que têm permissões para o conteúdo de origem, sejam adicionados manualmente ou adicionados pelo ia.</span><span class="sxs-lookup"><span data-stu-id="88997-128">Files, pages, and sites are only visible to users who have permissions to the source content, whether manually added or added by AI.</span></span>

<span data-ttu-id="88997-129">A tabela a seguir descreve o que os usuários ( visualizadores de tópicos, colaboradores e gerentes de conhecimento ) podem ver em um determinado tópico com base em suas permissões.</span><span class="sxs-lookup"><span data-stu-id="88997-129">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="88997-130">Item de tópico</span><span class="sxs-lookup"><span data-stu-id="88997-130">Topic item</span></span>|<span data-ttu-id="88997-131">O que os usuários podem ver</span><span class="sxs-lookup"><span data-stu-id="88997-131">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="88997-132">Nome do tópico</span><span class="sxs-lookup"><span data-stu-id="88997-132">Topic name</span></span>|<span data-ttu-id="88997-133">Os usuários podem ver o nome do tópico de todos os tópicos no centro de tópicos.</span><span class="sxs-lookup"><span data-stu-id="88997-133">Users can see the topic name of all topics in the topic center.</span></span> <span data-ttu-id="88997-134">Alguns tópicos podem não estar visíveis se eles têm uma baixa relevância para o usuário.</span><span class="sxs-lookup"><span data-stu-id="88997-134">Some topics may not be visible if they have a low relevancy to the user.</span></span>|
|<span data-ttu-id="88997-135">Descrição do tópico</span><span class="sxs-lookup"><span data-stu-id="88997-135">Topic description</span></span>|<span data-ttu-id="88997-136">As descrições geradas por IA são visíveis apenas para usuários que têm permissões para o conteúdo de origem.</span><span class="sxs-lookup"><span data-stu-id="88997-136">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="88997-137">As descrições inseridas ou editadas manualmente ficam visíveis para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="88997-137">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="88997-138">Pessoas</span><span class="sxs-lookup"><span data-stu-id="88997-138">People</span></span>|<span data-ttu-id="88997-139">As pessoas fixadas ficam visíveis para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="88997-139">Pinned people are visible to all users.</span></span> <span data-ttu-id="88997-140">As pessoas sugeridas só ficam visíveis para os usuários que têm permissões para o conteúdo de origem.</span><span class="sxs-lookup"><span data-stu-id="88997-140">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="88997-141">Arquivos</span><span class="sxs-lookup"><span data-stu-id="88997-141">Files</span></span>|<span data-ttu-id="88997-142">Os arquivos só ficam visíveis para os usuários que têm permissões para o conteúdo de origem.</span><span class="sxs-lookup"><span data-stu-id="88997-142">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="88997-143">Páginas</span><span class="sxs-lookup"><span data-stu-id="88997-143">Pages</span></span>|<span data-ttu-id="88997-144">As páginas só ficam visíveis para os usuários que têm permissões para o conteúdo de origem.</span><span class="sxs-lookup"><span data-stu-id="88997-144">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="88997-145">Sites</span><span class="sxs-lookup"><span data-stu-id="88997-145">Sites</span></span>|<span data-ttu-id="88997-146">Os sites só ficam visíveis para os usuários que têm permissões para o conteúdo de origem.</span><span class="sxs-lookup"><span data-stu-id="88997-146">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="88997-147">Confira também</span><span class="sxs-lookup"><span data-stu-id="88997-147">See also</span></span>

