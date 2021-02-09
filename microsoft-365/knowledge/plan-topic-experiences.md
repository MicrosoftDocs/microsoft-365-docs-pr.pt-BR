---
title: Planejar tópicos do Microsoft Viva
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Saiba como planejar o planejamento de tópicos do Microsoft Viva
ms.openlocfilehash: 2f7b85399f0b1f49e25aae1f1d4627413594f618
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150473"
---
# <a name="plan-for-microsoft-viva-topics"></a><span data-ttu-id="6bafa-103">Planejar tópicos do Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="6bafa-103">Plan for Microsoft Viva Topics</span></span>

<span data-ttu-id="6bafa-104">Você controla como os tópicos são experientes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="6bafa-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="6bafa-105">Suas decisões de planejamento para Tópicos garantem que os tópicos de alta qualidade sejam mostrados aos seus usuários e que eles tenham as permissões corretas para consumir e contribuir com o conhecimento.</span><span class="sxs-lookup"><span data-stu-id="6bafa-105">Your planning decisions for Topics ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="6bafa-106">Neste artigo, examinaremos estas decisões de planejamento:</span><span class="sxs-lookup"><span data-stu-id="6bafa-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="6bafa-107">Quais sites do SharePoint você deseja rastrear para tópicos</span><span class="sxs-lookup"><span data-stu-id="6bafa-107">Which SharePoint sites you want to crawl for topics</span></span>
- <span data-ttu-id="6bafa-108">Quais tópicos, se algum, você deseja excluir das experiências de tópico</span><span class="sxs-lookup"><span data-stu-id="6bafa-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="6bafa-109">Para quais usuários você deseja tornar os tópicos visíveis</span><span class="sxs-lookup"><span data-stu-id="6bafa-109">Which users you want to make topics visible to</span></span>
- <span data-ttu-id="6bafa-110">Quais usuários você deseja dar permissões para gerenciar tópicos no centro de tópicos</span><span class="sxs-lookup"><span data-stu-id="6bafa-110">Which users you want to give permissions to manage topics in the topic center</span></span>
- <span data-ttu-id="6bafa-111">Quais usuários você deseja dar permissões para criar ou editar tópicos no centro de tópicos</span><span class="sxs-lookup"><span data-stu-id="6bafa-111">Which users you want to give permissions to create or edit topics in the topic center</span></span>
- <span data-ttu-id="6bafa-112">Qual nome você deseja dar ao seu centro de tópicos</span><span class="sxs-lookup"><span data-stu-id="6bafa-112">What name you want to give your topic center</span></span>

<span data-ttu-id="6bafa-113">A segurança e a privacidade dos seus dados são respeitadas, e as experiências de tópico não concedem aos usuários acesso adicional aos arquivos aos que eles não têm direitos.</span><span class="sxs-lookup"><span data-stu-id="6bafa-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="6bafa-114">Recomendamos que você leia também a segurança e a privacidade [dos Tópicos](topic-experiences-security-privacy.md) do Microsoft Viva como parte do seu processo de planejamento.</span><span class="sxs-lookup"><span data-stu-id="6bafa-114">We recommend you also read [Microsoft Viva Topics security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

## <a name="requirements"></a><span data-ttu-id="6bafa-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6bafa-115">Requirements</span></span>

