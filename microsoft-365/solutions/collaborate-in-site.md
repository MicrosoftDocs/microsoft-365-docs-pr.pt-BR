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
description: Saiba mais sobre as etapas de configuração do 365 da Microsoft necessárias para configurar um site do SharePoint para colaboração com convidados.
ms.openlocfilehash: df9068ef4b4eb35f946b78d8f7fefa01c254c79c
ms.sourcegitcommit: 8a726ed7ec19a8728c079780fa4d343a5f759fbb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49029988"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="f0605-103">Colaborar com convidados em um site</span><span class="sxs-lookup"><span data-stu-id="f0605-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="f0605-104">Se você precisar colaborar com convidados entre documentos, dados e listas, poderá usar um site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f0605-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="f0605-105">Os sites modernos do SharePoint estão conectados a grupos do Microsoft 365 e podem gerenciar a associação do site e fornecer ferramentas de colaboração adicionais, como uma caixa de correio compartilhada e um calendário.</span><span class="sxs-lookup"><span data-stu-id="f0605-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and a calendar.</span></span>

<span data-ttu-id="f0605-106">Neste artigo, veremos as etapas de configuração do Microsoft 365 necessárias para configurar um site do SharePoint para colaboração com convidados.</span><span class="sxs-lookup"><span data-stu-id="f0605-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="f0605-107">Demonstração de vídeo</span><span class="sxs-lookup"><span data-stu-id="f0605-107">Video demonstration</span></span>

<span data-ttu-id="f0605-108">Este vídeo mostra as etapas de configuração descritas neste documento.</span><span class="sxs-lookup"><span data-stu-id="f0605-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="f0605-109">Configurações de colaboração externa do Azure</span><span class="sxs-lookup"><span data-stu-id="f0605-109">Azure external collaboration settings</span></span>

