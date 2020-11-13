---
title: Colaborar com convidados em um documento
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
description: Neste artigo, você aprenderá como colaborar com convidados em um documento no SharePoint e no OneDrive.
ms.openlocfilehash: e3492732756aecb176eb21f0bdfd0d394013975e
ms.sourcegitcommit: 8a726ed7ec19a8728c079780fa4d343a5f759fbb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030000"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="34d91-103">Colaborar com convidados em um documento</span><span class="sxs-lookup"><span data-stu-id="34d91-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="34d91-104">Se você precisar colaborar com pessoas de fora da sua organização em documentos no SharePoint ou no OneDrive, você pode enviar-lhes um link de compartilhamento para o documento.</span><span class="sxs-lookup"><span data-stu-id="34d91-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing-link to the document.</span></span> <span data-ttu-id="34d91-105">Neste artigo, veremos as etapas de configuração do Microsoft 365 necessárias para configurar o compartilhamento de links para o SharePoint e o OneDrive para as necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="34d91-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing-links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="34d91-106">Demonstração de vídeo</span><span class="sxs-lookup"><span data-stu-id="34d91-106">Video demonstration</span></span>

<span data-ttu-id="34d91-107">Este vídeo mostra as etapas de configuração descritas neste documento.</span><span class="sxs-lookup"><span data-stu-id="34d91-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="34d91-108">Configurações de relações organizacionais do Azure</span><span class="sxs-lookup"><span data-stu-id="34d91-108">Azure organizational relationships settings</span></span>

