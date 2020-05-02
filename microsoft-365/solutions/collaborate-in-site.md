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
ms.custom:
- M365solutions
localization_priority: Normal
f1.keywords: NOCSH
description: Saiba como colaborar com convidados em um site do SharePoint.
ms.openlocfilehash: b9b5a50b4d0f7486b3c86546a672b01db3a5b000
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/01/2020
ms.locfileid: "44002272"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="f05d0-103">Colaborar com convidados em um site</span><span class="sxs-lookup"><span data-stu-id="f05d0-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="f05d0-104">Se você precisar colaborar com convidados entre documentos, dados e listas, poderá usar um site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f05d0-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="f05d0-105">Os sites modernos do SharePoint estão conectados a grupos do Microsoft 365 e podem gerenciar a associação do site e fornecer ferramentas de colaboração adicionais, como uma caixa de correio e um calendário compartilhados.</span><span class="sxs-lookup"><span data-stu-id="f05d0-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and calendar.</span></span>

<span data-ttu-id="f05d0-106">Neste artigo, veremos as etapas de configuração do Microsoft 365 necessárias para configurar um site do SharePoint para colaboração com convidados.</span><span class="sxs-lookup"><span data-stu-id="f05d0-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="f05d0-107">Demonstração de vídeo</span><span class="sxs-lookup"><span data-stu-id="f05d0-107">Video demonstration</span></span>

<span data-ttu-id="f05d0-108">Este vídeo mostra as etapas de configuração descritas neste documento.</span><span class="sxs-lookup"><span data-stu-id="f05d0-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="f05d0-109">Configurações de relações organizacionais do Azure</span><span class="sxs-lookup"><span data-stu-id="f05d0-109">Azure Organizational relationships settings</span></span>

<span data-ttu-id="f05d0-110">O compartilhamento no Microsoft 365 é regido no seu nível mais alto pelas configurações de relações organizacionais no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f05d0-110">Sharing in Microsoft 365 is governed at its highest level by the organizational relationships settings in Azure Active Directory.</span></span> <span data-ttu-id="f05d0-111">Se o compartilhamento de convidados estiver desabilitado ou restrito no Azure AD, isso substituirá as configurações de compartilhamento que você configurar no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f05d0-111">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="f05d0-112">Verifique as configurações de relações organizacionais para garantir que o compartilhamento com convidados não seja bloqueado.</span><span class="sxs-lookup"><span data-stu-id="f05d0-112">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Captura de tela da página de configurações das Relações Organizacionais do Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="f05d0-114">Para definir as configurações de relação organizacional</span><span class="sxs-lookup"><span data-stu-id="f05d0-114">To set organizational relationship settings</span></span>

