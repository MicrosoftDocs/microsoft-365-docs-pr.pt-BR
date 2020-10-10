---
title: Colaborar com convidados em uma equipe
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
description: Saiba mais sobre as etapas de configuração do 365 da Microsoft necessárias para configurar uma equipe para colaboração com convidados no Microsoft Teams.
ms.openlocfilehash: 7a2259358d6976184d393980b2b7c0320c3bb171
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48409043"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="39c8d-103">Colaborar com convidados em uma equipe</span><span class="sxs-lookup"><span data-stu-id="39c8d-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="39c8d-104">Se você precisar colaborar com convidados entre documentos, tarefas e conversas, recomendamos o uso do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="39c8d-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="39c8d-105">O Microsoft Teams fornece todos os recursos de colaboração disponíveis no Office e no SharePoint com chat persistente e um conjunto personalizável e extensível de ferramentas de colaboração em uma experiência de usuário unificada.</span><span class="sxs-lookup"><span data-stu-id="39c8d-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="39c8d-106">Neste artigo, veremos as etapas de configuração do 365 da Microsoft necessárias para configurar uma equipe para colaboração com convidados.</span><span class="sxs-lookup"><span data-stu-id="39c8d-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="39c8d-107">Demonstração de vídeo</span><span class="sxs-lookup"><span data-stu-id="39c8d-107">Video demonstration</span></span>

<span data-ttu-id="39c8d-108">Este vídeo mostra as etapas de configuração descritas neste documento.</span><span class="sxs-lookup"><span data-stu-id="39c8d-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="39c8d-109">Configurações de relações organizacionais do Azure</span><span class="sxs-lookup"><span data-stu-id="39c8d-109">Azure Organizational relationships settings</span></span>

