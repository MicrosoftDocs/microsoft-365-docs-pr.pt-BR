---
title: Tópico experiências de filtragem de segurança (versão prévia)
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Visão geral de como a segurança é usada para exibir tópicos.
ms.openlocfilehash: 7e503082494d27f9418b8e09b8d20d01e4708fe9
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698782"
---
# <a name="topic-experiences-security-trimming-preview"></a><span data-ttu-id="c3246-103">Tópico experiências de filtragem de segurança (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="c3246-103">Topic Experiences security trimming (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="c3246-104">O conteúdo deste artigo é para a visualização privada do Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="c3246-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="c3246-105">[Mais informações sobre o Projeto Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="c3246-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="c3246-106">Tópico experiências os usuários não poderão exibir informações nos tópicos que suas permissões existentes do Office 365 impedem que eles vejam.</span><span class="sxs-lookup"><span data-stu-id="c3246-106">Topic experiences users will not be able to view information in topics that their existing Office 365 permissions prevents them from seeing.</span></span> <span data-ttu-id="c3246-107">Tudo o que um usuário vê em uma página de tópico (por exemplo, sites do SharePoint, documentos, arquivos) serão informações que eles já podem ver.</span><span class="sxs-lookup"><span data-stu-id="c3246-107">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="c3246-108">As experiências de tópico não fazem alterações nas permissões existentes.</span><span class="sxs-lookup"><span data-stu-id="c3246-108">Topic experiences does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="c3246-109">Por que dois usuários podem ter modos de exibição diferentes do mesmo tópico</span><span class="sxs-lookup"><span data-stu-id="c3246-109">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="c3246-110">Quando um tópico é criado através do AI ou da seção de manual, ele pode conter uma descrição do tópico, nomes alternativos, pessoas associadas ao tópico, bem como sites, páginas e arquivos relacionados ao tópico.</span><span class="sxs-lookup"><span data-stu-id="c3246-110">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="c3246-111">Quando essas informações são exibidas em uma página de tópico, é possível que dois usuários que estejam exibindo o mesmo tópico não vejam as mesmas informações.</span><span class="sxs-lookup"><span data-stu-id="c3246-111">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="c3246-112">Por exemplo, quando o usuário 1 exibe a página de tópico Neptune, isso é o que eles podem ver.</span><span class="sxs-lookup"><span data-stu-id="c3246-112">For example, when User 1 views the Neptune topic page, this is what they might see.</span></span>

