---
title: Colaborar com convidados em um site
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Saiba mais sobre as etapas de configuração do Microsoft 365 necessárias para configurar um site do SharePoint para colaboração com convidados.
ms.openlocfilehash: 6862fe715fe2f19b968b773bc6df6c70c207a44f
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663519"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="249ff-103">Colaborar com convidados em um site</span><span class="sxs-lookup"><span data-stu-id="249ff-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="249ff-104">Se você precisar colaborar com convidados em documentos, dados e listas, poderá usar um site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="249ff-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="249ff-105">Os sites modernos do SharePoint estão conectados aos Grupos do Microsoft 365 e podem gerenciar a associação ao site e fornecer ferramentas de colaboração adicionais, como uma caixa de correio compartilhada e um calendário.</span><span class="sxs-lookup"><span data-stu-id="249ff-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and a calendar.</span></span>

<span data-ttu-id="249ff-106">Neste artigo, vamos ver as etapas de configuração do Microsoft 365 necessárias para configurar um site do SharePoint para colaboração com convidados.</span><span class="sxs-lookup"><span data-stu-id="249ff-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="249ff-107">Demonstração de vídeo</span><span class="sxs-lookup"><span data-stu-id="249ff-107">Video demonstration</span></span>

<span data-ttu-id="249ff-108">Este vídeo mostra as etapas de configuração descritas neste documento.</span><span class="sxs-lookup"><span data-stu-id="249ff-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="249ff-109">Configurações de colaboração externa do Azure</span><span class="sxs-lookup"><span data-stu-id="249ff-109">Azure external collaboration settings</span></span>

