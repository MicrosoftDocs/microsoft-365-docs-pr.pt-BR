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
description: Saiba como planejar os Tópicos do Microsoft Viva
ms.openlocfilehash: 19baf8bdcfdd1fe38d64e3c2f259ace1ceab5a4b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925971"
---
# <a name="plan-for-microsoft-viva-topics"></a><span data-ttu-id="4460c-103">Planejar tópicos do Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="4460c-103">Plan for Microsoft Viva Topics</span></span>

<span data-ttu-id="4460c-104">Você está no controle de como os tópicos são experimentado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="4460c-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="4460c-105">Suas decisões de planejamento para Tópicos garantem que os tópicos de alta qualidade sejam mostrados aos usuários e que eles tenham as permissões certas para consumir e contribuir com conhecimento.</span><span class="sxs-lookup"><span data-stu-id="4460c-105">Your planning decisions for Topics ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="4460c-106">Neste artigo, examinaremos essas decisões de planejamento:</span><span class="sxs-lookup"><span data-stu-id="4460c-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="4460c-107">Quais sites do SharePoint você deseja rastrear para tópicos</span><span class="sxs-lookup"><span data-stu-id="4460c-107">Which SharePoint sites you want to crawl for topics</span></span>
- <span data-ttu-id="4460c-108">Quais tópicos, se algum, você deseja excluir das experiências de tópico</span><span class="sxs-lookup"><span data-stu-id="4460c-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="4460c-109">Para quais usuários você deseja tornar os tópicos visíveis</span><span class="sxs-lookup"><span data-stu-id="4460c-109">Which users you want to make topics visible to</span></span>
- <span data-ttu-id="4460c-110">Quais usuários você deseja dar permissões para gerenciar tópicos no centro de tópicos</span><span class="sxs-lookup"><span data-stu-id="4460c-110">Which users you want to give permissions to manage topics in the topic center</span></span>
- <span data-ttu-id="4460c-111">Quais usuários você deseja dar permissões para criar ou editar tópicos no centro de tópicos</span><span class="sxs-lookup"><span data-stu-id="4460c-111">Which users you want to give permissions to create or edit topics in the topic center</span></span>
- <span data-ttu-id="4460c-112">Qual nome você deseja dar ao centro de tópicos</span><span class="sxs-lookup"><span data-stu-id="4460c-112">What name you want to give your topic center</span></span>

<span data-ttu-id="4460c-113">A segurança e a privacidade de seus dados são respeitadas, e as experiências de tópico não concedem aos usuários acesso adicional aos arquivos aos que eles não têm direitos.</span><span class="sxs-lookup"><span data-stu-id="4460c-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="4460c-114">Recomendamos que você também leia a segurança e a privacidade [dos Tópicos](topic-experiences-security-privacy.md) do Microsoft Viva como parte do seu processo de planejamento.</span><span class="sxs-lookup"><span data-stu-id="4460c-114">We recommend you also read [Microsoft Viva Topics security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

## <a name="requirements"></a><span data-ttu-id="4460c-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4460c-115">Requirements</span></span>

