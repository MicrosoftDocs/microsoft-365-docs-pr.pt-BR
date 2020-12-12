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
description: Neste artigo, você aprenderá como colaborar com convidados em um documento no SharePoint e no OneDrive.
ms.openlocfilehash: 1b2fe003902b69e4c0c58852af67862ce6f2eb34
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663506"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="02027-103">Colaborar com convidados em um documento</span><span class="sxs-lookup"><span data-stu-id="02027-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="02027-104">Se você precisar colaborar com pessoas de fora da sua organização em documentos no SharePoint ou no OneDrive, você pode enviar-lhes um link de compartilhamento para o documento.</span><span class="sxs-lookup"><span data-stu-id="02027-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing-link to the document.</span></span> <span data-ttu-id="02027-105">Neste artigo, veremos as etapas de configuração do Microsoft 365 necessárias para configurar o compartilhamento de links para o SharePoint e o OneDrive para as necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="02027-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing-links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="02027-106">Demonstração de vídeo</span><span class="sxs-lookup"><span data-stu-id="02027-106">Video demonstration</span></span>

<span data-ttu-id="02027-107">Este vídeo mostra as etapas de configuração descritas neste documento.</span><span class="sxs-lookup"><span data-stu-id="02027-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="02027-108">Configurações de colaboração externa do Azure</span><span class="sxs-lookup"><span data-stu-id="02027-108">Azure external collaboration settings</span></span>

