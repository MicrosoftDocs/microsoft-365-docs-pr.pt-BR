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
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Saiba mais sobre as etapas de configuração do 365 da Microsoft necessárias para configurar um site do SharePoint para colaboração com convidados.
ms.openlocfilehash: c04114218342a2d65b318c71d061c2a0ed815fab
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46797811"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="879b8-103">Colaborar com convidados em um site</span><span class="sxs-lookup"><span data-stu-id="879b8-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="879b8-104">Se você precisar colaborar com convidados entre documentos, dados e listas, poderá usar um site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="879b8-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="879b8-105">Os sites modernos do SharePoint estão conectados a grupos do Microsoft 365 e podem gerenciar a associação do site e fornecer ferramentas de colaboração adicionais, como uma caixa de correio e um calendário compartilhados.</span><span class="sxs-lookup"><span data-stu-id="879b8-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and calendar.</span></span>

<span data-ttu-id="879b8-106">Neste artigo, veremos as etapas de configuração do Microsoft 365 necessárias para configurar um site do SharePoint para colaboração com convidados.</span><span class="sxs-lookup"><span data-stu-id="879b8-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="879b8-107">Demonstração de vídeo</span><span class="sxs-lookup"><span data-stu-id="879b8-107">Video demonstration</span></span>

<span data-ttu-id="879b8-108">Este vídeo mostra as etapas de configuração descritas neste documento.</span><span class="sxs-lookup"><span data-stu-id="879b8-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="879b8-109">Configurações de relações organizacionais do Azure</span><span class="sxs-lookup"><span data-stu-id="879b8-109">Azure Organizational relationships settings</span></span>