<span data-ttu-id="249ff-110">O compartilhamento no Microsoft 365 é regido em seu nível mais alto pelas configurações de colaboração [externa B2B no Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)</span><span class="sxs-lookup"><span data-stu-id="249ff-110">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="249ff-111">Se o compartilhamento de convidados estiver desabilitado ou restrito no Azure AD, essa configuração substituirá as configurações de compartilhamento que você definir no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="249ff-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="249ff-112">Verifique as configurações de colaboração externa B2B para garantir que o compartilhamento com convidados não seja bloqueado.</span><span class="sxs-lookup"><span data-stu-id="249ff-112">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Captura de tela da página Configurações de colaboração externa do Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="249ff-114">Para definir configurações de colaboração externa</span><span class="sxs-lookup"><span data-stu-id="249ff-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="249ff-115">Entre no Azure Active Directory em [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="249ff-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="249ff-116">No painel de navegação esquerdo, clique no **Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="249ff-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="249ff-117">Clique **em Identidades externas.**</span><span class="sxs-lookup"><span data-stu-id="249ff-117">Click **External identities**.</span></span>
4. <span data-ttu-id="249ff-118">Na tela **De início,** no painel de navegação esquerdo, clique em **Configurações de colaboração externa.**</span><span class="sxs-lookup"><span data-stu-id="249ff-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="249ff-119">Certifique-se de que os administradores e  usuários na função de convidado convidado possam convidar e que os membros possam convidar estão **definidos** como **Sim.**</span><span class="sxs-lookup"><span data-stu-id="249ff-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="249ff-120">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="249ff-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="249ff-121">Observe as configurações na seção **Restrições de** colaboração.</span><span class="sxs-lookup"><span data-stu-id="249ff-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="249ff-122">Certifique-se de que os domínios dos convidados com os que você deseja colaborar não sejam bloqueados.</span><span class="sxs-lookup"><span data-stu-id="249ff-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="249ff-123">Se você trabalha com convidados de várias organizações, talvez queira restringir sua capacidade de acessar dados de diretório.</span><span class="sxs-lookup"><span data-stu-id="249ff-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="249ff-124">Isso impedirá que eles veja quem mais é um convidado no diretório.</span><span class="sxs-lookup"><span data-stu-id="249ff-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="249ff-125">Para fazer isso, em restrições de acesso de usuário **convidado,** selecione **Usuários** convidados têm acesso limitado a propriedades e associação de configurações de objetos de diretório ou acesso de usuário convidado é restrito a propriedades e associações de seus próprios objetos de **diretório.**</span><span class="sxs-lookup"><span data-stu-id="249ff-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="249ff-126">Configurações de convidado dos Grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="249ff-126">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="249ff-127">Os sites modernos do SharePoint usam grupos do Microsoft 365 para controlar o acesso ao site.</span><span class="sxs-lookup"><span data-stu-id="249ff-127">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="249ff-128">As configurações de convidado dos Grupos do Microsoft 365 devem ser tivas para que o acesso de convidados nos sites do SharePoint funcione.</span><span class="sxs-lookup"><span data-stu-id="249ff-128">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Captura de tela das configurações de convidado dos Grupos do Microsoft 365 no Centro de administração do Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="249ff-130">Para definir as configurações de convidado dos Grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="249ff-130">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="249ff-131">No centro de administração do Microsoft 365, no painel de navegação esquerdo, **expanda Configurações.**</span><span class="sxs-lookup"><span data-stu-id="249ff-131">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="249ff-132">Clique **em Configurações da Organização.**</span><span class="sxs-lookup"><span data-stu-id="249ff-132">Click **Org settings**.</span></span>
3. <span data-ttu-id="249ff-133">Na lista, clique em **Grupos do Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="249ff-133">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="249ff-134">Verifique se os proprietários do grupo Permitem que os proprietários adicionem pessoas de fora da sua organização aos Grupos do **Microsoft 365** como convidados e deixe que os membros do grupo convidado acessem as caixas de seleção de conteúdo do grupo. </span><span class="sxs-lookup"><span data-stu-id="249ff-134">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="249ff-135">Se você fez alterações, clique em **Salvar alterações.**</span><span class="sxs-lookup"><span data-stu-id="249ff-135">If you made changes, click **Save changes**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="249ff-136">Configurações de compartilhamento no nível da organização do SharePoint</span><span class="sxs-lookup"><span data-stu-id="249ff-136">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="249ff-137">Para que os convidados tenham acesso aos sites do SharePoint, as configurações de compartilhamento no nível da organização do SharePoint devem permitir o compartilhamento com convidados.</span><span class="sxs-lookup"><span data-stu-id="249ff-137">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="249ff-138">As configurações no nível da organização determinam as configurações que estarão disponíveis para sites individuais.</span><span class="sxs-lookup"><span data-stu-id="249ff-138">The organization-level settings determine the settings that will be available for individual sites.</span></span> <span data-ttu-id="249ff-139">As configurações de site não podem ser mais permissivas do que as configurações no nível da organização.</span><span class="sxs-lookup"><span data-stu-id="249ff-139">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="249ff-140">Se você quiser permitir o compartilhamento de arquivos e pastas não autenticados, escolha **Qualquer Pessoa.**</span><span class="sxs-lookup"><span data-stu-id="249ff-140">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="249ff-141">Se você quiser garantir que todas as pessoas de fora da sua organização tenham que se autenticar, escolha convidados **novos e existentes.**</span><span class="sxs-lookup"><span data-stu-id="249ff-141">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="249ff-142">Escolha a configuração mais permissiva que será necessária para qualquer site em sua organização.</span><span class="sxs-lookup"><span data-stu-id="249ff-142">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Captura de tela das configurações de compartilhamento no nível da organização do SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="249ff-144">Para definir as configurações de compartilhamento no nível da organização do SharePoint</span><span class="sxs-lookup"><span data-stu-id="249ff-144">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="249ff-145">No centro de administração do Microsoft 365, no painel de navegação esquerdo, em **Centros** de administração, clique **em SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="249ff-145">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="249ff-146">No centro de administração do SharePoint, no painel de navegação esquerdo, em **Políticas,** clique em **Compartilhamento.**</span><span class="sxs-lookup"><span data-stu-id="249ff-146">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="249ff-147">Certifique-se de que o compartilhamento externo do SharePoint está definido **como Qualquer pessoa** ou convidados novos e **existentes.**</span><span class="sxs-lookup"><span data-stu-id="249ff-147">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="249ff-148">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="249ff-148">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="249ff-149">Criar um site</span><span class="sxs-lookup"><span data-stu-id="249ff-149">Create a site</span></span>

<span data-ttu-id="249ff-150">A próxima etapa é criar o site que você planeja usar para colaborar com convidados.</span><span class="sxs-lookup"><span data-stu-id="249ff-150">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="249ff-151">Para criar um site</span><span class="sxs-lookup"><span data-stu-id="249ff-151">To create a site</span></span>
1. <span data-ttu-id="249ff-152">No centro de administração do SharePoint, em **sites**, clique **sites ativos**.</span><span class="sxs-lookup"><span data-stu-id="249ff-152">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="249ff-153">Clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="249ff-153">Click **Create**.</span></span>
3. <span data-ttu-id="249ff-154">Clique **em Site de Equipe.**</span><span class="sxs-lookup"><span data-stu-id="249ff-154">Click **Team site**.</span></span>
4. <span data-ttu-id="249ff-155">Digite um nome de site e insira um nome para o proprietário do grupo (proprietário do site).</span><span class="sxs-lookup"><span data-stu-id="249ff-155">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="249ff-156">Em **Configurações Avançadas,** escolha se deseja que este site seja público ou privado.</span><span class="sxs-lookup"><span data-stu-id="249ff-156">Under **Advanced settings**, choose if you want this site to be a public or private one.</span></span>
6. <span data-ttu-id="249ff-157">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="249ff-157">Click **Next**.</span></span>
7. <span data-ttu-id="249ff-158">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="249ff-158">Click **Finish**.</span></span>

<span data-ttu-id="249ff-159">Convidaremos os usuários mais tarde.</span><span class="sxs-lookup"><span data-stu-id="249ff-159">We'll invite users later.</span></span> <span data-ttu-id="249ff-160">Em seguida, é importante verificar as configurações de compartilhamento no nível do site para este site.</span><span class="sxs-lookup"><span data-stu-id="249ff-160">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="249ff-161">Configurações de compartilhamento no nível do site do SharePoint</span><span class="sxs-lookup"><span data-stu-id="249ff-161">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="249ff-162">Verifique as configurações de compartilhamento no nível do site para garantir que elas permitam o tipo de acesso que você deseja para esse site.</span><span class="sxs-lookup"><span data-stu-id="249ff-162">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="249ff-163">Por exemplo, se você definir as configurações no nível da organização como Qualquer **Pessoa,** mas quiser que todos os convidados se autentiem nesse site, certifique-se de que as configurações de compartilhamento no nível do site estão definidas como Convidados novos e existentes. </span><span class="sxs-lookup"><span data-stu-id="249ff-163">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="249ff-164">Observe que o site não pode ser compartilhado com pessoas não autenticadas **(** configuração de Qualquer pessoa), mas arquivos e pastas individuais podem.</span><span class="sxs-lookup"><span data-stu-id="249ff-164">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

<span data-ttu-id="249ff-165">Você também pode usar [rótulos de sensibilidade para controlar as configurações de compartilhamento externo para sites do SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)</span><span class="sxs-lookup"><span data-stu-id="249ff-165">You can also use [sensitivity labels to control external sharing settings for SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

![Captura de tela das configurações de compartilhamento de site externo do SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="249ff-167">Para definir configurações de compartilhamento no nível do site</span><span class="sxs-lookup"><span data-stu-id="249ff-167">To set site-level sharing settings</span></span>
1. <span data-ttu-id="249ff-168">No centro de administração do SharePoint, na navegação à esquerda, expanda a opção **Sites** e clique em **Sites ativos**.</span><span class="sxs-lookup"><span data-stu-id="249ff-168">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="249ff-169">Selecione o site que você deseja compartilhar.</span><span class="sxs-lookup"><span data-stu-id="249ff-169">Select the site that you want to share.</span></span>
3. <span data-ttu-id="249ff-170">Clique em ...e clique em **Compartilhamento.**</span><span class="sxs-lookup"><span data-stu-id="249ff-170">Click ..., and click **Sharing**.</span></span>
4. <span data-ttu-id="249ff-171">Certifique-se de que o compartilhamento está definido **como Qualquer** pessoa ou convidados novos **e existentes.**</span><span class="sxs-lookup"><span data-stu-id="249ff-171">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="249ff-172">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="249ff-172">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="249ff-173">Convidar usuários</span><span class="sxs-lookup"><span data-stu-id="249ff-173">Invite users</span></span>

<span data-ttu-id="249ff-174">As configurações de compartilhamento de convidados agora estão configuradas, para que você possa começar a adicionar usuários internos e convidados ao seu site.</span><span class="sxs-lookup"><span data-stu-id="249ff-174">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="249ff-175">O acesso ao site é controlado por meio do Grupo do Microsoft 365 associado, portanto, adicionaremos usuários lá.</span><span class="sxs-lookup"><span data-stu-id="249ff-175">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="249ff-176">Para convidar usuários internos para um grupo</span><span class="sxs-lookup"><span data-stu-id="249ff-176">To invite internal users to a group</span></span>
1. <span data-ttu-id="249ff-177">Navegue até o site em que deseja adicionar usuários.</span><span class="sxs-lookup"><span data-stu-id="249ff-177">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="249ff-178">Clique **no** link Membros no canto superior direito que indica a contagem de membros.</span><span class="sxs-lookup"><span data-stu-id="249ff-178">Click **Members** link in the upper right which denotes the member count.</span></span>
3. <span data-ttu-id="249ff-179">Clique em **Adicionar membros**.</span><span class="sxs-lookup"><span data-stu-id="249ff-179">Click **Add members**.</span></span>
4. <span data-ttu-id="249ff-180">Digite os nomes ou endereços de email dos usuários que você deseja convidar para o site e clique em **Salvar.**</span><span class="sxs-lookup"><span data-stu-id="249ff-180">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="249ff-181">Os convidados não podem ser adicionados do site.</span><span class="sxs-lookup"><span data-stu-id="249ff-181">Guests can't be added from the site.</span></span> <span data-ttu-id="249ff-182">Você precisa adicioná-los usando o Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="249ff-182">You need to add them using Outlook on the web.</span></span> <span data-ttu-id="249ff-183">Portanto, como pré-requisito para adicionar e convidar convidados a um grupo, clique na URL do site na coluna **url**  para navegar até a página específica do site.</span><span class="sxs-lookup"><span data-stu-id="249ff-183">Therefore, as a prerequisite to add and invite guests to a group, click the URL of the site in the **URL**  column to navigate to the site-specific page.</span></span> <span data-ttu-id="249ff-184">Nesta página, clique no ícone do **iniciador de aplicativos** e selecione **Outlook.**</span><span class="sxs-lookup"><span data-stu-id="249ff-184">From this page, click the **App launcher** icon and select **Outlook**.</span></span> <span data-ttu-id="249ff-185">Esta é a tela da qual você pode convidar convidados para um grupo, para a qual o procedimento é descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="249ff-185">This is the screen from which you can invite guests into a group, for which procedure is described below.</span></span>

<span data-ttu-id="249ff-186">Para convidar convidados para um grupo</span><span class="sxs-lookup"><span data-stu-id="249ff-186">To invite guests to a group</span></span>
1. <span data-ttu-id="249ff-187">Em **Grupos,** clique no grupo para o qual você deseja convidar convidados.</span><span class="sxs-lookup"><span data-stu-id="249ff-187">Under **Groups**, click the group to which you want to invite guests.</span></span>
2. <span data-ttu-id="249ff-188">Abra o cartão de visita do grupo, **clique** no link Membros no canto superior direito (o link que indica a contagem de membros).</span><span class="sxs-lookup"><span data-stu-id="249ff-188">Open the group contact card, click **Members** link in the upper right (the link which denotes the member count).</span></span>
3. <span data-ttu-id="249ff-189">clique **em Adicionar membros**.</span><span class="sxs-lookup"><span data-stu-id="249ff-189">click **Add members**.</span></span>
4. <span data-ttu-id="249ff-190">Digite os endereços de email dos convidados que você deseja convidar e clique em **Adicionar.**</span><span class="sxs-lookup"><span data-stu-id="249ff-190">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
5. <span data-ttu-id="249ff-191">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="249ff-191">Click **Close**.</span></span>
<span data-ttu-id="249ff-192">Observe que você precisará **clicar** em Fechar somente se não for o proprietário do grupo e, como resultado, não tiver permissão para adicionar o convidado ao grupo.</span><span class="sxs-lookup"><span data-stu-id="249ff-192">Note that you need to click **Close** only if you are not the owner of the group and as a result, you are not allowed to add the guest into the group.</span></span> <span data-ttu-id="249ff-193">Nesses casos, a solicitação para adicionar o convidado ao grupo é transferida para o proprietário do grupo para aprovação.</span><span class="sxs-lookup"><span data-stu-id="249ff-193">In such cases, the request to add the guest into the group is transferred to the group owner for approval.</span></span>

## <a name="see-also"></a><span data-ttu-id="249ff-194">Confira também</span><span class="sxs-lookup"><span data-stu-id="249ff-194">See also</span></span>

[<span data-ttu-id="249ff-195">Práticas recomendadas para compartilhar arquivos e pastas com usuários não autenticados</span><span class="sxs-lookup"><span data-stu-id="249ff-195">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="249ff-196">Limitar a exposição acidental dos arquivos ao compartilhar com convidados</span><span class="sxs-lookup"><span data-stu-id="249ff-196">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="249ff-197">Criar um ambiente de compartilhamento de convidados seguro</span><span class="sxs-lookup"><span data-stu-id="249ff-197">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="249ff-198">Crie uma extranet B2B com convidados gerenciados</span><span class="sxs-lookup"><span data-stu-id="249ff-198">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="249ff-199">Integração do SharePoint e OneDrive com o Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="249ff-199">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