<span data-ttu-id="f0605-110">O compartilhamento no Microsoft 365 é regido no seu nível mais alto pelas [configurações de relações organizacionais no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="f0605-110">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="f0605-111">Se o compartilhamento de convidados estiver desabilitado ou restrito no Azure AD, essa configuração substituirá as configurações de compartilhamento que você configurar no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f0605-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="f0605-112">Verifique as configurações de colaboração externa para garantir que o compartilhamento com convidados não seja bloqueado.</span><span class="sxs-lookup"><span data-stu-id="f0605-112">Check the external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Captura de tela da página de configurações de colaboração externa do Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="f0605-114">Para definir configurações de colaboração externa</span><span class="sxs-lookup"><span data-stu-id="f0605-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="f0605-115">Faça logon no Azure Active Directory em [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="f0605-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="f0605-116">No painel de navegação esquerdo, clique em **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="f0605-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="f0605-117">Clique em **identidades externas**.</span><span class="sxs-lookup"><span data-stu-id="f0605-117">Click **External identities**.</span></span>
4. <span data-ttu-id="f0605-118">Na tela **introdução** , no painel de navegação esquerdo, clique em **configurações de colaboração externa**.</span><span class="sxs-lookup"><span data-stu-id="f0605-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="f0605-119">Certifique-se de que **Administradores e usuários na função de convite de convidado podem convidar** e **os membros podem convidar** estão definidos como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="f0605-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="f0605-120">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f0605-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="f0605-121">Observe as configurações na seção **restrições de colaboração** .</span><span class="sxs-lookup"><span data-stu-id="f0605-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="f0605-122">Certifique-se de que os domínios dos convidados com os quais você deseja colaborar não estão bloqueados.</span><span class="sxs-lookup"><span data-stu-id="f0605-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="f0605-123">Se você trabalha com convidados de várias organizações, convém restringir sua capacidade de acessar dados de diretório.</span><span class="sxs-lookup"><span data-stu-id="f0605-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="f0605-124">Isso impedirá que você veja quem mais é um convidado no diretório.</span><span class="sxs-lookup"><span data-stu-id="f0605-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="f0605-125">Para fazer isso, em **restrições de acesso de usuário convidado** , selecione **os usuários convidados têm acesso limitado às propriedades e à associação de configurações de objetos de diretório** ou **o acesso de usuário convidado é restrito a propriedades e associações de seus próprios objetos de diretório**.</span><span class="sxs-lookup"><span data-stu-id="f0605-125">To do this, under **Guest user access restrictions** , select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="f0605-126">Configurações de convidado de grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f0605-126">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="f0605-127">Os sites modernos do SharePoint usam os grupos do Microsoft 365 para controlar o acesso ao site.</span><span class="sxs-lookup"><span data-stu-id="f0605-127">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="f0605-128">As configurações de convidado do Microsoft 365 groups devem ser ativadas para que o acesso de convidados nos sites do SharePoint funcione.</span><span class="sxs-lookup"><span data-stu-id="f0605-128">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Captura de tela das configurações de convidado dos Grupos do Microsoft 365 no Centro de administração do Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="f0605-130">Para definir as configurações de convidados de grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f0605-130">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="f0605-131">No centro de administração do Microsoft 365, no painel de navegação esquerdo, expanda **configurações**.</span><span class="sxs-lookup"><span data-stu-id="f0605-131">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="f0605-132">Clique em **configurações da organização**.</span><span class="sxs-lookup"><span data-stu-id="f0605-132">Click **Org settings**.</span></span>
3. <span data-ttu-id="f0605-133">Na lista, clique em **Microsoft 365 grupos**.</span><span class="sxs-lookup"><span data-stu-id="f0605-133">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="f0605-134">Certifique-se de que os **proprietários de grupo permitem que as pessoas de fora da sua organização para o Microsoft 365 grupos de** convidados e **permitir que os membros do grupo convidado acessem o conteúdo do grupo de acesso** sejam verificados.</span><span class="sxs-lookup"><span data-stu-id="f0605-134">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="f0605-135">Se você tiver feito alterações, clique em **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="f0605-135">If you made changes, click **Save changes**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="f0605-136">Configurações de compartilhamento no nível da organização do SharePoint</span><span class="sxs-lookup"><span data-stu-id="f0605-136">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="f0605-137">Para que os convidados tenham acesso aos sites do SharePoint, as configurações de compartilhamento no nível da organização do SharePoint devem permitir o compartilhamento com convidados.</span><span class="sxs-lookup"><span data-stu-id="f0605-137">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="f0605-138">As configurações de nível de organização determinam as configurações que estarão disponíveis para sites individuais.</span><span class="sxs-lookup"><span data-stu-id="f0605-138">The organization-level settings determine the settings that will be available for individual sites.</span></span> <span data-ttu-id="f0605-139">As configurações do site não podem ser mais permissivas do que as configurações no nível da organização.</span><span class="sxs-lookup"><span data-stu-id="f0605-139">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="f0605-140">Se você quiser permitir o compartilhamento de arquivos e pastas não autenticados, escolha **qualquer pessoa**.</span><span class="sxs-lookup"><span data-stu-id="f0605-140">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="f0605-141">Se você quiser garantir que todas as pessoas de fora da sua organização tenham que se autenticar, escolha **novos e existentes convidados**.</span><span class="sxs-lookup"><span data-stu-id="f0605-141">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="f0605-142">Escolha a configuração mais permissiva que será necessária para qualquer site em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f0605-142">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Captura de tela das configurações de compartilhamento no nível da organização do SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="f0605-144">Para definir as configurações de compartilhamento no nível da organização do SharePoint</span><span class="sxs-lookup"><span data-stu-id="f0605-144">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="f0605-145">No centro de administração do Microsoft 365, no painel de navegação esquerdo, em **centros de administração** , clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="f0605-145">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers** , click **SharePoint**.</span></span>
2. <span data-ttu-id="f0605-146">No centro de administração do SharePoint, no painel de navegação esquerdo, em **políticas** , clique em **compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="f0605-146">In the SharePoint admin center, in the left navigation pane, under **Policies** , click **Sharing**.</span></span>
3. <span data-ttu-id="f0605-147">Verifique se o compartilhamento externo do SharePoint está definido como **qualquer pessoa** ou **novo convidado existente**.</span><span class="sxs-lookup"><span data-stu-id="f0605-147">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="f0605-148">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f0605-148">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="f0605-149">Criar um site</span><span class="sxs-lookup"><span data-stu-id="f0605-149">Create a site</span></span>

<span data-ttu-id="f0605-150">A próxima etapa é criar o site que você planeja usar para colaborar com convidados.</span><span class="sxs-lookup"><span data-stu-id="f0605-150">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="f0605-151">Para criar um site</span><span class="sxs-lookup"><span data-stu-id="f0605-151">To create a site</span></span>
1. <span data-ttu-id="f0605-152">No centro de administração do SharePoint, em **sites** , clique **sites ativos**.</span><span class="sxs-lookup"><span data-stu-id="f0605-152">In the SharePoint admin center, under **Sites** , click **Active sites**.</span></span>
2. <span data-ttu-id="f0605-153">Clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="f0605-153">Click **Create**.</span></span>
3. <span data-ttu-id="f0605-154">Clique em **site de equipe**.</span><span class="sxs-lookup"><span data-stu-id="f0605-154">Click **Team site**.</span></span>
4. <span data-ttu-id="f0605-155">Digite um nome de site e insira um nome para o proprietário do grupo (proprietário do site).</span><span class="sxs-lookup"><span data-stu-id="f0605-155">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="f0605-156">Em **Configurações avançadas** , escolha se você deseja que esse site seja público ou privado.</span><span class="sxs-lookup"><span data-stu-id="f0605-156">Under **Advanced settings** , choose if you want this site to be a public or private one.</span></span>
6. <span data-ttu-id="f0605-157">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f0605-157">Click **Next**.</span></span>
7. <span data-ttu-id="f0605-158">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="f0605-158">Click **Finish**.</span></span>

<span data-ttu-id="f0605-159">Vamos convidar os usuários mais tarde.</span><span class="sxs-lookup"><span data-stu-id="f0605-159">We'll invite users later.</span></span> <span data-ttu-id="f0605-160">Em seguida, é importante verificar as configurações de compartilhamento no nível do site para este site.</span><span class="sxs-lookup"><span data-stu-id="f0605-160">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="f0605-161">Configurações de compartilhamento no nível do site do SharePoint</span><span class="sxs-lookup"><span data-stu-id="f0605-161">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="f0605-162">Verifique as configurações de compartilhamento no nível do site para garantir que elas permitam o tipo de acesso que você deseja para este site.</span><span class="sxs-lookup"><span data-stu-id="f0605-162">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="f0605-163">Por exemplo, se você definir as configurações de nível de organização como **qualquer pessoa** , mas quiser que todos os convidados autentiquem esse site, verifique se as configurações de compartilhamento no nível do site estão definidas para **convidados novos e existentes**.</span><span class="sxs-lookup"><span data-stu-id="f0605-163">For example, if you set the organization-level settings to **Anyone** , but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="f0605-164">Observe que o site não pode ser compartilhado com pessoas não autenticadas (configuração de **qualquer pessoa** ), mas arquivos e pastas individuais podem.</span><span class="sxs-lookup"><span data-stu-id="f0605-164">Note that the site cannot be shared with unauthenticated people ( **Anyone** setting), but individual files and folders can.</span></span>

![Captura de tela das configurações de compartilhamento de site externo do SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="f0605-166">Para definir configurações de compartilhamento no nível do site</span><span class="sxs-lookup"><span data-stu-id="f0605-166">To set site-level sharing settings</span></span>
1. <span data-ttu-id="f0605-167">No centro de administração do SharePoint, na navegação à esquerda, expanda a opção **Sites** e clique em **Sites ativos**.</span><span class="sxs-lookup"><span data-stu-id="f0605-167">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="f0605-168">Selecione o site que você deseja compartilhar.</span><span class="sxs-lookup"><span data-stu-id="f0605-168">Select the site that you want to share.</span></span>
3. <span data-ttu-id="f0605-169">Clique em... e em **compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="f0605-169">Click ..., and click **Sharing**.</span></span>
4. <span data-ttu-id="f0605-170">Verifique se o compartilhamento está definido como **qualquer pessoa** ou **convidado novo e existente**.</span><span class="sxs-lookup"><span data-stu-id="f0605-170">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="f0605-171">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f0605-171">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="f0605-172">Convidar usuários</span><span class="sxs-lookup"><span data-stu-id="f0605-172">Invite users</span></span>

<span data-ttu-id="f0605-173">As configurações de compartilhamento de convidados agora estão configuradas para que você possa começar a adicionar usuários internos e convidados ao seu site.</span><span class="sxs-lookup"><span data-stu-id="f0605-173">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="f0605-174">O acesso ao site é controlado através do grupo associado da Microsoft 365, portanto, vamos adicionar usuários lá.</span><span class="sxs-lookup"><span data-stu-id="f0605-174">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="f0605-175">Para convidar usuários internos para um grupo</span><span class="sxs-lookup"><span data-stu-id="f0605-175">To invite internal users to a group</span></span>
1. <span data-ttu-id="f0605-176">Navegue até o site em que você deseja adicionar usuários.</span><span class="sxs-lookup"><span data-stu-id="f0605-176">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="f0605-177">Clique no link **Membros** no canto superior direito que denota a contagem de membros.</span><span class="sxs-lookup"><span data-stu-id="f0605-177">Click **Members** link in the upper right which denotes the member count.</span></span>
3. <span data-ttu-id="f0605-178">Clique em **Adicionar membros**.</span><span class="sxs-lookup"><span data-stu-id="f0605-178">Click **Add members**.</span></span>
4. <span data-ttu-id="f0605-179">Digite os nomes ou endereços de email dos usuários que você deseja convidar para o site e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="f0605-179">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="f0605-180">Os usuários convidados não podem ser adicionados do site.</span><span class="sxs-lookup"><span data-stu-id="f0605-180">Guest users can't be added from the site.</span></span> <span data-ttu-id="f0605-181">Você precisa adicioná-los usando o Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="f0605-181">You need to add them using Outlook on the web.</span></span> <span data-ttu-id="f0605-182">Portanto, como pré-requisito para adicionar e convidar convidados para um grupo, clique na URL do site na coluna **URL**  para navegar até a página específica do site.</span><span class="sxs-lookup"><span data-stu-id="f0605-182">Therefore, as a prerequisite to add and invite guests to a group, click the URL of the site in the **URL**  column to navigate to the site-specific page.</span></span> <span data-ttu-id="f0605-183">Nessa página, clique no ícone do **inicializador de aplicativos** e selecione **Outlook**.</span><span class="sxs-lookup"><span data-stu-id="f0605-183">From this page, click the **App launcher** icon and select **Outlook**.</span></span> <span data-ttu-id="f0605-184">Esta é a tela na qual você pode convidar convidados para um grupo, para o qual o procedimento descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="f0605-184">This is the screen from which you can invite guests into a group, for which procedure is described below.</span></span>

<span data-ttu-id="f0605-185">Para convidar convidados para um grupo</span><span class="sxs-lookup"><span data-stu-id="f0605-185">To invite guests to a group</span></span>
1. <span data-ttu-id="f0605-186">Em **grupos** , clique no grupo para o qual você deseja convidar convidados.</span><span class="sxs-lookup"><span data-stu-id="f0605-186">Under **Groups** , click the group to which you want to invite guests.</span></span>
2. <span data-ttu-id="f0605-187">Abra o cartão de visita do grupo, clique no link **Membros** no canto superior direito (o link que denota a contagem de membros).</span><span class="sxs-lookup"><span data-stu-id="f0605-187">Open the group contact card, click **Members** link in the upper right (the link which denotes the member count).</span></span>
3. <span data-ttu-id="f0605-188">clique em **adicionar membros**.</span><span class="sxs-lookup"><span data-stu-id="f0605-188">click **Add members**.</span></span>
4. <span data-ttu-id="f0605-189">Digite os endereços de email dos convidados que você deseja convidar e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="f0605-189">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
5. <span data-ttu-id="f0605-190">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="f0605-190">Click **Close**.</span></span>
<span data-ttu-id="f0605-191">Observe que você precisa clicar em **fechar** somente se não for o proprietário do grupo e, como resultado, você não tem permissão para adicionar o convidado ao grupo.</span><span class="sxs-lookup"><span data-stu-id="f0605-191">Note that you need to click **Close** only if you are not the owner of the group and as a result, you are not allowed to add the guest into the group.</span></span> <span data-ttu-id="f0605-192">Nesses casos, a solicitação para adicionar o convidado ao grupo é transferida para o proprietário do grupo para aprovação.</span><span class="sxs-lookup"><span data-stu-id="f0605-192">In such cases, the request to add the guest into the group is transferred to the group owner for approval.</span></span>

## <a name="see-also"></a><span data-ttu-id="f0605-193">Confira também</span><span class="sxs-lookup"><span data-stu-id="f0605-193">See also</span></span>

[<span data-ttu-id="f0605-194">Práticas recomendadas para compartilhar arquivos e pastas com usuários não autenticados</span><span class="sxs-lookup"><span data-stu-id="f0605-194">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="f0605-195">Limitar a exposição acidental dos arquivos ao compartilhar com convidados</span><span class="sxs-lookup"><span data-stu-id="f0605-195">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="f0605-196">Criar um ambiente de compartilhamento de convidados seguro</span><span class="sxs-lookup"><span data-stu-id="f0605-196">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="f0605-197">Crie uma extranet B2B com convidados gerenciados</span><span class="sxs-lookup"><span data-stu-id="f0605-197">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="f0605-198">Integração do SharePoint e do OneDrive com o B2B do Azure AD</span><span class="sxs-lookup"><span data-stu-id="f0605-198">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
