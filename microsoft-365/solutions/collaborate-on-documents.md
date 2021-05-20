---
title: Colaborar com convidados em um documento
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
localization_priority: Normal
f1.keywords: NOCSH
recommendations: false
description: Neste artigo, você aprenderá a colaborar com convidados em um documento SharePoint e OneDrive.
ms.openlocfilehash: 338c7f32944bccb766ed923c12a9fceee4d81db8
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537830"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="166b2-103">Colaborar com convidados em um documento</span><span class="sxs-lookup"><span data-stu-id="166b2-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="166b2-104">Se você precisar colaborar com pessoas de fora da sua organização em documentos SharePoint ou OneDrive, envie um link de compartilhamento para o documento.</span><span class="sxs-lookup"><span data-stu-id="166b2-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing-link to the document.</span></span> <span data-ttu-id="166b2-105">Neste artigo, vamos passar pelas etapas de configuração Microsoft 365 necessárias para configurar links de compartilhamento para SharePoint e OneDrive para as necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="166b2-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing-links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="166b2-106">Demonstração de vídeo</span><span class="sxs-lookup"><span data-stu-id="166b2-106">Video demonstration</span></span>

<span data-ttu-id="166b2-107">Este vídeo mostra as etapas de configuração descritas neste documento.</span><span class="sxs-lookup"><span data-stu-id="166b2-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="166b2-108">Configurações de colaboração externa do Azure</span><span class="sxs-lookup"><span data-stu-id="166b2-108">Azure external collaboration settings</span></span>