<span data-ttu-id="02027-109">O compartilhamento no Microsoft 365 é regido em seu nível mais alto pelas [configurações de colaboração externa B2B no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="02027-109">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="02027-110">Se o compartilhamento de convidados estiver desabilitado ou restrito no Azure AD, essa configuração substituirá as configurações de compartilhamento que você configurar no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="02027-110">If guest-sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="02027-111">Verifique as configurações de colaboração externa B2B para garantir que o compartilhamento com convidados não seja bloqueado.</span><span class="sxs-lookup"><span data-stu-id="02027-111">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Captura de tela da página de configurações das Relações Organizacionais do Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="02027-113">Para definir configurações de colaboração externa</span><span class="sxs-lookup"><span data-stu-id="02027-113">To set external collaboration settings</span></span>

1. <span data-ttu-id="02027-114">Faça logon no Azure Active Directory em [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="02027-114">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="02027-115">No painel de navegação esquerdo, clique em **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="02027-115">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="02027-116">Clique em **identidades externas**.</span><span class="sxs-lookup"><span data-stu-id="02027-116">Click **External identities**.</span></span>
4. <span data-ttu-id="02027-117">Na tela **introdução** , no painel de navegação esquerdo, clique em **configurações de colaboração externa**.</span><span class="sxs-lookup"><span data-stu-id="02027-117">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="02027-118">Certifique-se de que **Administradores e usuários na função de convite de convidado podem convidar** e **os membros podem convidar** estão definidos como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="02027-118">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="02027-119">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="02027-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="02027-120">Observe as configurações na seção **restrições de colaboração** .</span><span class="sxs-lookup"><span data-stu-id="02027-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="02027-121">Certifique-se de que os domínios dos convidados com os quais você deseja colaborar não estão bloqueados.</span><span class="sxs-lookup"><span data-stu-id="02027-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="02027-122">Se você trabalha com convidados de várias organizações, convém restringir sua capacidade de acessar dados de diretório.</span><span class="sxs-lookup"><span data-stu-id="02027-122">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="02027-123">Isso impedirá que você veja quem mais é um convidado no diretório.</span><span class="sxs-lookup"><span data-stu-id="02027-123">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="02027-124">Para fazer isso, em **restrições de acesso de usuário convidado**, selecione **os usuários convidados têm acesso limitado às propriedades e à associação de configurações de objetos de diretório** ou **o acesso de usuário convidado é restrito a propriedades e associações de seus próprios objetos de diretório**.</span><span class="sxs-lookup"><span data-stu-id="02027-124">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="02027-125">Configurações de compartilhamento no nível da organização do SharePoint</span><span class="sxs-lookup"><span data-stu-id="02027-125">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="02027-126">Para que as pessoas de fora da sua organização tenham acesso a um documento no SharePoint ou no OneDrive, as configurações de compartilhamento no nível da organização do SharePoint e do OneDrive devem permitir o compartilhamento com pessoas de fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="02027-126">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="02027-127">As configurações de nível de organização para o SharePoint determinam as configurações que estarão disponíveis para sites individuais do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="02027-127">The organization-level settings for SharePoint determine the settings that will be available for individual SharePoint sites.</span></span> <span data-ttu-id="02027-128">As configurações do site não podem ser mais permissivas do que as configurações no nível da organização.</span><span class="sxs-lookup"><span data-stu-id="02027-128">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="02027-129">A configuração de nível de organização para o OneDrive determina o nível de compartilhamento que estará disponível nas bibliotecas do OneDrive dos usuários.</span><span class="sxs-lookup"><span data-stu-id="02027-129">The organization-level setting for OneDrive determines the level of sharing that will be available in users' OneDrive libraries.</span></span>

<span data-ttu-id="02027-130">Para o SharePoint e o OneDrive, se você quiser permitir compartilhamento de arquivos e pastas não autenticados, escolha **qualquer pessoa**.</span><span class="sxs-lookup"><span data-stu-id="02027-130">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="02027-131">Se você quiser garantir que as pessoas de fora da sua organização tenham que se autenticar, escolha **novos e existentes convidados**.</span><span class="sxs-lookup"><span data-stu-id="02027-131">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="02027-132">Links de *qualquer pessoa* é a maneira mais fácil de compartilhar: pessoas de fora da sua organização podem abrir o link sem autenticação e ficar livres para passá-lo para outros.</span><span class="sxs-lookup"><span data-stu-id="02027-132">*Anyone* links is the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="02027-133">Para o SharePoint, escolha a configuração mais permissiva que será necessária para qualquer site em sua organização.</span><span class="sxs-lookup"><span data-stu-id="02027-133">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Captura de tela das configurações de compartilhamento no nível da organização do SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="02027-135">Para definir as configurações de compartilhamento no nível da organização do SharePoint</span><span class="sxs-lookup"><span data-stu-id="02027-135">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="02027-136">No centro de administração do Microsoft 365, no painel de navegação esquerdo, em **centros de administração**, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="02027-136">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="02027-137">No centro de administração do SharePoint, no painel de navegação esquerdo, em **políticas**, clique em **compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="02027-137">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="02027-138">Certifique-se de que o compartilhamento externo do SharePoint ou do OneDrive está definido como **qualquer pessoa** ou **convidado novo e existente**.</span><span class="sxs-lookup"><span data-stu-id="02027-138">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="02027-139">(Observe que a configuração do OneDrive não pode ser mais permissiva do que a configuração do SharePoint.)</span><span class="sxs-lookup"><span data-stu-id="02027-139">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="02027-140">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="02027-140">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="02027-141">Configurações de link padrão no nível da organização do SharePoint</span><span class="sxs-lookup"><span data-stu-id="02027-141">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="02027-142">As configurações padrão de link de arquivo e pasta determinam a opção de link que será mostrada para os usuários por padrão ao compartilhar um arquivo ou uma pasta.</span><span class="sxs-lookup"><span data-stu-id="02027-142">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="02027-143">Os usuários podem alterar o tipo de link para uma das outras opções antes de compartilhar, se desejado.</span><span class="sxs-lookup"><span data-stu-id="02027-143">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="02027-144">Tenha em mente que essa configuração afeta os sites do SharePoint em sua organização, bem como o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="02027-144">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="02027-145">Escolha um link de qualquer um dos seguintes tipos, que é selecionado por padrão quando os usuários compartilham arquivos e pastas:</span><span class="sxs-lookup"><span data-stu-id="02027-145">Choose a link from any of the following types which is then selected by default when users share files and folders:</span></span>

- <span data-ttu-id="02027-146">**Qualquer pessoa com o link** -escolha essa opção se você quiser fazer muito do compartilhamento de arquivos e pastas não autenticados.</span><span class="sxs-lookup"><span data-stu-id="02027-146">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="02027-147">Se você quiser permitir links de *qualquer pessoa* , mas estiver preocupado com o compartilhamento acidental não autenticado, considere uma das outras opções como padrão.</span><span class="sxs-lookup"><span data-stu-id="02027-147">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="02027-148">Esse tipo de link só estará disponível se você tiver habilitado o compartilhamento de **qualquer pessoa** .</span><span class="sxs-lookup"><span data-stu-id="02027-148">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="02027-149">**Somente as pessoas da sua organização** -escolha esta opção se você espera que a maioria dos compartilhamento de arquivos e pastas seja com pessoas dentro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="02027-149">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="02027-150">**Pessoas específicas** -considere essa opção se você espera que um grande volume de compartilhamento de arquivos e pastas com convidados.</span><span class="sxs-lookup"><span data-stu-id="02027-150">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="02027-151">Esse tipo de link funciona com convidados e exige a autenticação.</span><span class="sxs-lookup"><span data-stu-id="02027-151">This type of link works with guests and requires them to authenticate.</span></span>
 
![Captura de tela das configurações de compartilhamento de pastas e arquivos no nível da organização do SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="02027-153">Para definir as configurações de link padrão no nível da organização do SharePoint e do OneDrive</span><span class="sxs-lookup"><span data-stu-id="02027-153">To set the SharePoint and OneDrive organization-level default link settings</span></span>

1. <span data-ttu-id="02027-154">Navegue até a página de compartilhamento no centro de administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="02027-154">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="02027-155">Em **links de arquivo e pasta**, selecione o link de compartilhamento padrão que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="02027-155">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="02027-156">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="02027-156">If you made changes, click **Save**.</span></span>

<span data-ttu-id="02027-157">Para definir a permissão para o link de compartilhamento, em **escolha a permissão selecionada por padrão para links de compartilhamento.**</span><span class="sxs-lookup"><span data-stu-id="02027-157">To set the permission for the sharing link, under **Choose the permission that's selected by default for sharing links.**</span></span>

1. <span data-ttu-id="02027-158">Selecione **Exibir** se você não quiser que usuários não autenticados façam alterações nos arquivos e pastas.</span><span class="sxs-lookup"><span data-stu-id="02027-158">Select **View** if you do not want unauthenticated users to make changes to the files and folders.</span></span>
2. <span data-ttu-id="02027-159">Selecione **Editar** se quiser permitir que usuários não autenticados façam alterações nos arquivos e pastas.</span><span class="sxs-lookup"><span data-stu-id="02027-159">Select **Edit** if you want to allow unauthenticated users to make changes to the files and folders.</span></span>

<span data-ttu-id="02027-160">Observe que as duas opções de ignoração acima podem ser aplicadas não apenas para convidados/usuários externos, mas também para usuários internos.</span><span class="sxs-lookup"><span data-stu-id="02027-160">Note that the above two premission-options can be applied not only for guests/external users but also for internal users.</span></span> <span data-ttu-id="02027-161">A opção de permissão escolhida é determinada por autocritério.</span><span class="sxs-lookup"><span data-stu-id="02027-161">The permission-option you choose is determined by self-discretion.</span></span>

<span data-ttu-id="02027-162">Para definir permissões para links que permitem o compartilhamento com qualquer pessoa</span><span class="sxs-lookup"><span data-stu-id="02027-162">To set permissions for links that allow sharing with anyone</span></span>

1. <span data-ttu-id="02027-163">Nos **seguintes links podem conceder estas permissões:** Subpainel,</span><span class="sxs-lookup"><span data-stu-id="02027-163">Under the **These links can give these permissions:** sub-pane,</span></span> 
    1. <span data-ttu-id="02027-164">Na lista suspensa **arquivos** ,</span><span class="sxs-lookup"><span data-stu-id="02027-164">From the **Files** drop-down list,</span></span> 
        - <span data-ttu-id="02027-165">Selecione **Exibir e editar** se quiser permitir que usuários não autenticados façam alterações nos arquivos.</span><span class="sxs-lookup"><span data-stu-id="02027-165">Select **View and edit** if you want to allow unauthenticated users to make changes to the files.</span></span>
        - <span data-ttu-id="02027-166">Selecione **Exibir** se você não quiser que usuários não autenticados façam alterações nos arquivos.</span><span class="sxs-lookup"><span data-stu-id="02027-166">Select **View** if you do not want unauthenticated users to make changes to the files.</span></span>
    2. <span data-ttu-id="02027-167">Na lista suspensa **pastas** ,</span><span class="sxs-lookup"><span data-stu-id="02027-167">From the **Folders** drop-down list,</span></span>
        - <span data-ttu-id="02027-168">Selecione **Exibir, editar e carregar** se quiser permitir que usuários não autenticados façam alterações nas pastas.</span><span class="sxs-lookup"><span data-stu-id="02027-168">Select **View, edit, and upload** if you want to allow unauthenticated users to make changes to the folders.</span></span>
        - <span data-ttu-id="02027-169">Selecione **Exibir** se você não quiser que usuários não autenticados façam alterações nas pastas.</span><span class="sxs-lookup"><span data-stu-id="02027-169">Select **View** if you do not want unauthenticated users to make changes to the folders.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="02027-170">Configurações de compartilhamento no nível do site do SharePoint</span><span class="sxs-lookup"><span data-stu-id="02027-170">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="02027-171">Se você estiver compartilhando arquivos e pastas que estão em um site do SharePoint, também precisará verificar as configurações de compartilhamento no nível do site.</span><span class="sxs-lookup"><span data-stu-id="02027-171">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![Captura de tela das configurações de compartilhamento de site externo do SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="02027-173">Para definir configurações de compartilhamento no nível do site</span><span class="sxs-lookup"><span data-stu-id="02027-173">To set site-level sharing settings</span></span>

1. <span data-ttu-id="02027-174">No centro de administração do SharePoint, no painel de navegação esquerdo, expanda **sites** e clique em **sites ativos**.</span><span class="sxs-lookup"><span data-stu-id="02027-174">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="02027-175">Selecione o site no qual você deseja compartilhar arquivos e pastas com convidados.</span><span class="sxs-lookup"><span data-stu-id="02027-175">Select the site on which you want to share files and folders with guests.</span></span>
3. <span data-ttu-id="02027-176">Role à direita através da linha (na qual o site selecionado está presente) e clique em qualquer lugar na coluna **compartilhamento externo** .</span><span class="sxs-lookup"><span data-stu-id="02027-176">Scroll right across the row (in which the selected site is present) and click anywhere in the **External sharing** column.</span></span>
4. <span data-ttu-id="02027-177">Na página exibida, clique na guia **políticas** .</span><span class="sxs-lookup"><span data-stu-id="02027-177">From the page that pops up, click **Policies** tab.</span></span>
5. <span data-ttu-id="02027-178">No painel **compartilhamento externo** , clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="02027-178">Under the **External sharing** pane, click **Edit**.</span></span>
6. <span data-ttu-id="02027-179">Verifique se o compartilhamento está definido como **qualquer pessoa** ou **convidado novo e existente**.</span><span class="sxs-lookup"><span data-stu-id="02027-179">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
7. <span data-ttu-id="02027-180">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="02027-180">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="02027-181">Convidar usuários</span><span class="sxs-lookup"><span data-stu-id="02027-181">Invite users</span></span>

<span data-ttu-id="02027-182">As configurações de compartilhamento de convidados agora estão configuradas; Portanto, os usuários agora podem compartilhar arquivos e pastas com pessoas de fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="02027-182">Guest-sharing settings are now configured; so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="02027-183">Consulte [compartilhar arquivos e pastas do onedrive](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) e [compartilhar arquivos ou pastas do SharePoint](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="02027-183">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="02027-184">Confira também</span><span class="sxs-lookup"><span data-stu-id="02027-184">See also</span></span>

[<span data-ttu-id="02027-185">Práticas recomendadas para compartilhar arquivos e pastas com usuários não autenticados</span><span class="sxs-lookup"><span data-stu-id="02027-185">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="02027-186">Limitar a exposição acidental dos arquivos ao compartilhar com convidados</span><span class="sxs-lookup"><span data-stu-id="02027-186">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="02027-187">Integração do SharePoint e do OneDrive com o B2B do Azure AD</span><span class="sxs-lookup"><span data-stu-id="02027-187">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