![Tópico Neptune para o usuário 1](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="c3246-114">No entanto, quando o usuário 2 examina a mesma página de tópico Neptune, seu modo de exibição difere do usuário 1.</span><span class="sxs-lookup"><span data-stu-id="c3246-114">However, when User 2 looks at the same Neptune topic page, her view differs from User 1.</span></span>  <span data-ttu-id="c3246-115">O usuário 2 é capaz de ver o arquivo de *visão geral do produto DG-2000* na seção **arquivos fixos e páginas** da página de tópico, que não aparece para o usuário 1.</span><span class="sxs-lookup"><span data-stu-id="c3246-115">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![Tópico Neptune do usuário 2](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="c3246-117">A diferença no que os usuários podem ver no mesmo tópico é porque os usuários podem não ter as permissões do Office 365 para exibir um site ou arquivo relacionado.</span><span class="sxs-lookup"><span data-stu-id="c3246-117">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="c3246-118">A experiência do tópico respeita as permissões que são definidas nos itens de um tópico e não podem alterar o acesso a elas.</span><span class="sxs-lookup"><span data-stu-id="c3246-118">Topic experiences respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="c3246-119">No nosso exemplo, o usuário 1 não pode exibir o arquivo de *visão geral do produto DG-2000* na página de tópico para Neptune porque o usuário 1 não tem as permissões do Office 365 para exibir o arquivo.</span><span class="sxs-lookup"><span data-stu-id="c3246-119">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="c3246-120">Se um usuário não conseguir ver informações suficientes em um tópico para ser útil, o tópico não estará disponível para o usuário.</span><span class="sxs-lookup"><span data-stu-id="c3246-120">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="c3246-121">Nesse caso, o usuário não verá o tópico realçado.</span><span class="sxs-lookup"><span data-stu-id="c3246-121">In this instance, the user will not see the highlighted topic.</span></span> <span data-ttu-id="c3246-122">No entanto, um usuário diferente que tenha permissões para obter mais informações no tópico para que ele seja útil, poderá ver o tópico.</span><span class="sxs-lookup"><span data-stu-id="c3246-122">However, a different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="c3246-123">Permissões de tópico para gerentes de conhecimento e colaboradores de tópico</span><span class="sxs-lookup"><span data-stu-id="c3246-123">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="c3246-124">Os usuários que receberam permissões para gerenciar tópicos-gerentes de conhecimento – só poderão exibir as informações que têm permissões para ver nos tópicos.</span><span class="sxs-lookup"><span data-stu-id="c3246-124">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="c3246-125">Da mesma forma, os usuários que têm permissões de criação e edição de tópico – os colaboradores do tópico só poderão exibir as informações que têm permissões para ver nos tópicos.</span><span class="sxs-lookup"><span data-stu-id="c3246-125">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="c3246-126">AI versus informações de tópico organizadas manualmente</span><span class="sxs-lookup"><span data-stu-id="c3246-126">AI versus manually curated topic information</span></span>

<span data-ttu-id="c3246-127">Os tópicos podem conter informações geradas pelo AI e informações adicionadas ou editadas por colaboradores de tópico ou gerentes de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="c3246-127">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="c3246-128">As informações de um tópico que foram adicionadas pelo AI são visíveis apenas para pessoas que têm acesso ao conteúdo de origem.</span><span class="sxs-lookup"><span data-stu-id="c3246-128">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="c3246-129">As informações que foram adicionadas ou editadas manualmente por um tópico Contribuidor ou gerente de conhecimento estão visíveis para todas as pessoas que podem ver o tópico.</span><span class="sxs-lookup"><span data-stu-id="c3246-129">Information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>

<span data-ttu-id="c3246-130">A tabela a seguir descreve quais usuários – visualizadores de tópicos, colaboradores e gerentes de conhecimento-podem ver em um determinado tópico com base em suas permissões.</span><span class="sxs-lookup"><span data-stu-id="c3246-130">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="c3246-131">Item de tópico</span><span class="sxs-lookup"><span data-stu-id="c3246-131">Topic item</span></span>|<span data-ttu-id="c3246-132">O que os usuários podem ver</span><span class="sxs-lookup"><span data-stu-id="c3246-132">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="c3246-133">Nome do tópico</span><span class="sxs-lookup"><span data-stu-id="c3246-133">Topic name</span></span>|<span data-ttu-id="c3246-134">Os usuários podem ver o nome do tópico de todos os tópicos no centro de tópicos.</span><span class="sxs-lookup"><span data-stu-id="c3246-134">Users can see the topic name of all topics in the topic center.</span></span> <span data-ttu-id="c3246-135">Alguns tópicos podem não estar visíveis se tiverem uma relevância baixa para o usuário.</span><span class="sxs-lookup"><span data-stu-id="c3246-135">Some topics may not be visible if they have a low relevancy to the user.</span></span>|
|<span data-ttu-id="c3246-136">Descrição do tópico</span><span class="sxs-lookup"><span data-stu-id="c3246-136">Topic description</span></span>|<span data-ttu-id="c3246-137">As descrições geradas pelo AI são visíveis apenas para os usuários que têm permissões para o conteúdo de origem.</span><span class="sxs-lookup"><span data-stu-id="c3246-137">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="c3246-138">Descrições inseridas ou editadas manualmente são visíveis para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="c3246-138">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="c3246-139">Pessoas</span><span class="sxs-lookup"><span data-stu-id="c3246-139">People</span></span>|<span data-ttu-id="c3246-140">Pessoas fixas estão visíveis para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="c3246-140">Pinned people are visible to all users.</span></span> <span data-ttu-id="c3246-141">As pessoas sugeridas são visíveis apenas para os usuários que têm permissões para o conteúdo de origem.</span><span class="sxs-lookup"><span data-stu-id="c3246-141">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="c3246-142">Arquivos</span><span class="sxs-lookup"><span data-stu-id="c3246-142">Files</span></span>|<span data-ttu-id="c3246-143">Os arquivos são visíveis apenas para os usuários que têm permissões para o conteúdo de origem.</span><span class="sxs-lookup"><span data-stu-id="c3246-143">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="c3246-144">Páginas</span><span class="sxs-lookup"><span data-stu-id="c3246-144">Pages</span></span>|<span data-ttu-id="c3246-145">As páginas são visíveis apenas para os usuários que têm permissões para o conteúdo de origem.</span><span class="sxs-lookup"><span data-stu-id="c3246-145">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="c3246-146">Sites</span><span class="sxs-lookup"><span data-stu-id="c3246-146">Sites</span></span>|<span data-ttu-id="c3246-147">Os sites são visíveis apenas para os usuários que têm permissões para o conteúdo de origem.</span><span class="sxs-lookup"><span data-stu-id="c3246-147">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="c3246-148">Confira também</span><span class="sxs-lookup"><span data-stu-id="c3246-148">See also</span></span>

