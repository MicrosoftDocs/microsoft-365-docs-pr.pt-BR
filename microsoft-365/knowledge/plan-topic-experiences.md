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
ms.openlocfilehash: de7534ce58a7888ac822826ef4ef1b4934ed8cb1
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583107"
---
# <a name="plan-for-microsoft-viva-topics"></a><span data-ttu-id="43d5a-103">Planejar tópicos do Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="43d5a-103">Plan for Microsoft Viva Topics</span></span>

<span data-ttu-id="43d5a-104">Você está no controle de como os tópicos são experimentado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="43d5a-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="43d5a-105">Suas decisões de planejamento para Tópicos garantem que os tópicos de alta qualidade sejam mostrados aos usuários e que eles tenham as permissões certas para consumir e contribuir com conhecimento.</span><span class="sxs-lookup"><span data-stu-id="43d5a-105">Your planning decisions for Topics ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="43d5a-106">Neste artigo, examinaremos essas decisões de planejamento:</span><span class="sxs-lookup"><span data-stu-id="43d5a-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="43d5a-107">Quais SharePoint sites que você deseja rastrear para tópicos</span><span class="sxs-lookup"><span data-stu-id="43d5a-107">Which SharePoint sites you want to crawl for topics</span></span>
- <span data-ttu-id="43d5a-108">Quais tópicos, se algum, você deseja excluir das experiências de tópico</span><span class="sxs-lookup"><span data-stu-id="43d5a-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="43d5a-109">Para quais usuários você deseja tornar os tópicos visíveis</span><span class="sxs-lookup"><span data-stu-id="43d5a-109">Which users you want to make topics visible to</span></span>
- <span data-ttu-id="43d5a-110">Quais usuários você deseja dar permissões para gerenciar tópicos no centro de tópicos</span><span class="sxs-lookup"><span data-stu-id="43d5a-110">Which users you want to give permissions to manage topics in the topic center</span></span>
- <span data-ttu-id="43d5a-111">Quais usuários você deseja dar permissões para criar ou editar tópicos no centro de tópicos</span><span class="sxs-lookup"><span data-stu-id="43d5a-111">Which users you want to give permissions to create or edit topics in the topic center</span></span>
- <span data-ttu-id="43d5a-112">Qual nome você deseja dar ao centro de tópicos</span><span class="sxs-lookup"><span data-stu-id="43d5a-112">What name you want to give your topic center</span></span>

<span data-ttu-id="43d5a-113">A segurança e a privacidade de seus dados são respeitadas, e as experiências de tópico não concedem aos usuários acesso adicional aos arquivos aos que eles não têm direitos.</span><span class="sxs-lookup"><span data-stu-id="43d5a-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="43d5a-114">Recomendamos que você também leia a segurança e a privacidade [dos Tópicos](topic-experiences-security-privacy.md) do Microsoft Viva como parte do seu processo de planejamento.</span><span class="sxs-lookup"><span data-stu-id="43d5a-114">We recommend you also read [Microsoft Viva Topics security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

