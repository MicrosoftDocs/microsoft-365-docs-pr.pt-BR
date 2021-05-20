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
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
recommendations: false
description: Saiba mais sobre as etapas de configuração do Microsoft 365 necessárias para configurar uma equipe para tarefas, conversas e colaboração de documentação com convidados no Teams.
ms.openlocfilehash: c17732705c1d88ff70e56f5d26d9e268e3ff7c19
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539258"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="25730-103">Colaborar com convidados em uma equipe</span><span class="sxs-lookup"><span data-stu-id="25730-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="25730-104">Se você precisar colaborar com convidados em documentos, tarefas e conversas, recomendamos o uso do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="25730-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="25730-105">O Teams fornece todos os recursos de colaboração disponíveis no Office e no Microsoft Office SharePoint Online com chat persistente e um conjunto personalizável e extensível de ferramentas de colaboração em uma experiência de usuário unificada.</span><span class="sxs-lookup"><span data-stu-id="25730-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="25730-106">Neste artigo, vamos percorrer as etapas de configuração do Microsoft 365 necessárias para configurar uma equipe para colaboração com convidados.</span><span class="sxs-lookup"><span data-stu-id="25730-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span> <span data-ttu-id="25730-107">Depois de configurar o acesso de convidado, você pode convidar pessoas para equipes seguindo as etapas em [Adicionar convidados a uma equipe no Teams](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f).</span><span class="sxs-lookup"><span data-stu-id="25730-107">Once you have configured guest access, you can invite guests to teams by following the steps in [Add guests to a team in Teams](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="25730-108">Demonstração de vídeo</span><span class="sxs-lookup"><span data-stu-id="25730-108">Video demonstration</span></span>

<span data-ttu-id="25730-109">Este vídeo mostra as etapas de configuração descritas neste documento.</span><span class="sxs-lookup"><span data-stu-id="25730-109">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="25730-110">Configurações de colaboração externa do Azure</span><span class="sxs-lookup"><span data-stu-id="25730-110">Azure External collaboration settings</span></span>