<span data-ttu-id="39c8d-110">O compartilhamento no Microsoft 365 é regido no seu nível mais alto pelas [configurações de relações organizacionais no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="39c8d-110">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="39c8d-111">Se o compartilhamento de convidados estiver desabilitado ou restrito no Azure AD, essa configuração substituirá as configurações de compartilhamento que você configurar no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="39c8d-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="39c8d-112">Verifique as configurações de relações organizacionais para garantir que o compartilhamento com convidados não seja bloqueado.</span><span class="sxs-lookup"><span data-stu-id="39c8d-112">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Captura de tela da página de configurações das Relações Organizacionais do Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="39c8d-114">Para definir as configurações de relação organizacional</span><span class="sxs-lookup"><span data-stu-id="39c8d-114">To set organizational relationship settings</span></span>

1. <span data-ttu-id="39c8d-115">Faça logon no Azure Active Directory em [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="39c8d-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="39c8d-116">No painel de navegação esquerdo, clique em **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="39c8d-117">Clique em **identidades externas**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-117">Click **External identities**.</span></span>
4. <span data-ttu-id="39c8d-118">Na tela **introdução** , no painel de navegação esquerdo, clique em **configurações de colaboração externa**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="39c8d-119">Certifique-se de que **Administradores e usuários na função de convite de convidado podem convidar** e **os membros podem convidar** estão definidos como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="39c8d-120">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="39c8d-121">Observe as configurações na seção **restrições de colaboração** .</span><span class="sxs-lookup"><span data-stu-id="39c8d-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="39c8d-122">Certifique-se de que os domínios dos convidados com os quais você deseja colaborar não estão bloqueados.</span><span class="sxs-lookup"><span data-stu-id="39c8d-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="39c8d-123">Se você trabalha com convidados de várias organizações, convém restringir sua capacidade de acessar dados de diretório.</span><span class="sxs-lookup"><span data-stu-id="39c8d-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="39c8d-124">Isso impedirá que você veja quem mais é um convidado no diretório.</span><span class="sxs-lookup"><span data-stu-id="39c8d-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="39c8d-125">Para fazer isso, em **restrições de acesso de usuário convidado**, selecione **os usuários convidados têm acesso limitado às propriedades e à associação de configurações de objetos de diretório** ou **o acesso de usuário convidado é restrito a propriedades e associações de seus próprios objetos de diretório**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="39c8d-126">Configurações de acesso de convidados do teams</span><span class="sxs-lookup"><span data-stu-id="39c8d-126">Teams guest access settings</span></span>

<span data-ttu-id="39c8d-127">O Microsoft Teams tem uma opção de ativar/desativar mestre para acesso de convidados e uma variedade de configurações disponíveis para controlar o que os convidados podem fazer em uma equipe.</span><span class="sxs-lookup"><span data-stu-id="39c8d-127">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="39c8d-128">A opção mestre **permite que o acesso de convidados no Microsoft Teams** seja **ativado** para que o acesso de convidados funcione no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="39c8d-128">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="39c8d-129">Verifique se o acesso de convidados está habilitado no Teams e faça qualquer ajuste nas configurações de convidado com base nas suas necessidades de negócios.</span><span class="sxs-lookup"><span data-stu-id="39c8d-129">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="39c8d-130">Tenha em mente que essas configurações afetam todas as equipes.</span><span class="sxs-lookup"><span data-stu-id="39c8d-130">Keep in mind that these settings affect all teams.</span></span>

![Captura de tela de alternância de acesso de convidados](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="39c8d-132">Para definir as configurações de acesso de convidado do Teams</span><span class="sxs-lookup"><span data-stu-id="39c8d-132">To set Teams guest access settings</span></span>

1. <span data-ttu-id="39c8d-133">Entre no Centro de administração do Microsoft 365 em [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="39c8d-133">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="39c8d-134">No painel de navegação esquerdo, clique em **Mostrar tudo**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-134">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="39c8d-135">Em **Centros de administração**, clique em **Teams**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-135">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="39c8d-136">No centro de administração do Microsoft Teams, no painel de navegação esquerdo, expanda **configurações de toda a organização** e clique em **acesso de convidado**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-136">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="39c8d-137">Certifique-se de que **Permitir acesso de convidado no Teams** esteja definido como **Ativado**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-137">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="39c8d-138">Faça as alterações desejadas nas configurações de convidado adicionais e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-138">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="39c8d-139">Pode levar até vinte e quatro horas para que as configurações de convidados do teams se tornem ativas depois de ativá-la.</span><span class="sxs-lookup"><span data-stu-id="39c8d-139">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="39c8d-140">Configurações de convidado de grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="39c8d-140">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="39c8d-141">O Teams usa os grupos do Microsoft 365 para associação da equipe.</span><span class="sxs-lookup"><span data-stu-id="39c8d-141">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="39c8d-142">As configurações de convidado do Microsoft 365 groups devem ser ativadas para que o acesso de convidados no Teams funcione.</span><span class="sxs-lookup"><span data-stu-id="39c8d-142">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Captura de tela das configurações de convidado dos Grupos do Microsoft 365 no Centro de administração do Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="39c8d-144">Para definir as configurações de convidados de grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="39c8d-144">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="39c8d-145">No centro de administração do Microsoft 365, no painel de navegação esquerdo, expanda **configurações**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-145">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="39c8d-146">Clique em **configurações da organização**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-146">Click **Org settings**.</span></span>
3. <span data-ttu-id="39c8d-147">Na lista, clique em **Microsoft 365 grupos**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-147">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="39c8d-148">Certifique-se de que os **proprietários de grupo permitem que as pessoas de fora da sua organização para o Microsoft 365 grupos de** convidados e **permitir que os membros do grupo convidado acessem o conteúdo do grupo de acesso** sejam verificados.</span><span class="sxs-lookup"><span data-stu-id="39c8d-148">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="39c8d-149">Se você tiver feito alterações, clique em **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-149">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="39c8d-150">Configurações de compartilhamento de nível da organização do SharePoint</span><span class="sxs-lookup"><span data-stu-id="39c8d-150">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="39c8d-151">O conteúdo de equipes, como arquivos, pastas e listas, é armazenado no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="39c8d-151">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="39c8d-152">Para que os convidados tenham acesso a esses itens no Teams, as configurações de compartilhamento no nível da organização do SharePoint devem permitir o compartilhamento com convidados.</span><span class="sxs-lookup"><span data-stu-id="39c8d-152">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="39c8d-153">As configurações de nível de organização determinam quais configurações estão disponíveis para sites individuais, incluindo sites associados ao Teams.</span><span class="sxs-lookup"><span data-stu-id="39c8d-153">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="39c8d-154">As configurações do site não podem ser mais permissivas do que as configurações no nível da organização.</span><span class="sxs-lookup"><span data-stu-id="39c8d-154">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="39c8d-155">Se você quiser permitir o compartilhamento de arquivos e pastas com pessoas não autenticadas, escolha **qualquer pessoa**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-155">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="39c8d-156">Se você quiser garantir que todos os convidados devem se autenticar, escolha **novos e existentes convidados**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-156">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="39c8d-157">Escolha a configuração mais permissiva que será necessária para qualquer site em sua organização.</span><span class="sxs-lookup"><span data-stu-id="39c8d-157">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Captura de tela das configurações de compartilhamento no nível da organização do SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="39c8d-159">Para definir as configurações de compartilhamento no nível da organização do SharePoint</span><span class="sxs-lookup"><span data-stu-id="39c8d-159">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="39c8d-160">No centro de administração do Microsoft 365, no painel de navegação esquerdo, em **centros de administração**, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-160">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="39c8d-161">No centro de administração do SharePoint, no painel de navegação esquerdo, expanda **políticas** e clique em **compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-161">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="39c8d-162">Verifique se o compartilhamento externo do SharePoint está definido como **qualquer pessoa** ou **novo convidado existente**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-162">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="39c8d-163">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-163">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="39c8d-164">Configurações de link padrão no nível da organização do SharePoint</span><span class="sxs-lookup"><span data-stu-id="39c8d-164">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="39c8d-165">As configurações padrão de link de arquivo e pasta determinam a opção de link que será mostrada para os usuários por padrão ao compartilhar um arquivo ou uma pasta.</span><span class="sxs-lookup"><span data-stu-id="39c8d-165">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="39c8d-166">Os usuários podem alterar o tipo de link para uma das outras opções antes de compartilhar, se desejado.</span><span class="sxs-lookup"><span data-stu-id="39c8d-166">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="39c8d-167">Tenha em mente que essa configuração afeta todas as equipes e sites do SharePoint em sua organização.</span><span class="sxs-lookup"><span data-stu-id="39c8d-167">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="39c8d-168">Escolha qualquer um dos seguintes tipos de link que serão selecionados por padrão quando os usuários compartilharem arquivos e pastas:</span><span class="sxs-lookup"><span data-stu-id="39c8d-168">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="39c8d-169">**Qualquer pessoa com o link** -escolha essa opção se você quiser fazer muito do compartilhamento não autenticado de arquivos e pastas.</span><span class="sxs-lookup"><span data-stu-id="39c8d-169">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="39c8d-170">Se você quiser permitir links de *qualquer pessoa* , mas estiver preocupado com o compartilhamento acidental não autenticado, considere uma das outras opções como padrão.</span><span class="sxs-lookup"><span data-stu-id="39c8d-170">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="39c8d-171">Esse tipo de link só estará disponível se você tiver habilitado o compartilhamento de **qualquer pessoa** .</span><span class="sxs-lookup"><span data-stu-id="39c8d-171">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="39c8d-172">**Somente as pessoas da sua organização** -escolha esta opção se você espera que a maioria dos compartilhamento de arquivos e pastas seja com pessoas dentro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="39c8d-172">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="39c8d-173">**Pessoas específicas** -considere essa opção se você espera que um grande volume de compartilhamento de arquivos e pastas com convidados.</span><span class="sxs-lookup"><span data-stu-id="39c8d-173">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="39c8d-174">Esse tipo de link funciona com convidados e exige a autenticação.</span><span class="sxs-lookup"><span data-stu-id="39c8d-174">This type of link works with guests and requires them to authenticate.</span></span>
 
![Captura de tela das configurações de compartilhamento de pastas e arquivos no nível da organização do SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="39c8d-176">Para definir as configurações de link padrão no nível da organização do SharePoint</span><span class="sxs-lookup"><span data-stu-id="39c8d-176">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="39c8d-177">Navegue até a página de compartilhamento no centro de administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="39c8d-177">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="39c8d-178">Em **links de arquivo e pasta**, selecione o link de compartilhamento padrão que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="39c8d-178">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="39c8d-179">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-179">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="39c8d-180">Criar uma equipe</span><span class="sxs-lookup"><span data-stu-id="39c8d-180">Create a team</span></span>

<span data-ttu-id="39c8d-181">A próxima etapa é criar a equipe que você planeja usar para colaborar com convidados.</span><span class="sxs-lookup"><span data-stu-id="39c8d-181">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="39c8d-182">Para criar uma equipe</span><span class="sxs-lookup"><span data-stu-id="39c8d-182">To create a team</span></span>
1. <span data-ttu-id="39c8d-183">No Teams, na guia **Teams** , clique em **ingressar ou criar uma equipe** na parte inferior do painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="39c8d-183">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="39c8d-184">Clique em **criar uma equipe**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-184">Click **Create a team**.</span></span>
3. <span data-ttu-id="39c8d-185">Clique em **criar uma equipe do zero**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-185">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="39c8d-186">Escolha **privado** ou **público**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-186">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="39c8d-187">Digite um nome e uma descrição para a equipe e, em seguida, clique em **criar**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-187">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="39c8d-188">Clique em **ignorar**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-188">Click **Skip**.</span></span>

<span data-ttu-id="39c8d-189">Vamos convidar os usuários mais tarde.</span><span class="sxs-lookup"><span data-stu-id="39c8d-189">We'll invite users later.</span></span> <span data-ttu-id="39c8d-190">Em seguida, é importante verificar as configurações de compartilhamento no nível do site do SharePoint associado à equipe.</span><span class="sxs-lookup"><span data-stu-id="39c8d-190">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="39c8d-191">Configurações de compartilhamento no nível do site do SharePoint</span><span class="sxs-lookup"><span data-stu-id="39c8d-191">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="39c8d-192">Verifique as configurações de compartilhamento no nível do site para garantir que elas permitam o tipo de acesso que você deseja para essa equipe.</span><span class="sxs-lookup"><span data-stu-id="39c8d-192">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="39c8d-193">Por exemplo, se você definir as configurações de nível de organização como **qualquer pessoa**, mas quiser que todos os convidados autentiquem essa equipe, verifique se as configurações de compartilhamento no nível do site estão definidas para **convidados novos e existentes**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-193">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![Captura de tela das configurações de compartilhamento de site externo do SharePoint](../media/sharepoint-site-external-sharing-settings.png)


<span data-ttu-id="39c8d-195">Para definir configurações de compartilhamento no nível do site</span><span class="sxs-lookup"><span data-stu-id="39c8d-195">To set site-level sharing settings</span></span>
1. <span data-ttu-id="39c8d-196">No centro de administração do SharePoint, no painel de navegação esquerdo, expanda **sites** e clique em **sites ativos**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-196">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="39c8d-197">Selecione o site da equipe que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="39c8d-197">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="39c8d-198">Clique em... e escolha **compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-198">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="39c8d-199">Verifique se o compartilhamento está definido como **qualquer pessoa** ou **convidado novo e existente**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-199">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="39c8d-200">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-200">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="39c8d-201">Convidar usuários</span><span class="sxs-lookup"><span data-stu-id="39c8d-201">Invite users</span></span>

<span data-ttu-id="39c8d-202">As configurações de compartilhamento de convidados agora estão configuradas para que você possa começar a adicionar usuários internos e convidados à sua equipe.</span><span class="sxs-lookup"><span data-stu-id="39c8d-202">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="39c8d-203">Para convidar usuários internos para uma equipe</span><span class="sxs-lookup"><span data-stu-id="39c8d-203">To invite internal users to a team</span></span>
1. <span data-ttu-id="39c8d-204">Na equipe, clique em **mais opções** ( **\*\*\*** ) e, em seguida, clique em **Adicionar membro**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-204">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="39c8d-205">Digite o nome da pessoa que você deseja convidar.</span><span class="sxs-lookup"><span data-stu-id="39c8d-205">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="39c8d-206">Clique em **Adicionar**e, em seguida, clique em **fechar**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-206">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="39c8d-207">Para convidar convidados para uma equipe</span><span class="sxs-lookup"><span data-stu-id="39c8d-207">To invite guests to a team</span></span>
1. <span data-ttu-id="39c8d-208">Na equipe, clique em **mais opções** ( **\*\*\*** ) e, em seguida, clique em **Adicionar membro**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-208">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="39c8d-209">Digite o endereço de email do convidado que você deseja convidar.</span><span class="sxs-lookup"><span data-stu-id="39c8d-209">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="39c8d-210">Clique em **Editar informações de convidado**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-210">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="39c8d-211">Digite o nome completo do convidado e clique na marca de seleção.</span><span class="sxs-lookup"><span data-stu-id="39c8d-211">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="39c8d-212">Clique em **Adicionar**e, em seguida, clique em **fechar**.</span><span class="sxs-lookup"><span data-stu-id="39c8d-212">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="39c8d-213">Confira também</span><span class="sxs-lookup"><span data-stu-id="39c8d-213">See also</span></span>

[<span data-ttu-id="39c8d-214">Práticas recomendadas para compartilhar arquivos e pastas com usuários não autenticados</span><span class="sxs-lookup"><span data-stu-id="39c8d-214">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="39c8d-215">Limitar a exposição acidental dos arquivos ao compartilhar com convidados</span><span class="sxs-lookup"><span data-stu-id="39c8d-215">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="39c8d-216">Criar um ambiente de compartilhamento de convidados seguro</span><span class="sxs-lookup"><span data-stu-id="39c8d-216">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="39c8d-217">Crie uma extranet B2B com convidados gerenciados</span><span class="sxs-lookup"><span data-stu-id="39c8d-217">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="39c8d-218">Integração do SharePoint e do OneDrive com o B2B do Azure AD</span><span class="sxs-lookup"><span data-stu-id="39c8d-218">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