<span data-ttu-id="43d5a-115">Para saber mais sobre a tecnologia de IA por trás dos Tópicos do Viva, leia a leitura de Alexandria em Tópicos do Microsoft Viva: de [big data a grande conhecimento.](https://www.microsoft.com/research/blog/alexandria-in-microsoft-viva-topics-from-big-data-to-big-knowledge)</span><span class="sxs-lookup"><span data-stu-id="43d5a-115">To learn more about the AI technology behind Viva Topics, read [Alexandria in Microsoft Viva Topics: from big data to big knowledge](https://www.microsoft.com/research/blog/alexandria-in-microsoft-viva-topics-from-big-data-to-big-knowledge).</span></span>

## <a name="requirements"></a><span data-ttu-id="43d5a-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="43d5a-116">Requirements</span></span>

<span data-ttu-id="43d5a-117">Você deve estar inscrito em [Tópicos](https://www.microsoft.com/microsoft-viva/topics) do Viva e ser um administrador global ou SharePoint para acessar o centro de administração Microsoft 365 e configurar Tópicos.</span><span class="sxs-lookup"><span data-stu-id="43d5a-117">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="43d5a-118">Todos os usuários que vão usar Tópicos exigem uma **licença experiências de** tópico.</span><span class="sxs-lookup"><span data-stu-id="43d5a-118">All users who are going to use Topics require a **Topic Experiences** license.</span></span> <span data-ttu-id="43d5a-119">A atribuição de licenças é abordada [em Configurar Tópicos do Microsoft Viva.](set-up-topic-experiences.md)</span><span class="sxs-lookup"><span data-stu-id="43d5a-119">Assigning licenses is covered in [Set up Microsoft Viva Topics](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="43d5a-120">Descoberta de tópicos</span><span class="sxs-lookup"><span data-stu-id="43d5a-120">Topic discovery</span></span>

<span data-ttu-id="43d5a-121">As configurações de descoberta de tópicos especificam quais sites do Microsoft Office SharePoint Online são usados como fontes de tópicos.</span><span class="sxs-lookup"><span data-stu-id="43d5a-121">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="43d5a-122">Você pode optar por incluir todos os sites do Microsoft Office SharePoint Online, uma lista específica de sites ou nenhum site.</span><span class="sxs-lookup"><span data-stu-id="43d5a-122">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="43d5a-123">Recomendamos que você escolha todos os sites para que as experiências de tópico possam descobrir um grande número de tópicos bons para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="43d5a-123">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="43d5a-124">Ao configurar tópicos, você pode escolher entre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="43d5a-124">When you set up Topics, you can choose from the following options:</span></span>

- <span data-ttu-id="43d5a-125">**Todos os**: todos os sites do Microsoft Office SharePoint Online em sua organização.</span><span class="sxs-lookup"><span data-stu-id="43d5a-125">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="43d5a-126">Isso inclui sites atuais e futuros.</span><span class="sxs-lookup"><span data-stu-id="43d5a-126">This includes current and future sites.</span></span>
- <span data-ttu-id="43d5a-127">**Tudo, exceto sites selecionados**: Todos os sites, exceto aqueles que você especificar.</span><span class="sxs-lookup"><span data-stu-id="43d5a-127">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="43d5a-128">Os sites criados no futuro serão incluídos como fontes para descoberta de tópicos.</span><span class="sxs-lookup"><span data-stu-id="43d5a-128">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="43d5a-129">**Somente sites selecionados:** somente os sites especificados.</span><span class="sxs-lookup"><span data-stu-id="43d5a-129">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="43d5a-130">Sites criados no futuro não serão incluídos como fontes para descoberta de tópicos.</span><span class="sxs-lookup"><span data-stu-id="43d5a-130">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="43d5a-131">**Nenhum site**: Não incluir sites do Microsoft Office SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="43d5a-131">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="43d5a-132">Se você escolher **Todos,** exceto sites selecionados ou Somente **sites** selecionados, poderá carregar um arquivo .csv com uma lista de sites.</span><span class="sxs-lookup"><span data-stu-id="43d5a-132">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="43d5a-133">Essas opções são úteis se você estiver fazendo um piloto e quiser incluir um número limitado de sites para iniciar.</span><span class="sxs-lookup"><span data-stu-id="43d5a-133">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="43d5a-134">Você pode copiar o modelo .csv abaixo:</span><span class="sxs-lookup"><span data-stu-id="43d5a-134">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="43d5a-135">Não recomendamos escolher **Nenhum site** porque impede que os tópicos são criados ou atualizados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="43d5a-135">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="43d5a-136">No entanto, você pode escolher essa opção se quiser configurar Tópicos e adicionar sites posteriormente.</span><span class="sxs-lookup"><span data-stu-id="43d5a-136">However, you can choose this option if you want to set up Topics and then add sites later.</span></span>

<span data-ttu-id="43d5a-137">Recomendamos que você crie um processo para usuários ou gerentes de conhecimento solicitarem que sites individuais sejam removidos da descoberta de tópicos, se necessário em sua organização.</span><span class="sxs-lookup"><span data-stu-id="43d5a-137">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

### <a name="multi-geo"></a><span data-ttu-id="43d5a-138">Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="43d5a-138">Multi-geo</span></span>

<span data-ttu-id="43d5a-139">Se sua organização tiver implantado Microsoft 365 [multi-geo](/microsoft-365/enterprise/microsoft-365-multi-geo), o centro de tópicos será provisionado no local central e somente os sites SharePoint no local central estarão disponíveis para uso como fontes para tópicos.</span><span class="sxs-lookup"><span data-stu-id="43d5a-139">If your organization has deployed [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo), the topic center is provisioned in the central location and only SharePoint sites in the central location are available to use as sources for topics.</span></span> <span data-ttu-id="43d5a-140">(Se você selecionar **Todos os sites,** os Tópicos do Viva usarão todos os sites no local central.)</span><span class="sxs-lookup"><span data-stu-id="43d5a-140">(If you select **All sites**, Viva Topics will use all site in the central location.)</span></span>

<span data-ttu-id="43d5a-141">Todo o processamento e armazenamento do conteúdo é feito no local central.</span><span class="sxs-lookup"><span data-stu-id="43d5a-141">All processing and storage of content is done in the central location.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="43d5a-142">Permissões do usuário</span><span class="sxs-lookup"><span data-stu-id="43d5a-142">User permissions</span></span>

<span data-ttu-id="43d5a-143">As permissões de usuário especificadas determinam quais pessoas em sua organização interagem com tópicos e o que podem fazer.</span><span class="sxs-lookup"><span data-stu-id="43d5a-143">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

> [!Note] 
> <span data-ttu-id="43d5a-144">Neste momento, os Tópicos do Viva não suportam o fornecimento de licenças ou permissões de usuário para usuários convidados (externos).</span><span class="sxs-lookup"><span data-stu-id="43d5a-144">At this time, Viva Topics doesn't support providing licenses or user permissions for Guest (External) users.</span></span> 

<span data-ttu-id="43d5a-145">*Gerenciar tópicos*</span><span class="sxs-lookup"><span data-stu-id="43d5a-145">*Manage topics*</span></span>

<span data-ttu-id="43d5a-146">Os gerentes de conhecimento supervisionam a qualidade das informações, sua estrutura e outras práticas recomendadas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="43d5a-146">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="43d5a-147">Eles podem confirmar e rejeitar tópicos.</span><span class="sxs-lookup"><span data-stu-id="43d5a-147">They can confirm and reject topics.</span></span>

<span data-ttu-id="43d5a-148">Embora você possa especificar gerentes de tópicos individuais, recomendamos que você crie um grupo de segurança (ou use um existente) que contenha as pessoas que você deseja ser gerentes de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="43d5a-148">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="43d5a-149">Você pode especificar esse grupo de segurança durante o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="43d5a-149">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="43d5a-150">*Criar e editar tópicos*</span><span class="sxs-lookup"><span data-stu-id="43d5a-150">*Create and edit topics*</span></span>

<span data-ttu-id="43d5a-151">Os colaboradores de tópicos são os campeões e especialistas em assuntos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="43d5a-151">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="43d5a-152">Eles podem criar e editar tópicos.</span><span class="sxs-lookup"><span data-stu-id="43d5a-152">They can create and edit topics.</span></span> 

<span data-ttu-id="43d5a-153">Recomendamos que você permita que todos na sua organização criem e editem tópicos porque as experiências de tópico funcionam melhor quando todos os usuários podem compartilhar informações.</span><span class="sxs-lookup"><span data-stu-id="43d5a-153">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="43d5a-154">Se você quiser limitar a criação e edição de tópicos para pessoas ou grupos específicos, crie um grupo de segurança para eles e especifique-os durante o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="43d5a-154">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="43d5a-155">Você pode optar por não permitir que ninguém contribua com tópicos, no entanto, isso não é recomendado.</span><span class="sxs-lookup"><span data-stu-id="43d5a-155">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="43d5a-156">Os gerentes de conhecimento ainda poderão editar e criar tópicos se você escolher essa opção.</span><span class="sxs-lookup"><span data-stu-id="43d5a-156">Knowledge managers will still be able to edit and create topics if you choose this option.</span></span>

<span data-ttu-id="43d5a-157">*Visualizadores de tópicos*</span><span class="sxs-lookup"><span data-stu-id="43d5a-157">*Topic viewers*</span></span>

<span data-ttu-id="43d5a-158">Os visualizadores de tópicos podem ver informações sobre páginas de tópicos, nos resultados da pesquisa e quando os tópicos são realçados no conteúdo como SharePoint páginas.</span><span class="sxs-lookup"><span data-stu-id="43d5a-158">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="43d5a-159">Os usuários só podem ver tópicos descobertos quando têm acesso aos arquivos e páginas em que o tópico foi descoberto.</span><span class="sxs-lookup"><span data-stu-id="43d5a-159">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="43d5a-160">Ao configurar os visualizadores de tópicos, você pode escolher entre:</span><span class="sxs-lookup"><span data-stu-id="43d5a-160">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="43d5a-161">**Todos na minha organização**</span><span class="sxs-lookup"><span data-stu-id="43d5a-161">**Everyone in my organization**</span></span>
- <span data-ttu-id="43d5a-162">**Somente pessoas selecionadas ou grupos de segurança**</span><span class="sxs-lookup"><span data-stu-id="43d5a-162">**Only selected people or security groups**</span></span>
- <span data-ttu-id="43d5a-163">**Ninguém**</span><span class="sxs-lookup"><span data-stu-id="43d5a-163">**No one**</span></span>

<span data-ttu-id="43d5a-164">Recomendamos **Todos na minha organização**, mas se você estiver fazendo um piloto, talvez queira escolher apenas pessoas selecionadas ou grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="43d5a-164">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="43d5a-165">Você também pode escolher **Ninguém** se quiser configurar Tópicos, mas ainda não permitir que as pessoas vejam tópicos.</span><span class="sxs-lookup"><span data-stu-id="43d5a-165">You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet.</span></span> <span data-ttu-id="43d5a-166">(Os gerentes de conhecimento ainda terão acesso para permitir que eles exibirem os tópicos e ajudar com a decisão de disponibilizar tópicos amplamente.)</span><span class="sxs-lookup"><span data-stu-id="43d5a-166">(Knowledge managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="43d5a-167">Regras de conhecimento</span><span class="sxs-lookup"><span data-stu-id="43d5a-167">Knowledge rules</span></span>

<span data-ttu-id="43d5a-168">Como administrador, você pode excluir determinados tópicos de experiências de tópicos.</span><span class="sxs-lookup"><span data-stu-id="43d5a-168">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="43d5a-169">Isso é útil se você quiser impedir que dados confidenciais apareçam em tópicos.</span><span class="sxs-lookup"><span data-stu-id="43d5a-169">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="43d5a-170">Embora os gerentes de conhecimento possam excluir tópicos no centro de tópicos, os tópicos excluídos pelo administrador não são visíveis para gerentes de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="43d5a-170">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="43d5a-171">(Os gerentes de conhecimento também podem remover tópicos no centro de tópicos após a descoberta.)</span><span class="sxs-lookup"><span data-stu-id="43d5a-171">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="43d5a-172">Se você quiser excluir tópicos no nível de administrador, você deve adicioná-los a um arquivo .csv e carregar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="43d5a-172">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="43d5a-173">Você pode fazer isso durante a instalação ou posterior.</span><span class="sxs-lookup"><span data-stu-id="43d5a-173">You can do this during setup or later.</span></span>

<span data-ttu-id="43d5a-174">O .csv deve conter os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="43d5a-174">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="43d5a-175">**Nome**: digite o nome do tópico que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="43d5a-175">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="43d5a-176">Há duas maneiras de fazer isso:</span><span class="sxs-lookup"><span data-stu-id="43d5a-176">There are two ways to do this:</span></span>
- <span data-ttu-id="43d5a-177">**MatchType-Exact/Partial**: Digite se o nome inserido foi *um tipo de* combinação exato *ou* parcial.</span><span class="sxs-lookup"><span data-stu-id="43d5a-177">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="43d5a-178">Match exato: Você pode incluir o nome exato ou acrônimo (por exemplo, *Contoso* ou *ATL*).</span><span class="sxs-lookup"><span data-stu-id="43d5a-178">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="43d5a-179">Match parcial: você pode excluir todos os tópicos que tenham uma palavra específica nele.</span><span class="sxs-lookup"><span data-stu-id="43d5a-179">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="43d5a-180">Por exemplo, *o arco* excluirá  todos os tópicos com o arco de palavra nele, como círculo de *arco,* *soldagem* de arco de plasma ou arco *treinamento*. Observe que ele não excluirá tópicos nos quais o texto é incluído como parte de uma palavra, como *Arquitetura*.</span><span class="sxs-lookup"><span data-stu-id="43d5a-180">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="43d5a-181">**Significa (opcional)**: (Também conhecido como expansão *)* Se você quiser excluir um acrônimo, digite as palavras que o acrônimo representa.</span><span class="sxs-lookup"><span data-stu-id="43d5a-181">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![Excluir tópicos no modelo CSV](../media/exclude-topics-csv.png) 

<span data-ttu-id="43d5a-183">Você pode copiar o modelo csv abaixo:</span><span class="sxs-lookup"><span data-stu-id="43d5a-183">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="43d5a-184">Administração</span><span class="sxs-lookup"><span data-stu-id="43d5a-184">Administration</span></span>

<span data-ttu-id="43d5a-185">Quando você configura Tópicos, como parte do processo de instalação, um centro de tópicos é criado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="43d5a-185">When you set up Topics, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="43d5a-186">Pense no nome do centro de tópicos e no que deseja que a URL seja.</span><span class="sxs-lookup"><span data-stu-id="43d5a-186">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="43d5a-187">Você pode definir o nome e a URL como parte do processo de instalação e alterar o nome (mas não a URL) posteriormente no centro de administração Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="43d5a-187">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="43d5a-188">Você só pode ter um centro de tópicos.</span><span class="sxs-lookup"><span data-stu-id="43d5a-188">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="43d5a-189">Lista de verificação de instalação</span><span class="sxs-lookup"><span data-stu-id="43d5a-189">Setup checklist</span></span>

<span data-ttu-id="43d5a-190">Ao configurar experiências de tópico, você precisará dos seguintes itens ao passar pelo assistente de instalação:</span><span class="sxs-lookup"><span data-stu-id="43d5a-190">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="43d5a-191">Lista de sites a incluir ou excluir, se não incluir todos os sites para descoberta de tópicos</span><span class="sxs-lookup"><span data-stu-id="43d5a-191">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="43d5a-192">Grupo de segurança para visualizadores de tópicos, se não permitir que todos os usuários visualizem tópicos</span><span class="sxs-lookup"><span data-stu-id="43d5a-192">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="43d5a-193">Grupo de segurança para colaboradores de tópicos, se não permitir que todos os usuários criem e editem tópicos</span><span class="sxs-lookup"><span data-stu-id="43d5a-193">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="43d5a-194">Grupo de segurança para gerentes de conhecimento de tópicos, se não permitir que todos os usuários gerenciem tópicos</span><span class="sxs-lookup"><span data-stu-id="43d5a-194">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="43d5a-195">Lista de tópicos confidenciais a excluir da descoberta de tópicos</span><span class="sxs-lookup"><span data-stu-id="43d5a-195">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="43d5a-196">Um nome para seu site central de tópicos</span><span class="sxs-lookup"><span data-stu-id="43d5a-196">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="43d5a-197">Confira também</span><span class="sxs-lookup"><span data-stu-id="43d5a-197">See also</span></span>

[<span data-ttu-id="43d5a-198">Configurar Experiências de tópico</span><span class="sxs-lookup"><span data-stu-id="43d5a-198">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="43d5a-199">Gerenciar a descoberta de tópicos no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="43d5a-199">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="43d5a-200">Gerenciar visibilidade de tópicos no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="43d5a-200">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="43d5a-201">Gerenciar permissões de tópico em Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="43d5a-201">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="43d5a-202">Alterar o nome do centro de tópicos no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="43d5a-202">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