<span data-ttu-id="25730-111">Compartilhamento no Microsoft 365 é regido em seu nível mais alto pelas [Configurações de colaboração externa B2B no Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="25730-111">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="25730-112">Se o compartilhamento de convidados estiver desabilitado ou restrito no Azure AD, essa configuração substituirá todas as configurações de compartilhamento que você definir no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="25730-112">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="25730-113">Verifique as configurações de colaboração externa B2B para garantir que o compartilhamento com convidados não seja bloqueado.</span><span class="sxs-lookup"><span data-stu-id="25730-113">Check the B2B external collaboration settings settings to ensure that sharing with guests is not blocked.</span></span>

![Captura de tela da página de configurações das Relações Organizacionais do Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="25730-115">Para conjunto de configurações de colaboração externa</span><span class="sxs-lookup"><span data-stu-id="25730-115">To set external collaboration settings</span></span>

1. <span data-ttu-id="25730-116">Faça log no Azure Active Directory em[https://aad.portal.azure.com](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="25730-116">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="25730-117">No painel de navegação esquerdo, clique em **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="25730-117">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="25730-118">Clique em **Identidades externas**.</span><span class="sxs-lookup"><span data-stu-id="25730-118">Click **External identities**.</span></span>
4. <span data-ttu-id="25730-119">Na tela **Introdução**, no painel de navegação esquerdo, clique em **Configurações de colaboração externa**.</span><span class="sxs-lookup"><span data-stu-id="25730-119">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="25730-120">Certifique-se de que **Administradores e usuários na função de convidador podem convidar** e **Membros podem convidar** estão ambos no conjunto como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="25730-120">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="25730-121">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="25730-121">If you made changes, click **Save**.</span></span>

<span data-ttu-id="25730-122">Observe as configurações na seção **Restrições de colaboração**.</span><span class="sxs-lookup"><span data-stu-id="25730-122">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="25730-123">Certifique-se de que os domínios dos convidados com os quais deseja colaborar não estão bloqueados.</span><span class="sxs-lookup"><span data-stu-id="25730-123">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="25730-124">Se você trabalha com convidados de várias organizações, pode restringir sua capacidade de acessar os dados do diretório.</span><span class="sxs-lookup"><span data-stu-id="25730-124">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="25730-125">Isso os impedirá de ver quem mais é um convidado no diretório.</span><span class="sxs-lookup"><span data-stu-id="25730-125">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="25730-126">Para fazer isso, em **Restrições de acesso do usuário convidado**, selecione **Usuários convidados têm acesso limitado às propriedades e configurações de associação de objetos de diretório** ou **Acesso de usuário convidado é restrito a propriedades e associações de seus próprios objetos de diretório**.</span><span class="sxs-lookup"><span data-stu-id="25730-126">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="25730-127">Configurações de acesso de convidado das equipes</span><span class="sxs-lookup"><span data-stu-id="25730-127">Teams guest access settings</span></span>

<span data-ttu-id="25730-128">O Teams tem um interruptor mestre liga/desliga para acesso dos convidados e uma variedade de configurações disponíveis para controlar o que os convidados podem fazer em uma equipe.</span><span class="sxs-lookup"><span data-stu-id="25730-128">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="25730-129">O switch mestre, **Permitir acesso de convidado no Teams** deve ser **No** para o acesso do convidado funcionar no Teams.</span><span class="sxs-lookup"><span data-stu-id="25730-129">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="25730-p107">Verifique se o acesso de convidado está habilitado no Teams e faça qualquer ajuste nas configurações de convidado com base em suas necessidades de negócios. Lembre-se de que essas configurações afetam todas as equipes.</span><span class="sxs-lookup"><span data-stu-id="25730-p107">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs. Keep in mind that these settings affect all teams.</span></span>

![Captura de tela de alternância de acesso de convidados](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="25730-133">Para definir as configurações de acesso de convidado do Teams</span><span class="sxs-lookup"><span data-stu-id="25730-133">To set Teams guest access settings</span></span>

1. <span data-ttu-id="25730-134">Entre no Centro de administração do Microsoft 365 em [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="25730-134">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="25730-135">No painel de navegação esquerdo, clique em **Mostrar todos**.</span><span class="sxs-lookup"><span data-stu-id="25730-135">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="25730-136">Em **Centros de administração**, clique em **Teams**.</span><span class="sxs-lookup"><span data-stu-id="25730-136">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="25730-137">No Centro de administração de equipes, no painel de navegação esquerdo, expanda **Configurações em toda a organização** e clique em **Acesso de convidado**.</span><span class="sxs-lookup"><span data-stu-id="25730-137">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="25730-138">Certifique-se de que **Permitir acesso de convidado no Teams** esteja definido como **Ativado**.</span><span class="sxs-lookup"><span data-stu-id="25730-138">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="25730-139">Faça as alterações desejadas nas configurações de convidado adicionais e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="25730-139">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

<span data-ttu-id="25730-140">Depois que o acesso de convidado do Teams está ativado, você pode opcionalmente controlar o acesso de convidado a equipes individuais e seus sites do Microsoft Office SharePoint Online associados usando rótulos de sensibilidade.</span><span class="sxs-lookup"><span data-stu-id="25730-140">Once Teams guest access is turned on, you can optionally control guest access to individual teams and their associated SharePoint sites using sensitivity labels.</span></span> <span data-ttu-id="25730-141">Para mais informações, veja [Use rótulos de confidencialidade para proteger o conteúdo do Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md).</span><span class="sxs-lookup"><span data-stu-id="25730-141">For more information, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

> [!NOTE]
> <span data-ttu-id="25730-142">Pode levar até vinte e quatro horas para que as configurações de convidados do Teams se tornem ativas depois de ativadas.</span><span class="sxs-lookup"><span data-stu-id="25730-142">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="25730-143">Configurações de convidado do Microsoft 365 Groups</span><span class="sxs-lookup"><span data-stu-id="25730-143">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="25730-p109">O Teams utiliza os Grupos Microsoft 365 para a associação à equipe. As configurações dos Grupos Microsoft 365 devem ser ativadas para que o acesso de convidados em Equipes trabalhe.</span><span class="sxs-lookup"><span data-stu-id="25730-p109">Teams uses Microsoft 365 Groups for team membership. The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Captura de tela das configurações de convidado dos Grupos do Microsoft 365 no Centro de administração do Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="25730-147">Para definir as configurações de convidado do Grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="25730-147">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="25730-148">No Centro de administração do Microsoft 365, no painel de navegação esquerdo, expanda **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="25730-148">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="25730-149">Clique em **Configurações da organização**.</span><span class="sxs-lookup"><span data-stu-id="25730-149">Click **Org settings**.</span></span>
3. <span data-ttu-id="25730-150">Na lista, clique em **Grupos do Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="25730-150">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="25730-151">Certifique-se de que as caixas de seleção **Permitir que proprietários de grupos adicionem pessoas fora de sua organização aos Grupos do Microsoft 365 como convidados** e **Permitir que membros de grupos convidados acessem o conteúdo do grupo** estejam marcadas.</span><span class="sxs-lookup"><span data-stu-id="25730-151">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="25730-152">Se você fez alterações, clique em **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="25730-152">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="25730-153">Configurações de compartilhamento de nível de organização do Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="25730-153">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="25730-154">Conteúdo do Teams, como arquivos, pastas e listas, é armazenado no Microsoft Office SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="25730-154">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="25730-155">Na ordem para os convidados tenham acesso a esses itens no Teams, as configurações de compartilhamento no nível da organização do Microsoft Office SharePoint Online devem permitir o compartilhamento com convidados.</span><span class="sxs-lookup"><span data-stu-id="25730-155">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="25730-156">As configurações no nível da organização determinam quais configurações estão disponíveis para sites individuais, incluindo sites associados a equipes.</span><span class="sxs-lookup"><span data-stu-id="25730-156">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="25730-157">Como configurações no nível da organização determinam quais configurações estão disponíveis para sites individuais, incluindo sites associados a equipes.</span><span class="sxs-lookup"><span data-stu-id="25730-157">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="25730-158">Se você deseja permitir o compartilhamento de arquivos e pastas com pessoas não autenticadas, escolha **Qualquer pessoa**.</span><span class="sxs-lookup"><span data-stu-id="25730-158">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="25730-159">Se você quiser garantir que todos os convidados precisem ser autenticados, escolha **Convidados novos e existentes**.</span><span class="sxs-lookup"><span data-stu-id="25730-159">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="25730-160">Escolher a configuração mais permissiva que será necessária para qualquer site em sua organização.</span><span class="sxs-lookup"><span data-stu-id="25730-160">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Captura de tela das configurações de compartilhamento no nível da organização do Microsoft Office SharePoint Online](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="25730-162">Para definir as configurações de compartilhamento no nível da organização do Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="25730-162">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="25730-163">No Centro de administração do Microsoft 365, no painel de navegação esquerdo, em **Centros de administração**, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="25730-163">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="25730-164">No Centro de administração do SharePoint, no painel de navegação esquerdo, expanda **Políticas** e clique em **Compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="25730-164">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="25730-165">Certifique-se de que o compartilhamento externo para o Microsoft Office SharePoint Online esteja definido como **Qualquer Pessoa** ou **Convidados novos e existentes**.</span><span class="sxs-lookup"><span data-stu-id="25730-165">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="25730-166">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="25730-166">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="25730-167">Configurações de link padrão no nível da organização do Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="25730-167">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="25730-168">As configurações de link de arquivo e pasta padrão determinam a opção de link que será mostrada aos usuários por padrão quando eles compartilharem um arquivo ou pasta.</span><span class="sxs-lookup"><span data-stu-id="25730-168">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="25730-169">Os usuários podem alterar o tipo de link para uma das outras opções antes de compartilhar, se desejado.</span><span class="sxs-lookup"><span data-stu-id="25730-169">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="25730-170">Lembre-se de que essa configuração afeta todas as equipes e sites do Microsoft Office SharePoint Online em sua organização.</span><span class="sxs-lookup"><span data-stu-id="25730-170">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="25730-171">Escolher qualquer um dos seguintes tipos de link, que será selecionado por padrão quando os usuários compartilharem arquivos e pastas:</span><span class="sxs-lookup"><span data-stu-id="25730-171">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="25730-172">**Qualquer pessoa com o link** - Escolher esta opção se você espera fazer muitos compartilhamentos não autenticados de arquivos e pastas.</span><span class="sxs-lookup"><span data-stu-id="25730-172">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="25730-173">Se você deseja permitir links *Qualquer Pessoa*, mas está preocupado com o compartilhamento não autenticado acidental, considere uma das outras opções como padrão.</span><span class="sxs-lookup"><span data-stu-id="25730-173">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="25730-174">Este tipo de link só estará disponível se você tiver ativado o compartilhamento **Qualquer Pessoa**.</span><span class="sxs-lookup"><span data-stu-id="25730-174">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="25730-175">**Somente pessoas em sua organização** - Escolher esta opção se você espera que a maior parte do compartilhamento de arquivos e pastas seja com pessoas de dentro de sua organização.</span><span class="sxs-lookup"><span data-stu-id="25730-175">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="25730-176">**Pessoas específicas** - Considerar esta opção se você pretende fazer muitos compartilhamentos de arquivos e pastas com convidados.</span><span class="sxs-lookup"><span data-stu-id="25730-176">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="25730-177">Esse tipo de link funciona com os convidados e exige que eles se autentiquem.</span><span class="sxs-lookup"><span data-stu-id="25730-177">This type of link works with guests and requires them to authenticate.</span></span>
 
![Captura de tela das configurações de compartilhamento de pastas e arquivos no nível da organização do Microsoft Office SharePoint Online](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="25730-179">Para conjunto de configurações de link padrão no nível da organização do Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="25730-179">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="25730-180">Navegue até a página Compartilhamento no Centro de administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="25730-180">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="25730-181">Em **Links de arquivos e pastas**, selecione o link de compartilhamento padrão que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="25730-181">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="25730-182">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="25730-182">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="25730-183">Criar uma equipe</span><span class="sxs-lookup"><span data-stu-id="25730-183">Create a team</span></span>

<span data-ttu-id="25730-184">A próxima etapa é criar a equipe que você planeja usar para colaborar com os convidados.</span><span class="sxs-lookup"><span data-stu-id="25730-184">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="25730-185">Para criar uma equipe</span><span class="sxs-lookup"><span data-stu-id="25730-185">To create a team</span></span>
1. <span data-ttu-id="25730-186">No Teams, na guia **Teams**, clique em **Participar ou criar uma equipe** na parte inferior do painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="25730-186">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="25730-187">Clique em **Criar uma equipe**.</span><span class="sxs-lookup"><span data-stu-id="25730-187">Click **Create a team**.</span></span>
3. <span data-ttu-id="25730-188">Clique **Build uma equipe do zero**.</span><span class="sxs-lookup"><span data-stu-id="25730-188">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="25730-189">Escolher **Privado** ou **Público**.</span><span class="sxs-lookup"><span data-stu-id="25730-189">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="25730-190">Digite um nome e uma descrição para a equipe e clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="25730-190">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="25730-191">Clique **Ignorar**.</span><span class="sxs-lookup"><span data-stu-id="25730-191">Click **Skip**.</span></span>

<span data-ttu-id="25730-p116">Convidaremos os usuários mais tarde. Em seguida, é importante verificar as configurações de compartilhamento no nível do site para o site do Microsoft Office SharePoint Online que está associado à equipe.</span><span class="sxs-lookup"><span data-stu-id="25730-p116">We'll invite users later. Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="25730-194">Configurações de compartilhamento de nível de site do Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="25730-194">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="25730-195">Verificar as configurações de compartilhamento no nível do site para certificar-se de que permitem o tipo de acesso que você deseja para esta equipe.</span><span class="sxs-lookup"><span data-stu-id="25730-195">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="25730-196">Por exemplo, se você definir as configurações no nível da organização como **Qualquer Pessoa**, mas quiser que todos os convidados se autentiquem para esta equipe, certifique-se de que as configurações de compartilhamento no nível do site estejam definidas como **Convidados novos e existentes**.</span><span class="sxs-lookup"><span data-stu-id="25730-196">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![Captura de tela das configurações de compartilhamento externo do site do Microsoft Office SharePoint Online](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="25730-198">Para conjunto de configurações de compartilhamento no nível do site</span><span class="sxs-lookup"><span data-stu-id="25730-198">To set site-level sharing settings</span></span>
1. <span data-ttu-id="25730-199">No Centro de administração do SharePoint, no painel de navegação esquerdo, expanda **Sites** e clique em **Sites ativos**.</span><span class="sxs-lookup"><span data-stu-id="25730-199">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="25730-200">Selecione o site para a equipe que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="25730-200">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="25730-201">Clique em ... e escolha **Compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="25730-201">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="25730-202">Certifique-se de que o compartilhamento esteja no conjunto como **Qualquer pessoa** ou **Convidados novos e existentes**.</span><span class="sxs-lookup"><span data-stu-id="25730-202">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="25730-203">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="25730-203">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="25730-204">Convidar usuários</span><span class="sxs-lookup"><span data-stu-id="25730-204">Invite users</span></span>

<span data-ttu-id="25730-205">Configurações de compartilhamento de convidados agora estão definidas, para que você possa começar a adicionar usuários internos e convidados à sua equipe.</span><span class="sxs-lookup"><span data-stu-id="25730-205">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="25730-206">Para convidar usuários internos para uma equipe</span><span class="sxs-lookup"><span data-stu-id="25730-206">To invite internal users to a team</span></span>
1. <span data-ttu-id="25730-207">Na equipe, clique em **Mais opções** (**\*\*\***) e, em seguida, clique em **Adicionar membro**.</span><span class="sxs-lookup"><span data-stu-id="25730-207">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="25730-208">Toque no nome da pessoa que você quer convidar.</span><span class="sxs-lookup"><span data-stu-id="25730-208">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="25730-209">Clique em **Adicionar** e, em seguida, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="25730-209">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="25730-210">Para convidar pessoas para uma equipe</span><span class="sxs-lookup"><span data-stu-id="25730-210">To invite guests to a team</span></span>
1. <span data-ttu-id="25730-211">Na equipe, clique em **Mais opções** (**\*\*\***) e, em seguida, clique em **Adicionar membro**.</span><span class="sxs-lookup"><span data-stu-id="25730-211">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="25730-212">Digite o endereço de email do convidado que deseja convidar.</span><span class="sxs-lookup"><span data-stu-id="25730-212">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="25730-213">Clique em **Editar informações do convidado**.</span><span class="sxs-lookup"><span data-stu-id="25730-213">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="25730-214">Digite o nome completo do convidadi e clique na marca de verificação.</span><span class="sxs-lookup"><span data-stu-id="25730-214">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="25730-215">Clique em **Adicionar** e, em seguida, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="25730-215">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="25730-216">Confira também</span><span class="sxs-lookup"><span data-stu-id="25730-216">See also</span></span>

[<span data-ttu-id="25730-217">Práticas recomendadas para compartilhar arquivos e pastas com usuários não autenticados</span><span class="sxs-lookup"><span data-stu-id="25730-217">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="25730-218">Limitar a exposição acidental dos arquivos ao compartilhar com convidados</span><span class="sxs-lookup"><span data-stu-id="25730-218">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="25730-219">Criar um ambiente de compartilhamento de convidados seguro</span><span class="sxs-lookup"><span data-stu-id="25730-219">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="25730-220">Crie uma extranet B2B com convidados gerenciados</span><span class="sxs-lookup"><span data-stu-id="25730-220">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="25730-221">Integração do Microsoft Office SharePoint Online e OneDrive com Microsoft Azure Active Directory B2B</span><span class="sxs-lookup"><span data-stu-id="25730-221">SharePoint and OneDrive integration with Azure AD B2B</span></span>](/sharepoint/sharepoint-azureb2b-integration-preview)

[<span data-ttu-id="25730-222">Opções de compartilhamento ficam esmaecidas ao compartilhar do Microsoft Office SharePoint Online ou OneDrive</span><span class="sxs-lookup"><span data-stu-id="25730-222">Sharing options are greyed out when sharing from SharePoint or OneDrive</span></span>](/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)