<span data-ttu-id="879b8-110">O compartilhamento no Microsoft 365 é regido no seu nível mais alto pelas [configurações de relações organizacionais no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="879b8-110">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="879b8-111">Se o compartilhamento de convidados estiver desabilitado ou restrito no Azure AD, isso substituirá as configurações de compartilhamento que você configurar no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="879b8-111">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="879b8-112">Verifique as configurações de relações organizacionais para garantir que o compartilhamento com convidados não seja bloqueado.</span><span class="sxs-lookup"><span data-stu-id="879b8-112">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Captura de tela da página de configurações das Relações Organizacionais do Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="879b8-114">Para definir as configurações de relação organizacional</span><span class="sxs-lookup"><span data-stu-id="879b8-114">To set organizational relationship settings</span></span>

1. <span data-ttu-id="879b8-115">Faça logon no Microsoft Azure em [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="879b8-115">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="879b8-116">Na navegação à esquerda, clique em **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="879b8-116">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="879b8-117">No painel **visão geral** , clique em **relações organizacionais**.</span><span class="sxs-lookup"><span data-stu-id="879b8-117">In the **Overview** pane, click **Organizational relationships**.</span></span>
4. <span data-ttu-id="879b8-118">No painel **relações organizacionais** , clique em **configurações**.</span><span class="sxs-lookup"><span data-stu-id="879b8-118">In the **Organizational relationships** pane, click **Settings**.</span></span>
5. <span data-ttu-id="879b8-119">Certifique-se de que **Administradores e usuários na função de convite de convidado podem convidar** e **os membros podem convidar** estão definidos como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="879b8-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="879b8-120">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="879b8-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="879b8-121">Observe as configurações na seção **restrições de colaboração** .</span><span class="sxs-lookup"><span data-stu-id="879b8-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="879b8-122">Certifique-se de que os domínios dos convidados com os quais você deseja colaborar não estão bloqueados.</span><span class="sxs-lookup"><span data-stu-id="879b8-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="879b8-123">Se você trabalha com convidados de várias organizações, convém restringir sua capacidade de acessar dados de diretório.</span><span class="sxs-lookup"><span data-stu-id="879b8-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="879b8-124">Isso impedirá que você veja quem mais é um convidado no diretório.</span><span class="sxs-lookup"><span data-stu-id="879b8-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="879b8-125">Para fazer isso, em **restrições de acesso de usuário convidado**, selecione **os usuários convidados têm acesso limitado às propriedades e à associação de configurações de objetos de diretório** ou **o acesso de usuário convidado é restrito a propriedades e associações de seus próprios objetos de diretório**.</span><span class="sxs-lookup"><span data-stu-id="879b8-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="879b8-126">Configurações de convidado de grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="879b8-126">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="879b8-127">Os sites modernos do SharePoint usam os grupos do Microsoft 365 para controlar o acesso ao site.</span><span class="sxs-lookup"><span data-stu-id="879b8-127">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="879b8-128">As configurações de convidado do Microsoft 365 groups devem ser ativadas para que o acesso de convidados nos sites do SharePoint funcione.</span><span class="sxs-lookup"><span data-stu-id="879b8-128">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Captura de tela das configurações de convidado dos Grupos do Microsoft 365 no Centro de administração do Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="879b8-130">Para definir as configurações de convidados de grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="879b8-130">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="879b8-131">No centro de administração do Microsoft 365, no painel de navegação à esquerda, expanda **configurações**.</span><span class="sxs-lookup"><span data-stu-id="879b8-131">In the Microsoft 365 admin center, in the left navigation, expand **Settings**.</span></span>
2. <span data-ttu-id="879b8-132">Clique em **serviços & suplementos**.</span><span class="sxs-lookup"><span data-stu-id="879b8-132">Click **Services & add-ins**.</span></span>
3. <span data-ttu-id="879b8-133">Na lista, clique em **Microsoft 365 grupos**.</span><span class="sxs-lookup"><span data-stu-id="879b8-133">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="879b8-134">Certifique-se de que o **grupo permitir Membros fora do seu conteúdo de grupo de acesso à organização** e **que os proprietários do grupo adicionem pessoas fora da sua organização a grupos de** seleção.</span><span class="sxs-lookup"><span data-stu-id="879b8-134">Ensure that the **Let group members outside your organization access group content** and **Let group owners add people outside your organization to groups** check boxes are both checked.</span></span>
5. <span data-ttu-id="879b8-135">Se você tiver feito alterações, clique em **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="879b8-135">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="879b8-136">Configurações de compartilhamento de nível da organização do SharePoint</span><span class="sxs-lookup"><span data-stu-id="879b8-136">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="879b8-137">Para que os convidados tenham acesso aos sites do SharePoint, as configurações de compartilhamento no nível da organização do SharePoint devem permitir o compartilhamento com convidados.</span><span class="sxs-lookup"><span data-stu-id="879b8-137">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="879b8-138">As configurações de nível de organização determinam quais configurações estão disponíveis para sites individuais.</span><span class="sxs-lookup"><span data-stu-id="879b8-138">The organization-level settings determine what settings are available for individual sites.</span></span> <span data-ttu-id="879b8-139">As configurações do site não podem ser mais permissivas do que as configurações no nível da organização.</span><span class="sxs-lookup"><span data-stu-id="879b8-139">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="879b8-140">Se você quiser permitir o compartilhamento de arquivos e pastas não autenticados, escolha **qualquer pessoa**.</span><span class="sxs-lookup"><span data-stu-id="879b8-140">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="879b8-141">Se você quiser garantir que todas as pessoas de fora da sua organização tenham que se autenticar, escolha **novos e existentes convidados**.</span><span class="sxs-lookup"><span data-stu-id="879b8-141">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="879b8-142">Escolha a configuração mais permissiva que será necessária para qualquer site em sua organização.</span><span class="sxs-lookup"><span data-stu-id="879b8-142">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Captura de tela das configurações de compartilhamento no nível da organização do SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="879b8-144">Para definir as configurações de compartilhamento de nível da organização do SharePoint</span><span class="sxs-lookup"><span data-stu-id="879b8-144">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="879b8-145">No centro de administração do Microsoft 365, na navegação à esquerda, em **centros de administração**, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="879b8-145">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="879b8-146">No centro de administração do SharePoint, na navegação à esquerda, clique em **Compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="879b8-146">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="879b8-147">Verifique se o compartilhamento externo do SharePoint está definido como **qualquer pessoa** ou **novo convidado existente**.</span><span class="sxs-lookup"><span data-stu-id="879b8-147">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="879b8-148">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="879b8-148">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="879b8-149">Criar um site</span><span class="sxs-lookup"><span data-stu-id="879b8-149">Create a site</span></span>

<span data-ttu-id="879b8-150">A próxima etapa é criar o site que você planeja usar para colaborar com convidados.</span><span class="sxs-lookup"><span data-stu-id="879b8-150">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="879b8-151">Para criar um site</span><span class="sxs-lookup"><span data-stu-id="879b8-151">To create a site</span></span>
1. <span data-ttu-id="879b8-152">No centro de administração do SharePoint, em **sites**, clique **sites ativos**.</span><span class="sxs-lookup"><span data-stu-id="879b8-152">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="879b8-153">Clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="879b8-153">Click **Create**.</span></span>
3. <span data-ttu-id="879b8-154">Clique em **site de equipe**.</span><span class="sxs-lookup"><span data-stu-id="879b8-154">Click **Team site**.</span></span>
4. <span data-ttu-id="879b8-155">Digite um nome de site e insira um nome para o proprietário do grupo (proprietário do site).</span><span class="sxs-lookup"><span data-stu-id="879b8-155">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="879b8-156">Em **Configurações avançadas**, escolha se você deseja que este seja um site público ou privado.</span><span class="sxs-lookup"><span data-stu-id="879b8-156">Under **Advanced settings**, choose if you want this to be a public or private site.</span></span>
6. <span data-ttu-id="879b8-157">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="879b8-157">Click **Next**.</span></span>
7. <span data-ttu-id="879b8-158">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="879b8-158">Click **Finish**.</span></span>

<span data-ttu-id="879b8-159">Vamos convidar os usuários mais tarde.</span><span class="sxs-lookup"><span data-stu-id="879b8-159">We'll invite users later.</span></span> <span data-ttu-id="879b8-160">Em seguida, é importante verificar as configurações de compartilhamento no nível do site para este site.</span><span class="sxs-lookup"><span data-stu-id="879b8-160">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="879b8-161">Configurações de compartilhamento no nível do site do SharePoint</span><span class="sxs-lookup"><span data-stu-id="879b8-161">SharePoint site level sharing settings</span></span>

<span data-ttu-id="879b8-162">Verifique as configurações de compartilhamento no nível do site para garantir que elas permitam o tipo de acesso que você deseja para este site.</span><span class="sxs-lookup"><span data-stu-id="879b8-162">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="879b8-163">Por exemplo, se você definir as configurações de nível de organização como **qualquer pessoa**, mas quiser que todos os convidados autentiquem esse site, verifique se as configurações de compartilhamento no nível do site estão definidas para **convidados novos e existentes**.</span><span class="sxs-lookup"><span data-stu-id="879b8-163">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="879b8-164">Observe que o site não pode ser compartilhado com pessoas não autenticadas (configuração de**qualquer pessoa** ), mas arquivos e pastas individuais podem.</span><span class="sxs-lookup"><span data-stu-id="879b8-164">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

![Captura de tela das configurações de compartilhamento de site externo do SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="879b8-166">Para definir configurações de compartilhamento no nível do site</span><span class="sxs-lookup"><span data-stu-id="879b8-166">To set site-level sharing settings</span></span>
1. <span data-ttu-id="879b8-167">No centro de administração do SharePoint, na navegação à esquerda, expanda a opção **Sites** e clique em **Sites ativos**.</span><span class="sxs-lookup"><span data-stu-id="879b8-167">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="879b8-168">Selecione o site que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="879b8-168">Select the site that you just created.</span></span>
3. <span data-ttu-id="879b8-169">Na faixa de opções, clique em **Compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="879b8-169">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="879b8-170">Verifique se o compartilhamento está definido como **qualquer pessoa** ou **convidado novo e existente**.</span><span class="sxs-lookup"><span data-stu-id="879b8-170">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="879b8-171">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="879b8-171">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="879b8-172">Convidar usuários</span><span class="sxs-lookup"><span data-stu-id="879b8-172">Invite users</span></span>

<span data-ttu-id="879b8-173">As configurações de compartilhamento de convidados agora estão configuradas para que você possa começar a adicionar usuários internos e convidados ao seu site.</span><span class="sxs-lookup"><span data-stu-id="879b8-173">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="879b8-174">O acesso ao site é controlado através do grupo associado da Microsoft 365, portanto, vamos adicionar usuários lá.</span><span class="sxs-lookup"><span data-stu-id="879b8-174">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="879b8-175">Para convidar usuários internos para um grupo</span><span class="sxs-lookup"><span data-stu-id="879b8-175">To invite internal users to a group</span></span>
1. <span data-ttu-id="879b8-176">Navegue até o site em que você deseja adicionar usuários.</span><span class="sxs-lookup"><span data-stu-id="879b8-176">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="879b8-177">Clique em **Membros** no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="879b8-177">Click **Members** in the upper right.</span></span>
3. <span data-ttu-id="879b8-178">Clique em **Adicionar membros**.</span><span class="sxs-lookup"><span data-stu-id="879b8-178">Click **Add members**.</span></span>
4. <span data-ttu-id="879b8-179">Digite os nomes ou endereços de email dos usuários que você deseja convidar para o site e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="879b8-179">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="879b8-180">Os usuários convidados não podem ser adicionados do site.</span><span class="sxs-lookup"><span data-stu-id="879b8-180">Guest users can't be added from the site.</span></span> <span data-ttu-id="879b8-181">Você precisa adicioná-los usando o Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="879b8-181">You need to add them using Outlook on the web.</span></span>

<span data-ttu-id="879b8-182">Para convidar convidados para um grupo</span><span class="sxs-lookup"><span data-stu-id="879b8-182">To invite guests to a group</span></span>
1. <span data-ttu-id="879b8-183">No Outlook na Web, em **grupos**, clique no grupo em que você deseja adicionar membros.</span><span class="sxs-lookup"><span data-stu-id="879b8-183">In Outlook on the web, under **Groups**, click the group where you want to add members.</span></span>
2. <span data-ttu-id="879b8-184">Abra o cartão de visita do grupo e, em **mais opções** (...), clique em **adicionar membros**.</span><span class="sxs-lookup"><span data-stu-id="879b8-184">Open the group contact card, and then, under **More options** (...), click **Add members**.</span></span>
3. <span data-ttu-id="879b8-185">Digite os endereços de email dos convidados que você deseja convidar e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="879b8-185">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
4. <span data-ttu-id="879b8-186">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="879b8-186">Click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="879b8-187">Confira também</span><span class="sxs-lookup"><span data-stu-id="879b8-187">See Also</span></span>

[<span data-ttu-id="879b8-188">Práticas recomendadas para compartilhar arquivos e pastas com usuários não autenticados</span><span class="sxs-lookup"><span data-stu-id="879b8-188">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="879b8-189">Limitar a exposição acidental dos arquivos ao compartilhar com convidados</span><span class="sxs-lookup"><span data-stu-id="879b8-189">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="879b8-190">Criar um ambiente seguro de compartilhamento para convidados</span><span class="sxs-lookup"><span data-stu-id="879b8-190">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="879b8-191">Crie uma extranet B2B com convidados gerenciados</span><span class="sxs-lookup"><span data-stu-id="879b8-191">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