<span data-ttu-id="34d91-109">O compartilhamento no Microsoft 365 é regido no seu nível mais alto pelas [configurações de relações organizacionais no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="34d91-109">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="34d91-110">Se o compartilhamento de convidados estiver desabilitado ou restrito no Azure AD, essa configuração substituirá as configurações de compartilhamento que você configurar no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34d91-110">If guest-sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="34d91-111">Verifique as configurações de relações organizacionais para garantir que o compartilhamento com convidados não seja bloqueado.</span><span class="sxs-lookup"><span data-stu-id="34d91-111">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Captura de tela da página de configurações das Relações Organizacionais do Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="34d91-113">Para definir as configurações de relação organizacional</span><span class="sxs-lookup"><span data-stu-id="34d91-113">To set organizational relationship settings</span></span>

<span data-ttu-id="34d91-114">Para definir configurações de colaboração externa</span><span class="sxs-lookup"><span data-stu-id="34d91-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="34d91-115">Faça logon no Azure Active Directory em [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="34d91-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="34d91-116">No painel de navegação esquerdo, clique em **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="34d91-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="34d91-117">Clique em **identidades externas**.</span><span class="sxs-lookup"><span data-stu-id="34d91-117">Click **External identities**.</span></span>
4. <span data-ttu-id="34d91-118">Na tela **introdução** , no painel de navegação esquerdo, clique em **configurações de colaboração externa**.</span><span class="sxs-lookup"><span data-stu-id="34d91-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="34d91-119">Certifique-se de que **Administradores e usuários na função de convite de convidado podem convidar** e **os membros podem convidar** estão definidos como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="34d91-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="34d91-120">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="34d91-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="34d91-121">Observe as configurações na seção **restrições de colaboração** .</span><span class="sxs-lookup"><span data-stu-id="34d91-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="34d91-122">Certifique-se de que os domínios dos convidados com os quais você deseja colaborar não estão bloqueados.</span><span class="sxs-lookup"><span data-stu-id="34d91-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="34d91-123">Se você trabalha com convidados de várias organizações, convém restringir sua capacidade de acessar dados de diretório.</span><span class="sxs-lookup"><span data-stu-id="34d91-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="34d91-124">Isso impedirá que você veja quem mais é um convidado no diretório.</span><span class="sxs-lookup"><span data-stu-id="34d91-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="34d91-125">Para fazer isso, em **restrições de acesso de usuário convidado** , selecione **os usuários convidados têm acesso limitado às propriedades e à associação de configurações de objetos de diretório** ou **o acesso de usuário convidado é restrito a propriedades e associações de seus próprios objetos de diretório**.</span><span class="sxs-lookup"><span data-stu-id="34d91-125">To do this, under **Guest user access restrictions** , select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="34d91-126">Configurações de compartilhamento no nível da organização do SharePoint</span><span class="sxs-lookup"><span data-stu-id="34d91-126">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="34d91-127">Para que as pessoas de fora da sua organização tenham acesso a um documento no SharePoint ou no OneDrive, as configurações de compartilhamento no nível da organização do SharePoint e do OneDrive devem permitir o compartilhamento com pessoas de fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="34d91-127">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="34d91-128">As configurações de nível de organização para o SharePoint determinam as configurações que estarão disponíveis para sites individuais do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="34d91-128">The organization-level settings for SharePoint determine the settings that will be available for individual SharePoint sites.</span></span> <span data-ttu-id="34d91-129">As configurações do site não podem ser mais permissivas do que as configurações no nível da organização.</span><span class="sxs-lookup"><span data-stu-id="34d91-129">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="34d91-130">A configuração de nível de organização para o OneDrive determina o nível de compartilhamento que estará disponível nas bibliotecas do OneDrive dos usuários.</span><span class="sxs-lookup"><span data-stu-id="34d91-130">The organization-level setting for OneDrive determines the level of sharing that will be available in users' OneDrive libraries.</span></span>

<span data-ttu-id="34d91-131">Para o SharePoint e o OneDrive, se você quiser permitir compartilhamento de arquivos e pastas não autenticados, escolha **qualquer pessoa**.</span><span class="sxs-lookup"><span data-stu-id="34d91-131">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="34d91-132">Se você quiser garantir que as pessoas de fora da sua organização tenham que se autenticar, escolha **novos e existentes convidados**.</span><span class="sxs-lookup"><span data-stu-id="34d91-132">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="34d91-133">Links de *qualquer pessoa* é a maneira mais fácil de compartilhar: pessoas de fora da sua organização podem abrir o link sem autenticação e ficar livres para passá-lo para outros.</span><span class="sxs-lookup"><span data-stu-id="34d91-133">*Anyone* links is the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="34d91-134">Para o SharePoint, escolha a configuração mais permissiva que será necessária para qualquer site em sua organização.</span><span class="sxs-lookup"><span data-stu-id="34d91-134">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Captura de tela das configurações de compartilhamento no nível da organização do SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="34d91-136">Para definir as configurações de compartilhamento no nível da organização do SharePoint</span><span class="sxs-lookup"><span data-stu-id="34d91-136">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="34d91-137">No centro de administração do Microsoft 365, no painel de navegação esquerdo, em **centros de administração** , clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="34d91-137">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers** , click **SharePoint**.</span></span>
2. <span data-ttu-id="34d91-138">No centro de administração do SharePoint, no painel de navegação esquerdo, em **políticas** , clique em **compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="34d91-138">In the SharePoint admin center, in the left navigation pane, under **Policies** , click **Sharing**.</span></span>
3. <span data-ttu-id="34d91-139">Certifique-se de que o compartilhamento externo do SharePoint ou do OneDrive está definido como **qualquer pessoa** ou **convidado novo e existente**.</span><span class="sxs-lookup"><span data-stu-id="34d91-139">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="34d91-140">(Observe que a configuração do OneDrive não pode ser mais permissiva do que a configuração do SharePoint.)</span><span class="sxs-lookup"><span data-stu-id="34d91-140">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="34d91-141">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="34d91-141">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="34d91-142">Configurações de link padrão no nível da organização do SharePoint</span><span class="sxs-lookup"><span data-stu-id="34d91-142">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="34d91-143">As configurações padrão de link de arquivo e pasta determinam a opção de link que será mostrada para os usuários por padrão ao compartilhar um arquivo ou uma pasta.</span><span class="sxs-lookup"><span data-stu-id="34d91-143">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="34d91-144">Os usuários podem alterar o tipo de link para uma das outras opções antes de compartilhar, se desejado.</span><span class="sxs-lookup"><span data-stu-id="34d91-144">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="34d91-145">Tenha em mente que essa configuração afeta os sites do SharePoint em sua organização, bem como o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="34d91-145">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="34d91-146">Escolha um link de qualquer um dos seguintes tipos, que é selecionado por padrão quando os usuários compartilham arquivos e pastas:</span><span class="sxs-lookup"><span data-stu-id="34d91-146">Choose a link from any of the following types which is then selected by default when users share files and folders:</span></span>

- <span data-ttu-id="34d91-147">**Qualquer pessoa com o link** -escolha essa opção se você quiser fazer muito do compartilhamento de arquivos e pastas não autenticados.</span><span class="sxs-lookup"><span data-stu-id="34d91-147">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="34d91-148">Se você quiser permitir links de *qualquer pessoa* , mas estiver preocupado com o compartilhamento acidental não autenticado, considere uma das outras opções como padrão.</span><span class="sxs-lookup"><span data-stu-id="34d91-148">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="34d91-149">Esse tipo de link só estará disponível se você tiver habilitado o compartilhamento de **qualquer pessoa** .</span><span class="sxs-lookup"><span data-stu-id="34d91-149">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="34d91-150">**Somente as pessoas da sua organização** -escolha esta opção se você espera que a maioria dos compartilhamento de arquivos e pastas seja com pessoas dentro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="34d91-150">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="34d91-151">**Pessoas específicas** -considere essa opção se você espera que um grande volume de compartilhamento de arquivos e pastas com convidados.</span><span class="sxs-lookup"><span data-stu-id="34d91-151">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="34d91-152">Esse tipo de link funciona com convidados e exige a autenticação.</span><span class="sxs-lookup"><span data-stu-id="34d91-152">This type of link works with guests and requires them to authenticate.</span></span>
 
![Captura de tela das configurações de compartilhamento de pastas e arquivos no nível da organização do SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="34d91-154">Para definir as configurações de link padrão no nível da organização do SharePoint e do OneDrive</span><span class="sxs-lookup"><span data-stu-id="34d91-154">To set the SharePoint and OneDrive organization-level default link settings</span></span>

1. <span data-ttu-id="34d91-155">Navegue até a página de compartilhamento no centro de administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="34d91-155">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="34d91-156">Em **links de arquivo e pasta** , selecione o link de compartilhamento padrão que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="34d91-156">Under **File and folder links** , select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="34d91-157">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="34d91-157">If you made changes, click **Save**.</span></span>

<span data-ttu-id="34d91-158">Para definir a permissão para o link de compartilhamento, em **escolha a permissão selecionada por padrão para links de compartilhamento.**</span><span class="sxs-lookup"><span data-stu-id="34d91-158">To set the permission for the sharing link, under **Choose the permission that's selected by default for sharing links.**</span></span>

1. <span data-ttu-id="34d91-159">Selecione **Exibir** se você não quiser que usuários não autenticados façam alterações nos arquivos e pastas.</span><span class="sxs-lookup"><span data-stu-id="34d91-159">Select **View** if you do not want unauthenticated users to make changes to the files and folders.</span></span>
2. <span data-ttu-id="34d91-160">Selecione **Editar** se quiser permitir que usuários não autenticados façam alterações nos arquivos e pastas.</span><span class="sxs-lookup"><span data-stu-id="34d91-160">Select **Edit** if you want to allow unauthenticated users to make changes to the files and folders.</span></span>

<span data-ttu-id="34d91-161">Observe que as duas opções de ignoração acima podem ser aplicadas não apenas para convidados/usuários externos, mas também para usuários internos.</span><span class="sxs-lookup"><span data-stu-id="34d91-161">Note that the above two premission-options can be applied not only for guests/external users but also for internal users.</span></span> <span data-ttu-id="34d91-162">A opção de permissão escolhida é determinada por autocritério.</span><span class="sxs-lookup"><span data-stu-id="34d91-162">The permission-option you choose is determined by self-discretion.</span></span>

<span data-ttu-id="34d91-163">Para definir permissões para links que permitem o compartilhamento com qualquer pessoa</span><span class="sxs-lookup"><span data-stu-id="34d91-163">To set permissions for links that allow sharing with anyone</span></span>

1. <span data-ttu-id="34d91-164">Nos **seguintes links podem conceder estas permissões:** Subpainel,</span><span class="sxs-lookup"><span data-stu-id="34d91-164">Under the **These links can give these permissions:** sub-pane,</span></span> 
    1. <span data-ttu-id="34d91-165">Na lista suspensa **arquivos** ,</span><span class="sxs-lookup"><span data-stu-id="34d91-165">From the **Files** drop-down list,</span></span> 
        1. <span data-ttu-id="34d91-166">Selecione **Exibir e editar** se quiser permitir que usuários não autenticados façam alterações nos arquivos.</span><span class="sxs-lookup"><span data-stu-id="34d91-166">Select **View and edit** if you want to allow unauthenticated users to make changes to the files.</span></span>
        2. <span data-ttu-id="34d91-167">Selecione **Exibir** se você não quiser que usuários não autenticados façam alterações nos arquivos.</span><span class="sxs-lookup"><span data-stu-id="34d91-167">Select **View** if you do not want unauthenticated users to make changes to the files.</span></span>
    2. <span data-ttu-id="34d91-168">Na lista suspensa **pastas** ,</span><span class="sxs-lookup"><span data-stu-id="34d91-168">From the **Folders** drop-down list,</span></span>
        1. <span data-ttu-id="34d91-169">Selecione **Exibir, editar e carregar** se quiser permitir que usuários não autenticados façam alterações nas pastas.</span><span class="sxs-lookup"><span data-stu-id="34d91-169">Select **View, edit, and upload** if you want to allow unauthenticated users to make changes to the folders.</span></span>
        2. <span data-ttu-id="34d91-170">Selecione **Exibir** se você não quiser que usuários não autenticados façam alterações nas pastas.</span><span class="sxs-lookup"><span data-stu-id="34d91-170">Select **View** if you do not want unauthenticated users to make changes to the folders.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="34d91-171">Configurações de compartilhamento no nível do site do SharePoint</span><span class="sxs-lookup"><span data-stu-id="34d91-171">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="34d91-172">Se você estiver compartilhando arquivos e pastas que estão em um site do SharePoint, também precisará verificar as configurações de compartilhamento no nível do site.</span><span class="sxs-lookup"><span data-stu-id="34d91-172">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![Captura de tela das configurações de compartilhamento de site externo do SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="34d91-174">Para definir configurações de compartilhamento no nível do site</span><span class="sxs-lookup"><span data-stu-id="34d91-174">To set site-level sharing settings</span></span>

1. <span data-ttu-id="34d91-175">No centro de administração do SharePoint, no painel de navegação esquerdo, expanda **sites** e clique em **sites ativos**.</span><span class="sxs-lookup"><span data-stu-id="34d91-175">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="34d91-176">Selecione o site no qual você deseja compartilhar arquivos e pastas com convidados.</span><span class="sxs-lookup"><span data-stu-id="34d91-176">Select the site on which you want to share files and folders with guests.</span></span>
3. <span data-ttu-id="34d91-177">Role à direita através da linha (na qual o site selecionado está presente) e clique em qualquer lugar na coluna **compartilhamento externo** .</span><span class="sxs-lookup"><span data-stu-id="34d91-177">Scroll right across the row (in which the selected site is present) and click anywhere in the **External sharing** column.</span></span>
4. <span data-ttu-id="34d91-178">Na página exibida, clique na guia **políticas** .</span><span class="sxs-lookup"><span data-stu-id="34d91-178">From the page that pops up, click **Policies** tab.</span></span>
5. <span data-ttu-id="34d91-179">No painel **compartilhamento externo** , clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="34d91-179">Under the **External sharing** pane, click **Edit**.</span></span>
6. <span data-ttu-id="34d91-180">Verifique se o compartilhamento está definido como **qualquer pessoa** ou **convidado novo e existente**.</span><span class="sxs-lookup"><span data-stu-id="34d91-180">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
7. <span data-ttu-id="34d91-181">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="34d91-181">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="34d91-182">Convidar usuários</span><span class="sxs-lookup"><span data-stu-id="34d91-182">Invite users</span></span>

<span data-ttu-id="34d91-183">As configurações de compartilhamento de convidados agora estão configuradas; Portanto, os usuários agora podem compartilhar arquivos e pastas com pessoas de fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="34d91-183">Guest-sharing settings are now configured; so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="34d91-184">Consulte [compartilhar arquivos e pastas do onedrive](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) e [compartilhar arquivos ou pastas do SharePoint](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="34d91-184">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="34d91-185">Confira também</span><span class="sxs-lookup"><span data-stu-id="34d91-185">See also</span></span>

[<span data-ttu-id="34d91-186">Práticas recomendadas para compartilhar arquivos e pastas com usuários não autenticados</span><span class="sxs-lookup"><span data-stu-id="34d91-186">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="34d91-187">Limitar a exposição acidental dos arquivos ao compartilhar com convidados</span><span class="sxs-lookup"><span data-stu-id="34d91-187">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="34d91-188">Integração do SharePoint e do OneDrive com o B2B do Azure AD</span><span class="sxs-lookup"><span data-stu-id="34d91-188">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