1. <span data-ttu-id="f05d0-115">Faça logon no Microsoft Azure em [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="f05d0-115">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="f05d0-116">Na navegação à esquerda, clique em **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-116">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="f05d0-117">No painel **visão geral** , clique em **relações organizacionais**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-117">In the **Overview** pane, click **Organizational relationships**.</span></span>
4. <span data-ttu-id="f05d0-118">No painel **relações organizacionais** , clique em **configurações**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-118">In the **Organizational relationships** pane, click **Settings**.</span></span>
5. <span data-ttu-id="f05d0-119">Certifique-se de que **Administradores e usuários na função de convite de convidado podem convidar** e **os membros podem convidar** estão definidos como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="f05d0-120">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="f05d0-121">Observe as configurações na seção **restrições de colaboração** .</span><span class="sxs-lookup"><span data-stu-id="f05d0-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="f05d0-122">Certifique-se de que os domínios dos convidados com os quais você deseja colaborar não estão bloqueados.</span><span class="sxs-lookup"><span data-stu-id="f05d0-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="f05d0-123">Configurações de convidado de grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f05d0-123">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="f05d0-124">Os sites modernos do SharePoint usam os grupos do Microsoft 365 para controlar o acesso ao site.</span><span class="sxs-lookup"><span data-stu-id="f05d0-124">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="f05d0-125">As configurações de convidado do Microsoft 365 groups devem ser ativadas para que o acesso de convidados nos sites do SharePoint funcione.</span><span class="sxs-lookup"><span data-stu-id="f05d0-125">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Captura de tela das configurações de convidado dos Grupos do Microsoft 365 no Centro de administração do Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="f05d0-127">Para definir as configurações de convidados de grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f05d0-127">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="f05d0-128">No centro de administração do Microsoft 365, no painel de navegação à esquerda, expanda **configurações**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-128">In the Microsoft 365 admin center, in the left navigation, expand **Settings**.</span></span>
2. <span data-ttu-id="f05d0-129">Clique em **serviços & suplementos**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-129">Click **Services & add-ins**.</span></span>
3. <span data-ttu-id="f05d0-130">Na lista, clique em **Microsoft 365 grupos**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-130">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="f05d0-131">Certifique-se de que o **grupo permitir Membros fora do seu conteúdo de grupo de acesso à organização** e **que os proprietários do grupo adicionem pessoas fora da sua organização a grupos de** seleção.</span><span class="sxs-lookup"><span data-stu-id="f05d0-131">Ensure that the **Let group members outside your organization access group content** and **Let group owners add people outside your organization to groups** check boxes are both checked.</span></span>
5. <span data-ttu-id="f05d0-132">Se você tiver feito alterações, clique em **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-132">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="f05d0-133">Configurações de compartilhamento de nível da organização do SharePoint</span><span class="sxs-lookup"><span data-stu-id="f05d0-133">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="f05d0-134">Para que os convidados tenham acesso aos sites do SharePoint, as configurações de compartilhamento no nível da organização do SharePoint devem permitir o compartilhamento com convidados.</span><span class="sxs-lookup"><span data-stu-id="f05d0-134">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="f05d0-135">As configurações de nível de organização determinam quais configurações estão disponíveis para sites individuais.</span><span class="sxs-lookup"><span data-stu-id="f05d0-135">The organization-level settings determine what settings are available for individual sites.</span></span> <span data-ttu-id="f05d0-136">As configurações do site não podem ser mais permissivas do que as configurações no nível da organização.</span><span class="sxs-lookup"><span data-stu-id="f05d0-136">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="f05d0-137">Se você quiser permitir o compartilhamento de arquivos e pastas não autenticados, escolha **qualquer pessoa**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-137">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="f05d0-138">Se você quiser garantir que todas as pessoas de fora da sua organização tenham que se autenticar, escolha **novos e existentes convidados**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-138">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="f05d0-139">Escolha a configuração mais permissiva que será necessária para qualquer site em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f05d0-139">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Captura de tela das configurações de compartilhamento no nível da organização do SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="f05d0-141">Para definir as configurações de compartilhamento de nível da organização do SharePoint</span><span class="sxs-lookup"><span data-stu-id="f05d0-141">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="f05d0-142">No centro de administração do Microsoft 365, na navegação à esquerda, em **centros de administração**, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-142">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="f05d0-143">No centro de administração do SharePoint, na navegação à esquerda, clique em **Compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-143">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="f05d0-144">Verifique se o compartilhamento externo do SharePoint está definido como **qualquer pessoa** ou **novo convidado existente**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-144">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="f05d0-145">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-145">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="f05d0-146">Criar um site</span><span class="sxs-lookup"><span data-stu-id="f05d0-146">Create a site</span></span>

<span data-ttu-id="f05d0-147">A próxima etapa é criar o site que você planeja usar para colaborar com convidados.</span><span class="sxs-lookup"><span data-stu-id="f05d0-147">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="f05d0-148">Para criar um site</span><span class="sxs-lookup"><span data-stu-id="f05d0-148">To create a site</span></span>
1. <span data-ttu-id="f05d0-149">No centro de administração do SharePoint, em **sites**, clique **sites ativos**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-149">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="f05d0-150">Clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-150">Click **Create**.</span></span>
3. <span data-ttu-id="f05d0-151">Clique em **site de equipe**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-151">Click **Team site**.</span></span>
4. <span data-ttu-id="f05d0-152">Digite um nome de site e insira um nome para o proprietário do grupo (proprietário do site).</span><span class="sxs-lookup"><span data-stu-id="f05d0-152">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="f05d0-153">Em **Configurações avançadas**, escolha se você deseja que este seja um site público ou privado.</span><span class="sxs-lookup"><span data-stu-id="f05d0-153">Under **Advanced settings**, choose if you want this to be a public or private site.</span></span>
6. <span data-ttu-id="f05d0-154">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-154">Click **Next**.</span></span>
7. <span data-ttu-id="f05d0-155">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-155">Click **Finish**.</span></span>

<span data-ttu-id="f05d0-156">Vamos convidar os usuários mais tarde.</span><span class="sxs-lookup"><span data-stu-id="f05d0-156">We'll invite users later.</span></span> <span data-ttu-id="f05d0-157">Em seguida, é importante verificar as configurações de compartilhamento no nível do site para este site.</span><span class="sxs-lookup"><span data-stu-id="f05d0-157">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="f05d0-158">Configurações de compartilhamento no nível do site do SharePoint</span><span class="sxs-lookup"><span data-stu-id="f05d0-158">SharePoint site level sharing settings</span></span>

<span data-ttu-id="f05d0-159">Verifique as configurações de compartilhamento no nível do site para garantir que elas permitam o tipo de acesso que você deseja para este site.</span><span class="sxs-lookup"><span data-stu-id="f05d0-159">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="f05d0-160">Por exemplo, se você definir as configurações de nível de organização como **qualquer pessoa**, mas quiser que todos os convidados autentiquem esse site, verifique se as configurações de compartilhamento no nível do site estão definidas para **convidados novos e existentes**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-160">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="f05d0-161">Observe que o site não pode ser compartilhado com pessoas não autenticadas (configuração de**qualquer pessoa** ), mas arquivos e pastas individuais podem.</span><span class="sxs-lookup"><span data-stu-id="f05d0-161">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

![Captura de tela das configurações de compartilhamento de site externo do SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="f05d0-163">Para definir configurações de compartilhamento no nível do site</span><span class="sxs-lookup"><span data-stu-id="f05d0-163">To set site-level sharing settings</span></span>
1. <span data-ttu-id="f05d0-164">No centro de administração do SharePoint, na navegação à esquerda, expanda a opção **Sites** e clique em **Sites ativos**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-164">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="f05d0-165">Selecione o site que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="f05d0-165">Select the site that you just created.</span></span>
3. <span data-ttu-id="f05d0-166">Na faixa de opções, clique em **Compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-166">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="f05d0-167">Verifique se o compartilhamento está definido como **qualquer pessoa** ou **convidado novo e existente**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-167">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="f05d0-168">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-168">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="f05d0-169">Convidar usuários</span><span class="sxs-lookup"><span data-stu-id="f05d0-169">Invite users</span></span>

<span data-ttu-id="f05d0-170">As configurações de compartilhamento de convidados agora estão configuradas para que você possa começar a adicionar usuários internos e convidados ao seu site.</span><span class="sxs-lookup"><span data-stu-id="f05d0-170">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="f05d0-171">O acesso ao site é controlado através do grupo associado da Microsoft 365, portanto, vamos adicionar usuários lá.</span><span class="sxs-lookup"><span data-stu-id="f05d0-171">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="f05d0-172">Para convidar usuários internos para um grupo</span><span class="sxs-lookup"><span data-stu-id="f05d0-172">To invite internal users to a group</span></span>
1. <span data-ttu-id="f05d0-173">Navegue até o site em que você deseja adicionar usuários.</span><span class="sxs-lookup"><span data-stu-id="f05d0-173">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="f05d0-174">Clique em **Membros** no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="f05d0-174">Click **Members** in the upper right.</span></span>
3. <span data-ttu-id="f05d0-175">Clique em **Adicionar membros**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-175">Click **Add members**.</span></span>
4. <span data-ttu-id="f05d0-176">Digite os nomes ou endereços de email dos usuários que você deseja convidar para o site e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-176">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="f05d0-177">Os usuários convidados não podem ser adicionados do site.</span><span class="sxs-lookup"><span data-stu-id="f05d0-177">Guest users can't be added from the site.</span></span> <span data-ttu-id="f05d0-178">Você precisa adicioná-los usando o Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="f05d0-178">You need to add them using Outlook on the web.</span></span>

<span data-ttu-id="f05d0-179">Para convidar convidados para um grupo</span><span class="sxs-lookup"><span data-stu-id="f05d0-179">To invite guests to a group</span></span>
1. <span data-ttu-id="f05d0-180">No Outlook na Web, em **grupos**, clique no grupo em que você deseja adicionar membros.</span><span class="sxs-lookup"><span data-stu-id="f05d0-180">In Outlook on the web, under **Groups**, click the group where you want to add members.</span></span>
2. <span data-ttu-id="f05d0-181">Abra o cartão de visita do grupo e, em **mais opções** (...), clique em **adicionar membros**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-181">Open the group contact card, and then, under **More options** (...), click **Add members**.</span></span>
3. <span data-ttu-id="f05d0-182">Digite os endereços de email dos convidados que você deseja convidar e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-182">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
4. <span data-ttu-id="f05d0-183">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="f05d0-183">Click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="f05d0-184">Confira também</span><span class="sxs-lookup"><span data-stu-id="f05d0-184">See Also</span></span>

[<span data-ttu-id="f05d0-185">Práticas recomendadas para compartilhar arquivos e pastas com usuários não autenticados</span><span class="sxs-lookup"><span data-stu-id="f05d0-185">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="f05d0-186">Limitar a exposição acidental dos arquivos ao compartilhar com convidados</span><span class="sxs-lookup"><span data-stu-id="f05d0-186">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="f05d0-187">Criar um ambiente seguro de compartilhamento para convidados</span><span class="sxs-lookup"><span data-stu-id="f05d0-187">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="f05d0-188">Crie uma extranet B2B com convidados gerenciados</span><span class="sxs-lookup"><span data-stu-id="f05d0-188">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