<span data-ttu-id="6bafa-116">Você deve estar inscrito nos [Tópicos](https://www.microsoft.com/microsoft-viva/topics) do Viva e ser um administrador global ou administrador do SharePoint para acessar o centro de administração do Microsoft 365 e configurar Tópicos.</span><span class="sxs-lookup"><span data-stu-id="6bafa-116">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="6bafa-117">Todos os usuários que usarão Tópicos exigem uma licença **de Experiências de** Tópico.</span><span class="sxs-lookup"><span data-stu-id="6bafa-117">All users who are going to use Topics require a **Topic Experiences** license.</span></span> <span data-ttu-id="6bafa-118">A atribuição de licenças é [abordada em Configurar tópicos do Microsoft Viva.](set-up-topic-experiences.md)</span><span class="sxs-lookup"><span data-stu-id="6bafa-118">Assigning licenses is covered in [Set up Microsoft Viva Topics](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="6bafa-119">Descoberta de tópicos</span><span class="sxs-lookup"><span data-stu-id="6bafa-119">Topic discovery</span></span>

<span data-ttu-id="6bafa-120">As configurações de descoberta de tópico especificam quais sites do SharePoint são usados como fontes para tópicos.</span><span class="sxs-lookup"><span data-stu-id="6bafa-120">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="6bafa-121">Você pode optar por incluir todos os sites do SharePoint, uma lista específica de sites ou nenhum site.</span><span class="sxs-lookup"><span data-stu-id="6bafa-121">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="6bafa-122">Recomendamos que você escolha todos os sites para que as experiências de tópico possam descobrir um grande número de tópicos bons para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="6bafa-122">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="6bafa-123">Ao configurar tópicos, você pode escolher entre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="6bafa-123">When you set up Topics, you can choose from the following options:</span></span>

- <span data-ttu-id="6bafa-124">**Todos os sites:** todos os sites do SharePoint em sua organização.</span><span class="sxs-lookup"><span data-stu-id="6bafa-124">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="6bafa-125">Isso inclui sites atuais e futuros.</span><span class="sxs-lookup"><span data-stu-id="6bafa-125">This includes current and future sites.</span></span>
- <span data-ttu-id="6bafa-126">**Todos, exceto os sites selecionados:** todos os sites, exceto aqueles que você especificar.</span><span class="sxs-lookup"><span data-stu-id="6bafa-126">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="6bafa-127">Os sites criados no futuro serão incluídos como fontes para descoberta de tópicos.</span><span class="sxs-lookup"><span data-stu-id="6bafa-127">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="6bafa-128">**Somente sites selecionados:** somente os sites que você especificar.</span><span class="sxs-lookup"><span data-stu-id="6bafa-128">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="6bafa-129">Os sites criados no futuro não serão incluídos como fontes para descoberta de tópicos.</span><span class="sxs-lookup"><span data-stu-id="6bafa-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="6bafa-130">**Nenhum site:** não inclua sites do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6bafa-130">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="6bafa-131">Se você escolher **Todos,** exceto sites selecionados ou Apenas **sites** selecionados, poderá carregar um arquivo .csv com uma lista de sites.</span><span class="sxs-lookup"><span data-stu-id="6bafa-131">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="6bafa-132">Essas opções são úteis se você estiver fazendo um piloto e quiser incluir um número limitado de sites para iniciar.</span><span class="sxs-lookup"><span data-stu-id="6bafa-132">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="6bafa-133">Você pode copiar o modelo .csv abaixo:</span><span class="sxs-lookup"><span data-stu-id="6bafa-133">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="6bafa-134">Não recomendamos escolher Nenhum **site porque** impede que os tópicos são criados ou atualizados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6bafa-134">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="6bafa-135">No entanto, você pode escolher essa opção se quiser configurar Tópicos e adicionar sites mais tarde.</span><span class="sxs-lookup"><span data-stu-id="6bafa-135">However, you can choose this option if you want to set up Topics and then add sites later.</span></span>

<span data-ttu-id="6bafa-136">Recomendamos que você crie um processo para que os usuários ou gerentes de conhecimento solicitem que sites individuais sejam removidos da descoberta de tópicos, se necessário, em sua organização.</span><span class="sxs-lookup"><span data-stu-id="6bafa-136">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="6bafa-137">Permissões do usuário</span><span class="sxs-lookup"><span data-stu-id="6bafa-137">User permissions</span></span>

<span data-ttu-id="6bafa-138">As permissões de usuário especificadas determinam quais pessoas em sua organização interagem com tópicos e o que elas podem fazer.</span><span class="sxs-lookup"><span data-stu-id="6bafa-138">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

<span data-ttu-id="6bafa-139">*Gerenciar tópicos*</span><span class="sxs-lookup"><span data-stu-id="6bafa-139">*Manage topics*</span></span>

<span data-ttu-id="6bafa-140">Gerentes de conhecimento supervisionam a qualidade das informações, como ela é estruturada e outras práticas recomendadas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="6bafa-140">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="6bafa-141">Eles podem confirmar e rejeitar tópicos.</span><span class="sxs-lookup"><span data-stu-id="6bafa-141">They can confirm and reject topics.</span></span>

<span data-ttu-id="6bafa-142">Embora você possa especificar gerentes de tópico individuais, recomendamos que você crie um grupo de segurança (ou use um existente) que contenha as pessoas que você deseja que sejam gerentes de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="6bafa-142">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="6bafa-143">Você pode especificar esse grupo de segurança durante o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="6bafa-143">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="6bafa-144">*Criar e editar tópicos*</span><span class="sxs-lookup"><span data-stu-id="6bafa-144">*Create and edit topics*</span></span>

<span data-ttu-id="6bafa-145">Os colaboradores do tópico são os campeões e especialistas no assunto em sua organização.</span><span class="sxs-lookup"><span data-stu-id="6bafa-145">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="6bafa-146">Eles podem criar e editar tópicos.</span><span class="sxs-lookup"><span data-stu-id="6bafa-146">They can create and edit topics.</span></span> 

<span data-ttu-id="6bafa-147">Recomendamos que você permita que todos em sua organização criem e editem tópicos porque as experiências de tópico funcionam melhor quando todos os usuários podem compartilhar informações.</span><span class="sxs-lookup"><span data-stu-id="6bafa-147">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="6bafa-148">Se você deseja limitar a criação e edição de tópicos a pessoas ou grupos específicos, crie um grupo de segurança para eles e especifique-o durante o processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="6bafa-148">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="6bafa-149">Você pode optar por não permitir que ninguém contribua para tópicos, no entanto, isso não é recomendado.</span><span class="sxs-lookup"><span data-stu-id="6bafa-149">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="6bafa-150">Os gerentes de conhecimento ainda poderão editar e criar tópicos se você escolher essa opção.</span><span class="sxs-lookup"><span data-stu-id="6bafa-150">Knowledge managers will still be able to edit and create topics if you choose this option.</span></span>

<span data-ttu-id="6bafa-151">*Visualizadores de tópicos*</span><span class="sxs-lookup"><span data-stu-id="6bafa-151">*Topic viewers*</span></span>

<span data-ttu-id="6bafa-152">Os visualizadores de tópicos podem ver informações em páginas de tópicos, nos resultados da pesquisa e quando os tópicos são realçados no conteúdo, como páginas do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6bafa-152">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="6bafa-153">Os usuários só podem ver tópicos descobertos quando têm acesso aos arquivos e páginas em que o tópico foi descoberto.</span><span class="sxs-lookup"><span data-stu-id="6bafa-153">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="6bafa-154">Ao configurar os visualizadores de tópico, você pode escolher entre:</span><span class="sxs-lookup"><span data-stu-id="6bafa-154">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="6bafa-155">**Todos na minha organização**</span><span class="sxs-lookup"><span data-stu-id="6bafa-155">**Everyone in my organization**</span></span>
- <span data-ttu-id="6bafa-156">**Somente pessoas ou grupos de segurança selecionados**</span><span class="sxs-lookup"><span data-stu-id="6bafa-156">**Only selected people or security groups**</span></span>
- <span data-ttu-id="6bafa-157">**Ninguém**</span><span class="sxs-lookup"><span data-stu-id="6bafa-157">**No one**</span></span>

<span data-ttu-id="6bafa-158">Recomendamos **Todos na minha organização,** mas se você estiver fazendo um piloto, talvez queira escolher apenas pessoas ou grupos de segurança selecionados.</span><span class="sxs-lookup"><span data-stu-id="6bafa-158">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="6bafa-159">Você também pode **escolher Ninguém se** quiser configurar Tópicos, mas ainda não permitir que as pessoas vejam tópicos.</span><span class="sxs-lookup"><span data-stu-id="6bafa-159">You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet.</span></span> <span data-ttu-id="6bafa-160">(Os gerentes de conhecimento ainda terão acesso para permitir que eles consultem os tópicos e ajudar na decisão de tornar os Tópicos amplamente disponíveis.)</span><span class="sxs-lookup"><span data-stu-id="6bafa-160">(Knowledge managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="6bafa-161">Regras de conhecimento</span><span class="sxs-lookup"><span data-stu-id="6bafa-161">Knowledge rules</span></span>

<span data-ttu-id="6bafa-162">Como administrador, você pode excluir determinados tópicos de experiências de tópicos.</span><span class="sxs-lookup"><span data-stu-id="6bafa-162">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="6bafa-163">Isso será útil se você quiser evitar que dados confidenciais apareçam em tópicos.</span><span class="sxs-lookup"><span data-stu-id="6bafa-163">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="6bafa-164">Embora os gerentes de conhecimento possam excluir tópicos no centro de tópicos, os tópicos excluídos pelo administrador nem mesmo são visíveis para os gerentes de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="6bafa-164">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="6bafa-165">(Os gerentes de conhecimento também podem remover tópicos no centro de tópicos após a descoberta.)</span><span class="sxs-lookup"><span data-stu-id="6bafa-165">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="6bafa-166">Se quiser excluir tópicos no nível do administrador, você deve adicioná-los a um arquivo .csv e carregar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="6bafa-166">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="6bafa-167">Você pode fazer isso durante a instalação ou posterior.</span><span class="sxs-lookup"><span data-stu-id="6bafa-167">You can do this during setup or later.</span></span>

<span data-ttu-id="6bafa-168">O arquivo .csv deve conter os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="6bafa-168">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="6bafa-169">**Nome:** digite o nome do tópico que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="6bafa-169">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="6bafa-170">Há duas maneiras de fazer isso:</span><span class="sxs-lookup"><span data-stu-id="6bafa-170">There are two ways to do this:</span></span>
- <span data-ttu-id="6bafa-171">**MatchType-Exact/Partial**: digite se o nome digitado foi um *tipo de* combinação exato *ou* parcial.</span><span class="sxs-lookup"><span data-stu-id="6bafa-171">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="6bafa-172">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span><span class="sxs-lookup"><span data-stu-id="6bafa-172">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="6bafa-173">Parciais: você pode excluir todos os tópicos que têm uma palavra específica.</span><span class="sxs-lookup"><span data-stu-id="6bafa-173">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="6bafa-174">Por exemplo, *o arco* excluirá  todos os tópicos com o arco de palavras nele, como arco *círculo,* arco *de Arc arc arc ou* arco *de treinamento.* Observe que ele não excluirá tópicos nos quais o texto é incluído como parte de uma palavra, *como* Arquitetura .</span><span class="sxs-lookup"><span data-stu-id="6bafa-174">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="6bafa-175">**Significa (opcional)**: (também conhecido como expansão) Se você quiser excluir um acrônimo, digite as palavras que o acrônimo representa.</span><span class="sxs-lookup"><span data-stu-id="6bafa-175">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![Excluir tópicos no modelo CSV](../media/exclude-topics-csv.png) 

<span data-ttu-id="6bafa-177">Você pode copiar o modelo csv abaixo:</span><span class="sxs-lookup"><span data-stu-id="6bafa-177">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="6bafa-178">Administração</span><span class="sxs-lookup"><span data-stu-id="6bafa-178">Administration</span></span>

<span data-ttu-id="6bafa-179">Quando você configura Tópicos, como parte do processo de instalação, um centro de tópicos é criado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6bafa-179">When you set up Topics, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="6bafa-180">Pense em como você deseja nomear o centro de tópicos e o que você deseja que a URL seja.</span><span class="sxs-lookup"><span data-stu-id="6bafa-180">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="6bafa-181">Você pode definir o nome e a URL como parte do processo de instalação e pode alterar o nome (mas não a URL) posteriormente no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6bafa-181">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="6bafa-182">Você só pode ter um centro de tópicos.</span><span class="sxs-lookup"><span data-stu-id="6bafa-182">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="6bafa-183">Lista de verificação de instalação</span><span class="sxs-lookup"><span data-stu-id="6bafa-183">Setup checklist</span></span>

<span data-ttu-id="6bafa-184">Ao configurar experiências de tópico, você precisará dos seguintes itens ao passar pelo assistente de configuração:</span><span class="sxs-lookup"><span data-stu-id="6bafa-184">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="6bafa-185">Lista de sites a incluir ou excluir se não incluir todos os sites para descoberta de tópicos</span><span class="sxs-lookup"><span data-stu-id="6bafa-185">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="6bafa-186">Grupo de segurança para visualizadores de tópicos se não permitir que todos os usuários consultem tópicos</span><span class="sxs-lookup"><span data-stu-id="6bafa-186">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="6bafa-187">Grupo de segurança para colaboradores de tópicos se não permitir que todos os usuários criem e editem tópicos</span><span class="sxs-lookup"><span data-stu-id="6bafa-187">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="6bafa-188">Grupo de segurança para gerentes de conhecimento de tópicos se não permitir que todos os usuários gerenciem tópicos</span><span class="sxs-lookup"><span data-stu-id="6bafa-188">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="6bafa-189">Lista de tópicos confidenciais a excluir da descoberta de tópicos</span><span class="sxs-lookup"><span data-stu-id="6bafa-189">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="6bafa-190">Um nome para seu site central de tópicos</span><span class="sxs-lookup"><span data-stu-id="6bafa-190">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="6bafa-191">Confira também</span><span class="sxs-lookup"><span data-stu-id="6bafa-191">See also</span></span>

[<span data-ttu-id="6bafa-192">Configurar Experiências de tópico</span><span class="sxs-lookup"><span data-stu-id="6bafa-192">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="6bafa-193">Gerenciar a descoberta de tópicos no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6bafa-193">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="6bafa-194">Gerenciar visibilidade do tópico no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6bafa-194">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="6bafa-195">Gerenciar permissões de tópico no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6bafa-195">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="6bafa-196">Alterar o nome do centro de tópicos no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6bafa-196">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
