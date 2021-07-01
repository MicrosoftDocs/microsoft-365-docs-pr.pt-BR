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
ms.openlocfilehash: a407fd6e6919c3b85235e317e5ed3ff103607700
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229534"
---
# <a name="plan-for-microsoft-viva-topics"></a><span data-ttu-id="57296-103">Planejar tópicos do Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="57296-103">Plan for Microsoft Viva Topics</span></span>

<span data-ttu-id="57296-104">Você está no controle de como os tópicos são experimentado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="57296-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="57296-105">Suas decisões de planejamento para Tópicos garantem que os tópicos de alta qualidade sejam mostrados aos usuários e que eles tenham as permissões certas para consumir e contribuir com conhecimento.</span><span class="sxs-lookup"><span data-stu-id="57296-105">Your planning decisions for Topics ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="57296-106">Neste artigo, examinaremos essas decisões de planejamento:</span><span class="sxs-lookup"><span data-stu-id="57296-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="57296-107">Quais SharePoint sites que você deseja rastrear para tópicos</span><span class="sxs-lookup"><span data-stu-id="57296-107">Which SharePoint sites you want to crawl for topics</span></span>
- <span data-ttu-id="57296-108">Quais tópicos, se algum, você deseja excluir das experiências de tópico</span><span class="sxs-lookup"><span data-stu-id="57296-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="57296-109">Para quais usuários você deseja tornar os tópicos visíveis</span><span class="sxs-lookup"><span data-stu-id="57296-109">Which users you want to make topics visible to</span></span>
- <span data-ttu-id="57296-110">Quais usuários você deseja dar permissões para gerenciar tópicos no centro de tópicos</span><span class="sxs-lookup"><span data-stu-id="57296-110">Which users you want to give permissions to manage topics in the topic center</span></span>
- <span data-ttu-id="57296-111">Quais usuários você deseja dar permissões para criar ou editar tópicos no centro de tópicos</span><span class="sxs-lookup"><span data-stu-id="57296-111">Which users you want to give permissions to create or edit topics in the topic center</span></span>
- <span data-ttu-id="57296-112">Qual nome você deseja dar ao centro de tópicos</span><span class="sxs-lookup"><span data-stu-id="57296-112">What name you want to give your topic center</span></span>

<span data-ttu-id="57296-113">A segurança e a privacidade de seus dados são respeitadas, e as experiências de tópico não concedem aos usuários acesso adicional aos arquivos aos que eles não têm direitos.</span><span class="sxs-lookup"><span data-stu-id="57296-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="57296-114">Recomendamos que você também leia a segurança e a privacidade [dos Tópicos](topic-experiences-security-privacy.md) do Microsoft Viva como parte do seu processo de planejamento.</span><span class="sxs-lookup"><span data-stu-id="57296-114">We recommend you also read [Microsoft Viva Topics security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