<span data-ttu-id="4460c-116">Você deve estar inscrito em [Tópicos do Viva](https://www.microsoft.com/microsoft-viva/topics) e ser um administrador global ou administrador do SharePoint para acessar o centro de administração do Microsoft 365 e configurar Tópicos.</span><span class="sxs-lookup"><span data-stu-id="4460c-116">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="4460c-117">Todos os usuários que vão usar Tópicos exigem uma **licença experiências de** tópico.</span><span class="sxs-lookup"><span data-stu-id="4460c-117">All users who are going to use Topics require a **Topic Experiences** license.</span></span> <span data-ttu-id="4460c-118">A atribuição de licenças é abordada [em Configurar Tópicos do Microsoft Viva.](set-up-topic-experiences.md)</span><span class="sxs-lookup"><span data-stu-id="4460c-118">Assigning licenses is covered in [Set up Microsoft Viva Topics](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="4460c-119">Descoberta de tópicos</span><span class="sxs-lookup"><span data-stu-id="4460c-119">Topic discovery</span></span>

<span data-ttu-id="4460c-120">As configurações de descoberta de tópicos especificam quais sites do SharePoint são usados como fontes para tópicos.</span><span class="sxs-lookup"><span data-stu-id="4460c-120">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="4460c-121">Você pode optar por incluir todos os sites do SharePoint, uma lista específica de sites ou nenhum site.</span><span class="sxs-lookup"><span data-stu-id="4460c-121">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="4460c-122">Recomendamos que você escolha todos os sites para que as experiências de tópico possam descobrir um grande número de tópicos bons para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="4460c-122">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="4460c-123">Ao configurar Tópicos, você pode escolher entre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="4460c-123">When you set up Topics, you can choose from the following options:</span></span>

- <span data-ttu-id="4460c-124">**Todos os sites**: Todos os sites do SharePoint em sua organização.</span><span class="sxs-lookup"><span data-stu-id="4460c-124">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="4460c-125">Isso inclui sites atuais e futuros.</span><span class="sxs-lookup"><span data-stu-id="4460c-125">This includes current and future sites.</span></span>
- <span data-ttu-id="4460c-126">**Todos, exceto sites selecionados:** todos os sites, exceto aqueles especificados.</span><span class="sxs-lookup"><span data-stu-id="4460c-126">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="4460c-127">Os sites criados no futuro serão incluídos como fontes para descoberta de tópicos.</span><span class="sxs-lookup"><span data-stu-id="4460c-127">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="4460c-128">**Somente sites selecionados:** somente os sites especificados.</span><span class="sxs-lookup"><span data-stu-id="4460c-128">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="4460c-129">Os sites criados no futuro não serão incluídos como fontes para descoberta de tópicos.</span><span class="sxs-lookup"><span data-stu-id="4460c-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="4460c-130">**Nenhum site**: Não inclua sites do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4460c-130">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="4460c-131">Se você escolher **Todos, exceto sites** selecionados ou Somente **sites** selecionados, poderá carregar um arquivo .csv com uma lista de sites.</span><span class="sxs-lookup"><span data-stu-id="4460c-131">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="4460c-132">Essas opções são úteis se você estiver fazendo um piloto e quiser incluir um número limitado de sites para iniciar.</span><span class="sxs-lookup"><span data-stu-id="4460c-132">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="4460c-133">Você pode copiar o modelo .csv abaixo:</span><span class="sxs-lookup"><span data-stu-id="4460c-133">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="4460c-134">Não recomendamos escolher **Nenhum site** porque impede que os tópicos são criados ou atualizados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4460c-134">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="4460c-135">No entanto, você pode escolher essa opção se quiser configurar Tópicos e adicionar sites posteriormente.</span><span class="sxs-lookup"><span data-stu-id="4460c-135">However, you can choose this option if you want to set up Topics and then add sites later.</span></span>

<span data-ttu-id="4460c-136">Recomendamos que você crie um processo para usuários ou gerentes de conhecimento solicitarem que sites individuais sejam removidos da descoberta de tópicos, se necessário em sua organização.</span><span class="sxs-lookup"><span data-stu-id="4460c-136">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

### <a name="multi-geo"></a><span data-ttu-id="4460c-137">Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="4460c-137">Multi-geo</span></span>

<span data-ttu-id="4460c-138">Se sua organização tiver implantado o [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo), o centro de tópicos será provisionado no local central e somente os sites do SharePoint no local central estarão disponíveis para uso como fontes para tópicos.</span><span class="sxs-lookup"><span data-stu-id="4460c-138">If your organization has deployed [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo), the topic center is provisioned in the central location and only SharePoint sites in the central location are available to use as sources for topics.</span></span> <span data-ttu-id="4460c-139">(Se você selecionar **Todos os sites,** os Tópicos do Viva usarão todos os sites no local central.)</span><span class="sxs-lookup"><span data-stu-id="4460c-139">(If you select **All sites**, Viva Topics will use all site in the central location.)</span></span>

<span data-ttu-id="4460c-140">Todo o processamento e armazenamento do conteúdo é feito no local central.</span><span class="sxs-lookup"><span data-stu-id="4460c-140">All processing and storage of content is done in the central location.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="4460c-141">Permissões do usuário</span><span class="sxs-lookup"><span data-stu-id="4460c-141">User permissions</span></span>

<span data-ttu-id="4460c-142">As permissões de usuário especificadas determinam quais pessoas em sua organização interagem com tópicos e o que podem fazer.</span><span class="sxs-lookup"><span data-stu-id="4460c-142">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

<span data-ttu-id="4460c-143">*Gerenciar tópicos*</span><span class="sxs-lookup"><span data-stu-id="4460c-143">*Manage topics*</span></span>

<span data-ttu-id="4460c-144">Os gerentes de conhecimento supervisionam a qualidade das informações, sua estrutura e outras práticas recomendadas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="4460c-144">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="4460c-145">Eles podem confirmar e rejeitar tópicos.</span><span class="sxs-lookup"><span data-stu-id="4460c-145">They can confirm and reject topics.</span></span>

<span data-ttu-id="4460c-146">Embora você possa especificar gerentes de tópicos individuais, recomendamos que você crie um grupo de segurança (ou use um existente) que contenha as pessoas que você deseja ser gerentes de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="4460c-146">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="4460c-147">Você pode especificar esse grupo de segurança durante o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="4460c-147">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="4460c-148">*Criar e editar tópicos*</span><span class="sxs-lookup"><span data-stu-id="4460c-148">*Create and edit topics*</span></span>

<span data-ttu-id="4460c-149">Os colaboradores de tópicos são os campeões e especialistas em assuntos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="4460c-149">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="4460c-150">Eles podem criar e editar tópicos.</span><span class="sxs-lookup"><span data-stu-id="4460c-150">They can create and edit topics.</span></span> 

<span data-ttu-id="4460c-151">Recomendamos que você permita que todos na sua organização criem e editem tópicos porque as experiências de tópico funcionam melhor quando todos os usuários podem compartilhar informações.</span><span class="sxs-lookup"><span data-stu-id="4460c-151">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="4460c-152">Se você quiser limitar a criação e edição de tópicos para pessoas ou grupos específicos, crie um grupo de segurança para eles e especifique-os durante o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="4460c-152">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="4460c-153">Você pode optar por não permitir que ninguém contribua com tópicos, no entanto, isso não é recomendado.</span><span class="sxs-lookup"><span data-stu-id="4460c-153">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="4460c-154">Os gerentes de conhecimento ainda poderão editar e criar tópicos se você escolher essa opção.</span><span class="sxs-lookup"><span data-stu-id="4460c-154">Knowledge managers will still be able to edit and create topics if you choose this option.</span></span>

<span data-ttu-id="4460c-155">*Visualizadores de tópicos*</span><span class="sxs-lookup"><span data-stu-id="4460c-155">*Topic viewers*</span></span>

<span data-ttu-id="4460c-156">Os visualizadores de tópicos podem ver informações sobre páginas de tópicos, nos resultados da pesquisa e quando os tópicos são realçados no conteúdo, como páginas do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4460c-156">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="4460c-157">Os usuários só podem ver tópicos descobertos quando têm acesso aos arquivos e páginas em que o tópico foi descoberto.</span><span class="sxs-lookup"><span data-stu-id="4460c-157">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="4460c-158">Ao configurar os visualizadores de tópicos, você pode escolher entre:</span><span class="sxs-lookup"><span data-stu-id="4460c-158">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="4460c-159">**Todos na minha organização**</span><span class="sxs-lookup"><span data-stu-id="4460c-159">**Everyone in my organization**</span></span>
- <span data-ttu-id="4460c-160">**Somente pessoas selecionadas ou grupos de segurança**</span><span class="sxs-lookup"><span data-stu-id="4460c-160">**Only selected people or security groups**</span></span>
- <span data-ttu-id="4460c-161">**Ninguém**</span><span class="sxs-lookup"><span data-stu-id="4460c-161">**No one**</span></span>

<span data-ttu-id="4460c-162">Recomendamos **Todos na minha organização**, mas se você estiver fazendo um piloto, talvez queira escolher apenas pessoas selecionadas ou grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="4460c-162">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="4460c-163">Você também pode escolher **Ninguém** se quiser configurar Tópicos, mas ainda não permitir que as pessoas vejam tópicos.</span><span class="sxs-lookup"><span data-stu-id="4460c-163">You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet.</span></span> <span data-ttu-id="4460c-164">(Os gerentes de conhecimento ainda terão acesso para permitir que eles exibirem os tópicos e ajudar com a decisão de disponibilizar tópicos amplamente.)</span><span class="sxs-lookup"><span data-stu-id="4460c-164">(Knowledge managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="4460c-165">Regras de conhecimento</span><span class="sxs-lookup"><span data-stu-id="4460c-165">Knowledge rules</span></span>

<span data-ttu-id="4460c-166">Como administrador, você pode excluir determinados tópicos de experiências de tópicos.</span><span class="sxs-lookup"><span data-stu-id="4460c-166">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="4460c-167">Isso é útil se você quiser impedir que dados confidenciais apareçam em tópicos.</span><span class="sxs-lookup"><span data-stu-id="4460c-167">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="4460c-168">Embora os gerentes de conhecimento possam excluir tópicos no centro de tópicos, os tópicos excluídos pelo administrador não são visíveis para gerentes de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="4460c-168">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="4460c-169">(Os gerentes de conhecimento também podem remover tópicos no centro de tópicos após a descoberta.)</span><span class="sxs-lookup"><span data-stu-id="4460c-169">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="4460c-170">Se você quiser excluir tópicos no nível de administrador, você deve adicioná-los a um arquivo .csv e carregar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="4460c-170">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="4460c-171">Você pode fazer isso durante a instalação ou posterior.</span><span class="sxs-lookup"><span data-stu-id="4460c-171">You can do this during setup or later.</span></span>

<span data-ttu-id="4460c-172">O arquivo .csv deve conter os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="4460c-172">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="4460c-173">**Nome**: digite o nome do tópico que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="4460c-173">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="4460c-174">Há duas maneiras de fazer isso:</span><span class="sxs-lookup"><span data-stu-id="4460c-174">There are two ways to do this:</span></span>
- <span data-ttu-id="4460c-175">**MatchType-Exact/Partial**: Digite se o nome inserido foi *um tipo de* combinação exato *ou* parcial.</span><span class="sxs-lookup"><span data-stu-id="4460c-175">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="4460c-176">Match exato: Você pode incluir o nome exato ou acrônimo (por exemplo, *Contoso* ou *ATL*).</span><span class="sxs-lookup"><span data-stu-id="4460c-176">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="4460c-177">Match parcial: você pode excluir todos os tópicos que tenham uma palavra específica nele.</span><span class="sxs-lookup"><span data-stu-id="4460c-177">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="4460c-178">Por exemplo, *o arco* excluirá  todos os tópicos com o arco de palavra nele, como círculo de *arco,* *soldagem* de arco de plasma ou arco *treinamento*. Observe que ele não excluirá tópicos nos quais o texto é incluído como parte de uma palavra, como *Arquitetura*.</span><span class="sxs-lookup"><span data-stu-id="4460c-178">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="4460c-179">**Significa (opcional)**: (Também conhecido como expansão *)* Se você quiser excluir um acrônimo, digite as palavras que o acrônimo representa.</span><span class="sxs-lookup"><span data-stu-id="4460c-179">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![Excluir tópicos no modelo CSV](../media/exclude-topics-csv.png) 

<span data-ttu-id="4460c-181">Você pode copiar o modelo csv abaixo:</span><span class="sxs-lookup"><span data-stu-id="4460c-181">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="4460c-182">Administração</span><span class="sxs-lookup"><span data-stu-id="4460c-182">Administration</span></span>

<span data-ttu-id="4460c-183">Quando você configura Tópicos, como parte do processo de instalação, um centro de tópicos é criado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4460c-183">When you set up Topics, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="4460c-184">Pense no nome do centro de tópicos e no que deseja que a URL seja.</span><span class="sxs-lookup"><span data-stu-id="4460c-184">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="4460c-185">Você pode definir o nome e a URL como parte do processo de instalação e alterar o nome (mas não URL) posteriormente no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4460c-185">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="4460c-186">Você só pode ter um centro de tópicos.</span><span class="sxs-lookup"><span data-stu-id="4460c-186">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="4460c-187">Lista de verificação de instalação</span><span class="sxs-lookup"><span data-stu-id="4460c-187">Setup checklist</span></span>

<span data-ttu-id="4460c-188">Ao configurar experiências de tópico, você precisará dos seguintes itens ao passar pelo assistente de instalação:</span><span class="sxs-lookup"><span data-stu-id="4460c-188">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="4460c-189">Lista de sites para incluir ou excluir se não incluir todos os sites para descoberta de tópicos</span><span class="sxs-lookup"><span data-stu-id="4460c-189">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="4460c-190">Grupo de segurança para visualizadores de tópicos se não permitir que todos os usuários exibirem tópicos</span><span class="sxs-lookup"><span data-stu-id="4460c-190">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="4460c-191">Grupo de segurança para colaboradores de tópicos se não permitir que todos os usuários criem e editem tópicos</span><span class="sxs-lookup"><span data-stu-id="4460c-191">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="4460c-192">Grupo de segurança para gerentes de conhecimento de tópicos se não permitir que todos os usuários gerenciem tópicos</span><span class="sxs-lookup"><span data-stu-id="4460c-192">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="4460c-193">Lista de tópicos confidenciais a excluir da descoberta de tópicos</span><span class="sxs-lookup"><span data-stu-id="4460c-193">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="4460c-194">Um nome para seu site central de tópicos</span><span class="sxs-lookup"><span data-stu-id="4460c-194">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="4460c-195">Confira também</span><span class="sxs-lookup"><span data-stu-id="4460c-195">See also</span></span>

[<span data-ttu-id="4460c-196">Configurar Experiências de tópico</span><span class="sxs-lookup"><span data-stu-id="4460c-196">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="4460c-197">Gerenciar a descoberta de tópicos no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4460c-197">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="4460c-198">Gerenciar visibilidade de tópicos no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4460c-198">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="4460c-199">Gerenciar permissões de tópico no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4460c-199">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="4460c-200">Alterar o nome do centro de tópicos no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4460c-200">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