<span data-ttu-id="166b2-109">Compartilhamento no Microsoft 365 é regido em seu nível mais alto pelas [Configurações de colaboração externa B2B no Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="166b2-109">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="166b2-110">Se o compartilhamento de convidados estiver desabilitado ou restrito no Azure AD, essa configuração substituirá as configurações de compartilhamento que você configurar no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="166b2-110">If guest-sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="166b2-111">Verifique as configurações de colaboração externa B2B para garantir que o compartilhamento com convidados não seja bloqueado.</span><span class="sxs-lookup"><span data-stu-id="166b2-111">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Captura de tela da página de configurações das Relações Organizacionais do Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="166b2-113">Para conjunto de configurações de colaboração externa</span><span class="sxs-lookup"><span data-stu-id="166b2-113">To set external collaboration settings</span></span>

1. <span data-ttu-id="166b2-114">Faça log no Azure Active Directory em[https://aad.portal.azure.com](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="166b2-114">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="166b2-115">No painel de navegação esquerdo, clique em **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="166b2-115">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="166b2-116">Clique em **Identidades externas**.</span><span class="sxs-lookup"><span data-stu-id="166b2-116">Click **External identities**.</span></span>
4. <span data-ttu-id="166b2-117">Na tela **Introdução**, no painel de navegação esquerdo, clique em **Configurações de colaboração externa**.</span><span class="sxs-lookup"><span data-stu-id="166b2-117">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="166b2-118">Certifique-se de que **Administradores e usuários na função de convidador podem convidar** e **Membros podem convidar** estão ambos no conjunto como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="166b2-118">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="166b2-119">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="166b2-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="166b2-120">Observe as configurações na seção **Restrições de colaboração**.</span><span class="sxs-lookup"><span data-stu-id="166b2-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="166b2-121">Certifique-se de que os domínios dos convidados com os quais deseja colaborar não estão bloqueados.</span><span class="sxs-lookup"><span data-stu-id="166b2-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="166b2-122">Se você trabalha com convidados de várias organizações, pode restringir sua capacidade de acessar os dados do diretório.</span><span class="sxs-lookup"><span data-stu-id="166b2-122">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="166b2-123">Isso os impedirá de ver quem mais é um convidado no diretório.</span><span class="sxs-lookup"><span data-stu-id="166b2-123">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="166b2-124">Para fazer isso, em **Restrições de acesso do usuário convidado**, selecione **Usuários convidados têm acesso limitado às propriedades e configurações de associação de objetos de diretório** ou **Acesso de usuário convidado é restrito a propriedades e associações de seus próprios objetos de diretório**.</span><span class="sxs-lookup"><span data-stu-id="166b2-124">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="166b2-125">SharePoint configurações de compartilhamento no nível da organização</span><span class="sxs-lookup"><span data-stu-id="166b2-125">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="166b2-126">Para que pessoas de fora da sua organização tenham acesso a um documento no SharePoint ou OneDrive, as configurações de compartilhamento do SharePoint e OneDrive no nível da organização devem permitir o compartilhamento com pessoas de fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="166b2-126">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="166b2-127">As configurações no nível da organização para SharePoint determinam as configurações que estarão disponíveis para sites SharePoint individuais.</span><span class="sxs-lookup"><span data-stu-id="166b2-127">The organization-level settings for SharePoint determine the settings that will be available for individual SharePoint sites.</span></span> <span data-ttu-id="166b2-128">Como configurações no nível da organização determinam quais configurações estão disponíveis para sites individuais, incluindo sites associados a equipes.</span><span class="sxs-lookup"><span data-stu-id="166b2-128">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="166b2-129">A configuração no nível da organização OneDrive determina o nível de compartilhamento que estará disponível nas bibliotecas OneDrive dos usuários.</span><span class="sxs-lookup"><span data-stu-id="166b2-129">The organization-level setting for OneDrive determines the level of sharing that will be available in users' OneDrive libraries.</span></span>

<span data-ttu-id="166b2-130">Para SharePoint e OneDrive, se você quiser permitir o compartilhamento de arquivos e pastas não autenticados, escolha **Qualquer Pessoa**.</span><span class="sxs-lookup"><span data-stu-id="166b2-130">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="166b2-131">Se você quiser garantir que pessoas de fora da sua organização tenham que se autenticar, escolha Convidados novos **e existentes.**</span><span class="sxs-lookup"><span data-stu-id="166b2-131">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="166b2-132">*Os* links de qualquer pessoa são a maneira mais fácil de compartilhar: pessoas de fora da sua organização podem abrir o link sem autenticação e podem passá-lo para outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="166b2-132">*Anyone* links is the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="166b2-133">Para SharePoint, escolha a configuração mais permissiva que será necessária por qualquer site em sua organização.</span><span class="sxs-lookup"><span data-stu-id="166b2-133">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Captura de tela das configurações de compartilhamento no nível da organização do Microsoft Office SharePoint Online](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="166b2-135">Para definir as configurações de compartilhamento no nível da organização do Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="166b2-135">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="166b2-136">No Centro de administração do Microsoft 365, no painel de navegação esquerdo, em **Centros de administração**, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="166b2-136">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="166b2-137">No centro SharePoint de administração, no painel de navegação esquerdo, em **Políticas,** clique em **Compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="166b2-137">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="166b2-138">Verifique se o compartilhamento externo para SharePoint ou OneDrive está definido como **Qualquer** pessoa ou **convidados novos e existentes.**</span><span class="sxs-lookup"><span data-stu-id="166b2-138">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="166b2-139">(Observe que a configuração OneDrive não pode ser mais permissiva do que a SharePoint configuração.)</span><span class="sxs-lookup"><span data-stu-id="166b2-139">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="166b2-140">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="166b2-140">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="166b2-141">Configurações de link padrão no nível da organização do Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="166b2-141">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="166b2-142">As configurações de link de arquivo e pasta padrão determinam a opção de link que será mostrada aos usuários por padrão quando eles compartilharem um arquivo ou pasta.</span><span class="sxs-lookup"><span data-stu-id="166b2-142">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="166b2-143">Os usuários podem alterar o tipo de link para uma das outras opções antes de compartilhar, se desejado.</span><span class="sxs-lookup"><span data-stu-id="166b2-143">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="166b2-144">Lembre-se de que essa configuração afeta SharePoint sites em sua organização, bem como OneDrive.</span><span class="sxs-lookup"><span data-stu-id="166b2-144">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="166b2-145">Escolha um link de qualquer um dos seguintes tipos selecionados por padrão quando os usuários compartilharem arquivos e pastas:</span><span class="sxs-lookup"><span data-stu-id="166b2-145">Choose a link from any of the following types which is then selected by default when users share files and folders:</span></span>

- <span data-ttu-id="166b2-146">**Qualquer pessoa com o link** - Escolha essa opção se você espera fazer um monte de compartilhamento de pastas e arquivos não autenticados.</span><span class="sxs-lookup"><span data-stu-id="166b2-146">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="166b2-147">Se você deseja permitir links *Qualquer Pessoa*, mas está preocupado com o compartilhamento não autenticado acidental, considere uma das outras opções como padrão.</span><span class="sxs-lookup"><span data-stu-id="166b2-147">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="166b2-148">Este tipo de link só estará disponível se você tiver ativado o compartilhamento **Qualquer Pessoa**.</span><span class="sxs-lookup"><span data-stu-id="166b2-148">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="166b2-149">**Somente pessoas em sua organização** - Escolher esta opção se você espera que a maior parte do compartilhamento de arquivos e pastas seja com pessoas de dentro de sua organização.</span><span class="sxs-lookup"><span data-stu-id="166b2-149">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="166b2-150">**Pessoas específicas** - Considerar esta opção se você pretende fazer muitos compartilhamentos de arquivos e pastas com convidados.</span><span class="sxs-lookup"><span data-stu-id="166b2-150">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="166b2-151">Esse tipo de link funciona com os convidados e exige que eles se autentiquem.</span><span class="sxs-lookup"><span data-stu-id="166b2-151">This type of link works with guests and requires them to authenticate.</span></span>
 
![Captura de tela das configurações de compartilhamento de pastas e arquivos no nível da organização do Microsoft Office SharePoint Online](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="166b2-153">Para definir as configurações SharePoint e OneDrive de link padrão no nível da organização</span><span class="sxs-lookup"><span data-stu-id="166b2-153">To set the SharePoint and OneDrive organization-level default link settings</span></span>

1. <span data-ttu-id="166b2-154">Navegue até a página Compartilhamento no Centro de administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="166b2-154">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="166b2-155">Em **Links de arquivos e pastas**, selecione o link de compartilhamento padrão que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="166b2-155">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="166b2-156">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="166b2-156">If you made changes, click **Save**.</span></span>

<span data-ttu-id="166b2-157">Para definir a permissão para o link de compartilhamento, em Escolha a permissão selecionada **por padrão para compartilhar links.**</span><span class="sxs-lookup"><span data-stu-id="166b2-157">To set the permission for the sharing link, under **Choose the permission that's selected by default for sharing links.**</span></span>

1. <span data-ttu-id="166b2-158">Selecione **Exibir** se você não quiser que usuários não autenticados façam alterações nos arquivos e pastas.</span><span class="sxs-lookup"><span data-stu-id="166b2-158">Select **View** if you do not want unauthenticated users to make changes to the files and folders.</span></span>
2. <span data-ttu-id="166b2-159">Selecione **Editar** se quiser permitir que usuários não autenticados façam alterações nos arquivos e pastas.</span><span class="sxs-lookup"><span data-stu-id="166b2-159">Select **Edit** if you want to allow unauthenticated users to make changes to the files and folders.</span></span>

<span data-ttu-id="166b2-160">Observe que as duas opções de pré-emissão acima podem ser aplicadas não apenas para convidados/usuários externos, mas também para usuários internos.</span><span class="sxs-lookup"><span data-stu-id="166b2-160">Note that the above two premission-options can be applied not only for guests/external users but also for internal users.</span></span> <span data-ttu-id="166b2-161">A opção de permissão escolhida é determinada por autodiscrição.</span><span class="sxs-lookup"><span data-stu-id="166b2-161">The permission-option you choose is determined by self-discretion.</span></span>

<span data-ttu-id="166b2-162">Para definir permissões para links que permitem o compartilhamento com qualquer pessoa</span><span class="sxs-lookup"><span data-stu-id="166b2-162">To set permissions for links that allow sharing with anyone</span></span>

1. <span data-ttu-id="166b2-163">No **sub-painel Esses links podem dar essas permissões:**</span><span class="sxs-lookup"><span data-stu-id="166b2-163">Under the **These links can give these permissions:** sub-pane,</span></span> 
    1. <span data-ttu-id="166b2-164">Na lista **lista** listada de arquivos,</span><span class="sxs-lookup"><span data-stu-id="166b2-164">From the **Files** drop-down list,</span></span> 
        - <span data-ttu-id="166b2-165">Selecione **Exibir e editar** se quiser permitir que usuários não autenticados façam alterações nos arquivos.</span><span class="sxs-lookup"><span data-stu-id="166b2-165">Select **View and edit** if you want to allow unauthenticated users to make changes to the files.</span></span>
        - <span data-ttu-id="166b2-166">Selecione **Exibir** se você não quiser que usuários não autenticados façam alterações nos arquivos.</span><span class="sxs-lookup"><span data-stu-id="166b2-166">Select **View** if you do not want unauthenticated users to make changes to the files.</span></span>
    2. <span data-ttu-id="166b2-167">Na **lista** de pastas listadas,</span><span class="sxs-lookup"><span data-stu-id="166b2-167">From the **Folders** drop-down list,</span></span>
        - <span data-ttu-id="166b2-168">Selecione **Exibir, editar e carregar** se quiser permitir que usuários não autenticados façam alterações nas pastas.</span><span class="sxs-lookup"><span data-stu-id="166b2-168">Select **View, edit, and upload** if you want to allow unauthenticated users to make changes to the folders.</span></span>
        - <span data-ttu-id="166b2-169">Selecione **Exibir** se você não quiser que usuários não autenticados façam alterações nas pastas.</span><span class="sxs-lookup"><span data-stu-id="166b2-169">Select **View** if you do not want unauthenticated users to make changes to the folders.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="166b2-170">Configurações de compartilhamento de nível de site do Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="166b2-170">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="166b2-171">Se você estiver compartilhando arquivos e pastas que estão em um site SharePoint, você também precisa verificar as configurações de compartilhamento no nível do site para esse site.</span><span class="sxs-lookup"><span data-stu-id="166b2-171">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![Captura de tela das configurações de compartilhamento externo do site do Microsoft Office SharePoint Online](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="166b2-173">Para conjunto de configurações de compartilhamento no nível do site</span><span class="sxs-lookup"><span data-stu-id="166b2-173">To set site-level sharing settings</span></span>

1. <span data-ttu-id="166b2-174">No Centro de administração do SharePoint, no painel de navegação esquerdo, expanda **Sites** e clique em **Sites ativos**.</span><span class="sxs-lookup"><span data-stu-id="166b2-174">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="166b2-175">Selecione o site no qual você deseja compartilhar arquivos e pastas com convidados.</span><span class="sxs-lookup"><span data-stu-id="166b2-175">Select the site on which you want to share files and folders with guests.</span></span>
3. <span data-ttu-id="166b2-176">Role diretamente pela linha (na qual o site selecionado está presente) e clique em qualquer lugar na **coluna Compartilhamento** externo.</span><span class="sxs-lookup"><span data-stu-id="166b2-176">Scroll right across the row (in which the selected site is present) and click anywhere in the **External sharing** column.</span></span>
4. <span data-ttu-id="166b2-177">Na página que aparece, clique na **guia Políticas.**</span><span class="sxs-lookup"><span data-stu-id="166b2-177">From the page that pops up, click **Policies** tab.</span></span>
5. <span data-ttu-id="166b2-178">No painel **compartilhamento** externo, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="166b2-178">Under the **External sharing** pane, click **Edit**.</span></span>
6. <span data-ttu-id="166b2-179">Certifique-se de que o compartilhamento esteja no conjunto como **Qualquer pessoa** ou **Convidados novos e existentes**.</span><span class="sxs-lookup"><span data-stu-id="166b2-179">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
7. <span data-ttu-id="166b2-180">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="166b2-180">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="166b2-181">Convidar usuários</span><span class="sxs-lookup"><span data-stu-id="166b2-181">Invite users</span></span>

<span data-ttu-id="166b2-182">As configurações de compartilhamento de convidados agora estão configuradas; para que os usuários agora possam compartilhar arquivos e pastas com pessoas fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="166b2-182">Guest-sharing settings are now configured; so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="166b2-183">Confira [Compartilhar OneDrive arquivos e pastas e](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) Compartilhar SharePoint arquivos ou pastas [para](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="166b2-183">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="166b2-184">Confira também</span><span class="sxs-lookup"><span data-stu-id="166b2-184">See also</span></span>

[<span data-ttu-id="166b2-185">Práticas recomendadas para compartilhar arquivos e pastas com usuários não autenticados</span><span class="sxs-lookup"><span data-stu-id="166b2-185">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="166b2-186">Limitar a exposição acidental dos arquivos ao compartilhar com convidados</span><span class="sxs-lookup"><span data-stu-id="166b2-186">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="166b2-187">Integração do Microsoft Office SharePoint Online e OneDrive com Microsoft Azure Active Directory B2B</span><span class="sxs-lookup"><span data-stu-id="166b2-187">SharePoint and OneDrive integration with Azure AD B2B</span></span>](/sharepoint/sharepoint-azureb2b-integration-preview)