<span data-ttu-id="57296-115">Para saber mais sobre a tecnologia de IA por trás dos Tópicos do Viva, leia a leitura de Alexandria em Tópicos do Microsoft Viva: de [big data a grande conhecimento.](https://www.microsoft.com/research/blog/alexandria-in-microsoft-viva-topics-from-big-data-to-big-knowledge)</span><span class="sxs-lookup"><span data-stu-id="57296-115">To learn more about the AI technology behind Viva Topics, read [Alexandria in Microsoft Viva Topics: from big data to big knowledge](https://www.microsoft.com/research/blog/alexandria-in-microsoft-viva-topics-from-big-data-to-big-knowledge).</span></span>

## <a name="requirements"></a><span data-ttu-id="57296-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="57296-116">Requirements</span></span>

<span data-ttu-id="57296-117">Você deve estar inscrito em [Tópicos do Viva](https://www.microsoft.com/microsoft-viva/topics) e ser um administrador global ou SharePoint para acessar o Centro de administração do Microsoft 365 e configurar Tópicos.</span><span class="sxs-lookup"><span data-stu-id="57296-117">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="57296-118">Todos os usuários que vão usar Tópicos exigem uma **licença experiências de** tópico.</span><span class="sxs-lookup"><span data-stu-id="57296-118">All users who are going to use Topics require a **Topic Experiences** license.</span></span> <span data-ttu-id="57296-119">A atribuição de licenças é abordada [em Configurar Tópicos do Microsoft Viva.](set-up-topic-experiences.md)</span><span class="sxs-lookup"><span data-stu-id="57296-119">Assigning licenses is covered in [Set up Microsoft Viva Topics](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="57296-120">Descoberta de tópicos</span><span class="sxs-lookup"><span data-stu-id="57296-120">Topic discovery</span></span>

<span data-ttu-id="57296-121">As configurações de descoberta de tópicos especificam quais sites do Microsoft Office SharePoint Online são usados como fontes de tópicos.</span><span class="sxs-lookup"><span data-stu-id="57296-121">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="57296-122">Isso inclui sites clássicos e modernos, bem como sites associados a Microsoft Teams e Microsoft 365 Grupos.</span><span class="sxs-lookup"><span data-stu-id="57296-122">This includes both classic and modern sites, as well as sites associated with Microsoft Teams and Microsoft 365 Groups.</span></span> <span data-ttu-id="57296-123">OneDrive sites não estão incluídos.</span><span class="sxs-lookup"><span data-stu-id="57296-123">OneDrive sites are not included.</span></span>

<span data-ttu-id="57296-124">Você pode optar por incluir todos os sites do Microsoft Office SharePoint Online, uma lista específica de sites ou nenhum site.</span><span class="sxs-lookup"><span data-stu-id="57296-124">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="57296-125">Recomendamos que você escolha todos os sites para que as experiências de tópico possam descobrir um grande número de tópicos bons para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="57296-125">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="57296-126">Ao configurar tópicos, você pode escolher entre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="57296-126">When you set up Topics, you can choose from the following options:</span></span>

- <span data-ttu-id="57296-127">**Todos os**: todos os sites do Microsoft Office SharePoint Online em sua organização.</span><span class="sxs-lookup"><span data-stu-id="57296-127">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="57296-128">Isso inclui sites atuais e futuros.</span><span class="sxs-lookup"><span data-stu-id="57296-128">This includes current and future sites.</span></span>
- <span data-ttu-id="57296-129">**Tudo, exceto sites selecionados**: Todos os sites, exceto aqueles que você especificar.</span><span class="sxs-lookup"><span data-stu-id="57296-129">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="57296-130">Os sites criados no futuro serão incluídos como fontes para descoberta de tópicos.</span><span class="sxs-lookup"><span data-stu-id="57296-130">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="57296-131">**Somente sites selecionados:** somente os sites especificados.</span><span class="sxs-lookup"><span data-stu-id="57296-131">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="57296-132">Sites criados no futuro não serão incluídos como fontes para descoberta de tópicos.</span><span class="sxs-lookup"><span data-stu-id="57296-132">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="57296-133">**Nenhum site**: Não incluir sites do Microsoft Office SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="57296-133">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="57296-134">Se você escolher **Todos,** exceto sites selecionados ou Somente **sites** selecionados, poderá carregar um arquivo .csv com uma lista de sites.</span><span class="sxs-lookup"><span data-stu-id="57296-134">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="57296-135">Essas opções são úteis se você estiver fazendo um piloto e quiser incluir um número limitado de sites para iniciar.</span><span class="sxs-lookup"><span data-stu-id="57296-135">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="57296-136">Você pode copiar o modelo .csv abaixo:</span><span class="sxs-lookup"><span data-stu-id="57296-136">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="57296-137">Não recomendamos escolher **Nenhum site** porque impede que os tópicos são criados ou atualizados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="57296-137">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="57296-138">No entanto, você pode escolher essa opção se quiser configurar Tópicos e adicionar sites posteriormente.</span><span class="sxs-lookup"><span data-stu-id="57296-138">However, you can choose this option if you want to set up Topics and then add sites later.</span></span>

<span data-ttu-id="57296-139">Recomendamos que você crie um processo para usuários ou gerentes de conhecimento solicitarem que sites individuais sejam removidos da descoberta de tópicos, se necessário em sua organização.</span><span class="sxs-lookup"><span data-stu-id="57296-139">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

### <a name="multi-geo"></a><span data-ttu-id="57296-140">Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="57296-140">Multi-geo</span></span>

<span data-ttu-id="57296-141">Se sua organização tiver implantado Microsoft 365 [multi-geo](/microsoft-365/enterprise/microsoft-365-multi-geo), o centro de tópicos será provisionado no local central e somente os sites SharePoint no local central estarão disponíveis para uso como fontes para tópicos.</span><span class="sxs-lookup"><span data-stu-id="57296-141">If your organization has deployed [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo), the topic center is provisioned in the central location and only SharePoint sites in the central location are available to use as sources for topics.</span></span> <span data-ttu-id="57296-142">(Se você selecionar **Todos os sites,** os Tópicos do Viva usarão todos os sites no local central.)</span><span class="sxs-lookup"><span data-stu-id="57296-142">(If you select **All sites**, Viva Topics will use all site in the central location.)</span></span>

<span data-ttu-id="57296-143">Todo o processamento e armazenamento do conteúdo é feito no local central.</span><span class="sxs-lookup"><span data-stu-id="57296-143">All processing and storage of content is done in the central location.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="57296-144">Permissões do usuário</span><span class="sxs-lookup"><span data-stu-id="57296-144">User permissions</span></span>

<span data-ttu-id="57296-145">As permissões de usuário especificadas determinam quais pessoas em sua organização interagem com tópicos e o que podem fazer.</span><span class="sxs-lookup"><span data-stu-id="57296-145">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

> [!Note] 
> <span data-ttu-id="57296-146">Neste momento, os Tópicos do Viva não suportam o fornecimento de licenças ou permissões de usuário para usuários convidados (externos).</span><span class="sxs-lookup"><span data-stu-id="57296-146">At this time, Viva Topics doesn't support providing licenses or user permissions for Guest (External) users.</span></span> 

<span data-ttu-id="57296-147">*Gerenciar tópicos*</span><span class="sxs-lookup"><span data-stu-id="57296-147">*Manage topics*</span></span>

<span data-ttu-id="57296-148">Os gerentes de conhecimento supervisionam a qualidade das informações, sua estrutura e outras práticas recomendadas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="57296-148">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="57296-149">Eles podem confirmar e rejeitar tópicos.</span><span class="sxs-lookup"><span data-stu-id="57296-149">They can confirm and reject topics.</span></span>

<span data-ttu-id="57296-150">Embora você possa especificar gerentes de tópicos individuais, recomendamos que você crie um grupo de segurança (ou use um existente) que contenha as pessoas que você deseja ser gerentes de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="57296-150">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="57296-151">Você pode especificar esse grupo de segurança durante o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="57296-151">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="57296-152">*Criar e editar tópicos*</span><span class="sxs-lookup"><span data-stu-id="57296-152">*Create and edit topics*</span></span>

<span data-ttu-id="57296-153">Os colaboradores de tópicos são os campeões e especialistas em assuntos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="57296-153">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="57296-154">Eles podem criar e editar tópicos.</span><span class="sxs-lookup"><span data-stu-id="57296-154">They can create and edit topics.</span></span> 

<span data-ttu-id="57296-155">Recomendamos que você permita que todos na sua organização criem e editem tópicos porque as experiências de tópico funcionam melhor quando todos os usuários podem compartilhar informações.</span><span class="sxs-lookup"><span data-stu-id="57296-155">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="57296-156">Se você quiser limitar a criação e edição de tópicos para pessoas ou grupos específicos, crie um grupo de segurança para eles e especifique-os durante o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="57296-156">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="57296-157">Você pode optar por não permitir que ninguém contribua com tópicos, no entanto, isso não é recomendado.</span><span class="sxs-lookup"><span data-stu-id="57296-157">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="57296-158">Os gerentes de conhecimento ainda poderão editar e criar tópicos se você escolher essa opção.</span><span class="sxs-lookup"><span data-stu-id="57296-158">Knowledge managers will still be able to edit and create topics if you choose this option.</span></span>

<span data-ttu-id="57296-159">*Visualizadores de tópicos*</span><span class="sxs-lookup"><span data-stu-id="57296-159">*Topic viewers*</span></span>

<span data-ttu-id="57296-160">Os visualizadores de tópicos podem ver informações sobre páginas de tópicos, nos resultados da pesquisa e quando os tópicos são realçados no conteúdo como SharePoint páginas.</span><span class="sxs-lookup"><span data-stu-id="57296-160">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="57296-161">Os usuários só podem ver tópicos descobertos quando têm acesso aos arquivos e páginas em que o tópico foi descoberto.</span><span class="sxs-lookup"><span data-stu-id="57296-161">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="57296-162">Ao configurar os visualizadores de tópicos, você pode escolher entre:</span><span class="sxs-lookup"><span data-stu-id="57296-162">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="57296-163">**Todos na minha organização**</span><span class="sxs-lookup"><span data-stu-id="57296-163">**Everyone in my organization**</span></span>
- <span data-ttu-id="57296-164">**Somente pessoas selecionadas ou grupos de segurança**</span><span class="sxs-lookup"><span data-stu-id="57296-164">**Only selected people or security groups**</span></span>
- <span data-ttu-id="57296-165">**Ninguém**</span><span class="sxs-lookup"><span data-stu-id="57296-165">**No one**</span></span>

<span data-ttu-id="57296-166">Recomendamos **Todos na minha organização**, mas se você estiver fazendo um piloto, talvez queira escolher apenas pessoas selecionadas ou grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="57296-166">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="57296-167">Você também pode escolher **Ninguém** se quiser configurar Tópicos, mas ainda não permitir que as pessoas vejam tópicos.</span><span class="sxs-lookup"><span data-stu-id="57296-167">You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet.</span></span> <span data-ttu-id="57296-168">(Os gerentes de conhecimento ainda terão acesso para permitir que eles exibirem os tópicos e ajudar com a decisão de disponibilizar tópicos amplamente.)</span><span class="sxs-lookup"><span data-stu-id="57296-168">(Knowledge managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="57296-169">Regras de conhecimento</span><span class="sxs-lookup"><span data-stu-id="57296-169">Knowledge rules</span></span>

<span data-ttu-id="57296-170">Como administrador, você pode excluir determinados tópicos de experiências de tópicos.</span><span class="sxs-lookup"><span data-stu-id="57296-170">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="57296-171">Isso é útil se você quiser impedir que dados confidenciais apareçam em tópicos.</span><span class="sxs-lookup"><span data-stu-id="57296-171">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="57296-172">Embora os gerentes de conhecimento possam excluir tópicos no centro de tópicos, os tópicos excluídos pelo administrador não são visíveis para gerentes de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="57296-172">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="57296-173">(Os gerentes de conhecimento também podem remover tópicos no centro de tópicos após a descoberta.)</span><span class="sxs-lookup"><span data-stu-id="57296-173">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="57296-174">Se você quiser excluir tópicos no nível de administrador, você deve adicioná-los a um arquivo .csv e carregar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="57296-174">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="57296-175">Você pode fazer isso durante a instalação ou posterior.</span><span class="sxs-lookup"><span data-stu-id="57296-175">You can do this during setup or later.</span></span>

<span data-ttu-id="57296-176">O .csv deve conter os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="57296-176">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="57296-177">**Nome**: digite o nome do tópico que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="57296-177">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="57296-178">Há duas maneiras de fazer isso:</span><span class="sxs-lookup"><span data-stu-id="57296-178">There are two ways to do this:</span></span>
- <span data-ttu-id="57296-179">**MatchType-Exact/Partial**: Digite se o nome inserido foi *um tipo de* combinação exato *ou* parcial.</span><span class="sxs-lookup"><span data-stu-id="57296-179">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="57296-180">Match exato: Você pode incluir o nome exato ou acrônimo (por exemplo, *Contoso* ou *ATL*).</span><span class="sxs-lookup"><span data-stu-id="57296-180">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="57296-181">Match parcial: você pode excluir todos os tópicos que tenham uma palavra específica nele.</span><span class="sxs-lookup"><span data-stu-id="57296-181">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="57296-182">Por exemplo, *o arco* excluirá  todos os tópicos com o arco de palavra nele, como círculo de *arco,* *soldagem* de arco de plasma ou arco *treinamento*. Observe que ele não excluirá tópicos nos quais o texto é incluído como parte de uma palavra, como *Arquitetura*.</span><span class="sxs-lookup"><span data-stu-id="57296-182">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="57296-183">**Significa (opcional)**: (Também conhecido como expansão *)* Se você quiser excluir um acrônimo, digite as palavras que o acrônimo representa.</span><span class="sxs-lookup"><span data-stu-id="57296-183">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![Excluir tópicos no modelo CSV](../media/exclude-topics-csv.png) 

<span data-ttu-id="57296-185">Você pode copiar o modelo csv abaixo:</span><span class="sxs-lookup"><span data-stu-id="57296-185">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="57296-186">Administração</span><span class="sxs-lookup"><span data-stu-id="57296-186">Administration</span></span>

<span data-ttu-id="57296-187">Quando você configura Tópicos, como parte do processo de instalação, um centro de tópicos é criado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="57296-187">When you set up Topics, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="57296-188">Pense no nome do centro de tópicos e no que deseja que a URL seja.</span><span class="sxs-lookup"><span data-stu-id="57296-188">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="57296-189">Você pode definir o nome e a URL como parte do processo de instalação e pode alterar o nome (mas não URL) posteriormente no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="57296-189">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="57296-190">Você só pode ter um centro de tópicos.</span><span class="sxs-lookup"><span data-stu-id="57296-190">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="57296-191">Lista de verificação de instalação</span><span class="sxs-lookup"><span data-stu-id="57296-191">Setup checklist</span></span>

<span data-ttu-id="57296-192">Ao configurar experiências de tópico, você precisará dos seguintes itens ao passar pelo assistente de instalação:</span><span class="sxs-lookup"><span data-stu-id="57296-192">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="57296-193">Lista de sites a incluir ou excluir, se não incluir todos os sites para descoberta de tópicos</span><span class="sxs-lookup"><span data-stu-id="57296-193">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="57296-194">Grupo de segurança para visualizadores de tópicos, se não permitir que todos os usuários visualizem tópicos</span><span class="sxs-lookup"><span data-stu-id="57296-194">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="57296-195">Grupo de segurança para colaboradores de tópicos, se não permitir que todos os usuários criem e editem tópicos</span><span class="sxs-lookup"><span data-stu-id="57296-195">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="57296-196">Grupo de segurança para gerentes de conhecimento de tópicos, se não permitir que todos os usuários gerenciem tópicos</span><span class="sxs-lookup"><span data-stu-id="57296-196">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="57296-197">Lista de tópicos confidenciais a excluir da descoberta de tópicos</span><span class="sxs-lookup"><span data-stu-id="57296-197">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="57296-198">Um nome para seu site central de tópicos</span><span class="sxs-lookup"><span data-stu-id="57296-198">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="57296-199">Confira também</span><span class="sxs-lookup"><span data-stu-id="57296-199">See also</span></span>

[<span data-ttu-id="57296-200">Configurar Experiências de tópico</span><span class="sxs-lookup"><span data-stu-id="57296-200">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="57296-201">Gerenciar a descoberta de tópicos no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="57296-201">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="57296-202">Gerenciar visibilidade de tópicos no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="57296-202">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="57296-203">Gerenciar permissões de tópico em Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="57296-203">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="57296-204">Alterar o nome do centro de tópicos no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="57296-204">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
