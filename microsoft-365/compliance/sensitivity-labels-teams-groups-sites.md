---
title: Use etiquetas de confidencialidade com o Microsoft Teams, grupos do Office 365 e sites do SharePoint (visualização pública)
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Você pode aplicar rótulos ao Microsoft Teams, grupos do Office 365 e sites do SharePoint.
ms.openlocfilehash: 350e1906e4d645c444d772b1ade9a2ff9c850992
ms.sourcegitcommit: 1b1425142ae06deae3da10a7d30dce4db029d6d3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/27/2020
ms.locfileid: "42313796"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="ad35d-103">Use etiquetas de confidencialidade com o Microsoft Teams, grupos do Office 365 e sites do SharePoint (visualização pública)</span><span class="sxs-lookup"><span data-stu-id="ad35d-103">Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>

<span data-ttu-id="ad35d-104">Ao criar rótulos de confidencialidade no [Centro de conformidade do Microsoft 365](https://protection.office.com/), você pode aplicá-los aos seguintes contêineres: Microsoft Teams, grupos do Office 365 e sites do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ad35d-104">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to the following containers: Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="ad35d-105">Use as configurações de rótulo para controlar as seguintes opções para esses contêineres:</span><span class="sxs-lookup"><span data-stu-id="ad35d-105">Use label settings to control the following options for these containers:</span></span>

- <span data-ttu-id="ad35d-106">Privacidade (pública ou privada) dos sites de equipes conectados a grupos do Office 365</span><span class="sxs-lookup"><span data-stu-id="ad35d-106">Privacy (public or private) of Office 365 group-connected teams sites</span></span>
- <span data-ttu-id="ad35d-107">Acesso de usuários externos</span><span class="sxs-lookup"><span data-stu-id="ad35d-107">External users access</span></span>
- <span data-ttu-id="ad35d-108">Acesso de dispositivos não gerenciados</span><span class="sxs-lookup"><span data-stu-id="ad35d-108">Access from unmanaged devices</span></span> 

<span data-ttu-id="ad35d-109">Quando você aplica esse rótulo a um dos contêineres suportados, o rótulo aplica automaticamente as opções configuradas ao site de equipe ou site do SharePoint conectado.</span><span class="sxs-lookup"><span data-stu-id="ad35d-109">When you apply this label to one of the supported containers, the label automatically applies the configured options to the connected SharePoint site or team site.</span></span> 

<span data-ttu-id="ad35d-110">O conteúdo desses contêineres, no entanto, não herda os rótulos das configurações como nome, marcações visuais ou criptografia.</span><span class="sxs-lookup"><span data-stu-id="ad35d-110">Content in those containers however, do not inherit the labels for settings such as the label name, visual markings, or encryption.</span></span> <span data-ttu-id="ad35d-111">Para rotular arquivos em sites do SharePoint ou sites de equipe, [Habilite os rótulos de confidencialidade dos arquivos do Office no SharePoint e no OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="ad35d-111">To label files in SharePoint sites or team sites, [enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a><span data-ttu-id="ad35d-112">Sobre a visualização pública do Microsoft Teams, grupos do Office 365 e sites do SharePoint</span><span class="sxs-lookup"><span data-stu-id="ad35d-112">About the public preview for Microsoft Teams, Office 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="ad35d-113">Os rótulos de confidencialidade do Microsoft Teams, grupos do Office 365 e de sites do SharePoint são gradualmente implementados para locatários e podem ser alterados antes do lançamento final.</span><span class="sxs-lookup"><span data-stu-id="ad35d-113">Sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites are gradually rolling out to tenants and might change before final release.</span></span> <span data-ttu-id="ad35d-114">Esta versão pública não funciona com as CDNs (redes de distribuição de conteúdo do Office 365).</span><span class="sxs-lookup"><span data-stu-id="ad35d-114">This public preview doesn't work with Office 365 Content Delivery Networks (CDNs).</span></span>

<span data-ttu-id="ad35d-115">Antes de habilitar essa visualização e definir os rótulos de confidencialidade das novas configurações, os usuários podem ver e aplicar rótulos de confidencialidade em seus aplicativos.</span><span class="sxs-lookup"><span data-stu-id="ad35d-115">Before you enable this preview and configure sensitivity labels for the new settings, users can see and apply sensitivity labels in their apps.</span></span> <span data-ttu-id="ad35d-116">Por exemplo, no Word:</span><span class="sxs-lookup"><span data-stu-id="ad35d-116">For example, from Word:</span></span>

![Um rótulo de confidencialidade exibido no aplicativo Word para área de trabalho](../media/sensitivity-label-word.png)

<span data-ttu-id="ad35d-118">Depois de habilitar e configurar essa visualização, os usuários também podem ver e aplicar rótulos de confidencialidade ao Microsoft Teams, grupos do Office 365 e sites do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ad35d-118">After you enable and configure this preview, users can additionally see and apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="ad35d-119">Por exemplo, quando você cria um novo site de equipe no SharePoint:</span><span class="sxs-lookup"><span data-stu-id="ad35d-119">For example, when you create a new team site from SharePoint:</span></span>

![Um rótulo de confidencialidade ao criar um site de equipe do SharePoint](../media/sensitivity-labels-new-team-site.png)

## <a name="enable-this-preview-and-synchronize-labels"></a><span data-ttu-id="ad35d-121">Habilitar esta visualização e sincronizar rótulos</span><span class="sxs-lookup"><span data-stu-id="ad35d-121">Enable this preview and synchronize labels</span></span>

1. <span data-ttu-id="ad35d-122">Como esse recurso usa a funcionalidade do Azure AD, siga as instruções na documentação do Azure AD para habilitar a visualização: [Atribuir rótulos de confidencialidade aos grupos do Office 365 no Azure Active Directory (visualização)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="ad35d-122">Because this feature uses Azure AD functionality, follow the instructions in the Azure AD documentation to enable the preview: [Assign sensitivity labels to Office 365 groups in Azure Active Directory (preview)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span></span>

2. <span data-ttu-id="ad35d-123">Em uma sessão do PowerShell, conecte-se ao Centro de Conformidade e Segurança usando uma conta corporativa ou de estudante com privilégios de administrador global.</span><span class="sxs-lookup"><span data-stu-id="ad35d-123">In a PowerShell session, connect to the Security & Compliance Center by using a work or school account that has global admin privileges.</span></span> <span data-ttu-id="ad35d-124">Para mais instruções, confira [Conectar-se ao PowerShell do Centro de Conformidade e Segurança do Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="ad35d-124">For instructions, see [Connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

3. <span data-ttu-id="ad35d-125">Execute os seguintes comandos para sincronizar seus rótulos com o Azure AD, para que eles possam ser usados com grupos do Office 365:</span><span class="sxs-lookup"><span data-stu-id="ad35d-125">Run the following commands to synchronize your labels to Azure AD, so that they can be used with Office 365 groups:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a><span data-ttu-id="ad35d-126">Como definir configurações de site e grupo ao criar ou editar rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="ad35d-126">How to configure site and group settings when you create or edit sensitivity labels</span></span>

<span data-ttu-id="ad35d-127">Agora você está pronto para criar ou editar os rótulos de confidencialidade que deseja disponibilizar para sites e grupos.</span><span class="sxs-lookup"><span data-stu-id="ad35d-127">You're now ready to create or edit sensitivity labels that you want to be available for sites and groups.</span></span> <span data-ttu-id="ad35d-128">Habilitar a visualização torna uma nova página visível nas assistentes de rotulagem de confidencialidade: **Configurações de site e grupo**</span><span class="sxs-lookup"><span data-stu-id="ad35d-128">Enabling the preview makes a new page visible in the sensitivity labeling wizards: **Site and group settings**</span></span>

<span data-ttu-id="ad35d-129">Se precisar de ajuda para criar ou editar um rótulo de confidencialidade, confira as instruções em [Criar e configurar os rótulos de confidencialidade](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="ad35d-129">If you need help with creating or editing a sensitivity label, see the instructions from [Create and configure sensitivity labels](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span></span>

<span data-ttu-id="ad35d-130">Nesta nova página **Configurações de site e grupo**, defina as configurações:</span><span class="sxs-lookup"><span data-stu-id="ad35d-130">On this new **Site and group settings** page, configure the settings:</span></span>

- <span data-ttu-id="ad35d-131">**Privacidade dos sites de equipes conectados ao grupo do Office 365**: A configuração padrão de **Público** é selecionada automaticamente, o que significa que qualquer pessoa em sua organização pode acessar o site da equipe onde esse rótulo é aplicado.</span><span class="sxs-lookup"><span data-stu-id="ad35d-131">**Privacy of Office 365 group-connected teams sites**: The default setting of **Public** is automatically selected, which means anyone in your organization can access the team site where this label is applied.</span></span> <span data-ttu-id="ad35d-132">Selecione **Particular** quando desejar que apenas membros aprovados em sua organização acessem o site de equipe do grupo.</span><span class="sxs-lookup"><span data-stu-id="ad35d-132">Select **Private** when you want only approved members in your organization to access the group's team site.</span></span> 
    
    <span data-ttu-id="ad35d-133">A configuração selecionada substitui uma configuração de privacidade anterior que pode ser configurada para o grupo e bloqueia o valor da privacidade para que ele possa ser alterado apenas removendo primeiro o rótulo de confidencialidade do grupo ou site de equipe.</span><span class="sxs-lookup"><span data-stu-id="ad35d-133">The setting selected replaces a previous privacy setting that might be configured for the group, and locks the privacy value so it can be changed only by first removing the sensitivity label from the team site or group.</span></span> <span data-ttu-id="ad35d-134">Depois de remover o rótulo de confidencialidade, a configuração de privacidade do rótulo permanecerá, mas você pode alterá-lo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="ad35d-134">After you remove the sensitivity label, the privacy setting from the label remains and you can now change it if necessary.</span></span>

- <span data-ttu-id="ad35d-135">**Acesso de usuários externos**: Controle se o proprietário do grupo pode [adicionar convidados ao grupo](/office365/admin/create-groups/manage-guest-access-in-groups).</span><span class="sxs-lookup"><span data-stu-id="ad35d-135">**External users access**: Control whether the group owner can [add guests to the group](/office365/admin/create-groups/manage-guest-access-in-groups).</span></span>

- <span data-ttu-id="ad35d-136">**Dispositivos não gerenciados**: Para [dispositivos não gerenciados](/sharepoint/control-access-from-unmanaged-devices), permita acesso total, acesso somente Web ou bloqueio total de acesso.</span><span class="sxs-lookup"><span data-stu-id="ad35d-136">**Unmanaged devices**: For [unmanaged devices](/sharepoint/control-access-from-unmanaged-devices), allow full access, web only access, or block access completely.</span></span> 

![Guia configurações de site e grupo](../media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="ad35d-138">Somente essas configurações de site e grupo entrarão em vigor quando você aplicar um rótulo a uma equipe, grupo ou site.</span><span class="sxs-lookup"><span data-stu-id="ad35d-138">Only these site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="ad35d-139">Outras configurações de rótulo, como criptografia e marcação de conteúdo, não são aplicadas ao conteúdo da equipe, grupo ou site.</span><span class="sxs-lookup"><span data-stu-id="ad35d-139">Other label settings, such as encryption and content marking, aren't applied to the content within the team, group, or site.</span></span>
> 
> <span data-ttu-id="ad35d-140">Da mesma forma, se você criar um rótulo e não ativar essas configurações de site e grupo, o rótulo ainda estará disponível quando os usuários criarem equipes, grupos e sites, mas apenas o nome do rótulo será aplicado.</span><span class="sxs-lookup"><span data-stu-id="ad35d-140">Similarly, if you create a label and don't turn on these site and group settings, the label will still be available when users create teams, groups, and sites, but only the label name will be applied.</span></span>

<span data-ttu-id="ad35d-141">Se seu rótulo ainda não estiver publicado, publique-o agora [adicionando-o a uma política de rótulo](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span><span class="sxs-lookup"><span data-stu-id="ad35d-141">If your label isn't already published, now publish it by [adding it to a label policy](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

## <a name="sensitivity-label-management"></a><span data-ttu-id="ad35d-142">Gerenciamento de rótulo de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="ad35d-142">Sensitivity label management</span></span>

> [!WARNING]
> <span data-ttu-id="ad35d-143">Criar, modificar e excluir rótulos de confidencialidade que você usa para o Microsoft Teams, grupos do Office 365 e sites do SharePoint exige uma coordenação cuidadosa com as políticas de rótulo de publicação para os usuários.</span><span class="sxs-lookup"><span data-stu-id="ad35d-143">Creating, modifying, and deleting sensitivity labels that you use for Microsoft Teams, Office 365 groups, and SharePoint sites requires careful coordination with publishing label policies to users.</span></span> 

<span data-ttu-id="ad35d-144">Evite erros de criação para sites e grupos que possam afetar todos os usuários usando as diretrizes a seguir.</span><span class="sxs-lookup"><span data-stu-id="ad35d-144">Avoid creation errors for sites and groups that can affect all users by using the following guidance.</span></span>

<span data-ttu-id="ad35d-145">**Criar e publicar rótulos:**</span><span class="sxs-lookup"><span data-stu-id="ad35d-145">**Creating and publishing labels:**</span></span>

<span data-ttu-id="ad35d-146">Depois de criar e publicar um rótulo de confidencialidade, pode levar até 24 horas para que o rótulo se torne visível para usuários em equipes, grupos e sites.</span><span class="sxs-lookup"><span data-stu-id="ad35d-146">After a sensitivity label is created and published, it can take up to 24 hours for the label to become visible for users in teams, groups, and sites.</span></span> <span data-ttu-id="ad35d-147">Use as etapas a seguir para publicar um rótulo para todos os usuários no locatário:</span><span class="sxs-lookup"><span data-stu-id="ad35d-147">Use the following steps to publish a label for all users in the tenant:</span></span>

1. <span data-ttu-id="ad35d-148">Crie o rótulo de confidencialidade e publique-o para apenas algumas contas de usuários no locatário.</span><span class="sxs-lookup"><span data-stu-id="ad35d-148">Create the sensitivity label and publish it for just a few user accounts in the tenant.</span></span>

2. <span data-ttu-id="ad35d-149">Aguarde 24 horas.</span><span class="sxs-lookup"><span data-stu-id="ad35d-149">Wait for 24 hours.</span></span>

3. <span data-ttu-id="ad35d-150">Após essas 24 horas, use uma das contas de usuário especificadas na etapa 1 para criar uma equipe, um grupo do Office 365 ou um site do SharePoint com o rótulo que você criou na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="ad35d-150">After this 24 hours wait, use one of the user accounts you specified in step 1 to create a team, Office 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="ad35d-151">Se não houver erros durante a operação de criação da etapa 3, publique o rótulo para todos os usuários em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="ad35d-151">If there are no errors during the creation operation for step 3, publish the label for all users in your tenant.</span></span> <span data-ttu-id="ad35d-152">Se houver erros, contate o [suporte da Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="ad35d-152">If there are errors, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

<span data-ttu-id="ad35d-153">**Modificar e excluir rótulos publicados:**</span><span class="sxs-lookup"><span data-stu-id="ad35d-153">**Modifying and deleting published labels:**</span></span>

<span data-ttu-id="ad35d-154">Se você modificar ou excluir um rótulo de confidencialidade incluído em uma ou mais políticas de rótulo, essas ações poderão resultar em falhas de criação para todas as equipes, grupos e sites.</span><span class="sxs-lookup"><span data-stu-id="ad35d-154">If you modify or delete a sensitivity label that is included in one or more label policies, these actions can result in creation failures for all teams, groups, and sites.</span></span> <span data-ttu-id="ad35d-155">Para evitar essa situação, use as instruções a seguir:</span><span class="sxs-lookup"><span data-stu-id="ad35d-155">To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="ad35d-156">Remova o rótulo de confidencialidade de todas as políticas de rótulo que incluam o rótulo.</span><span class="sxs-lookup"><span data-stu-id="ad35d-156">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="ad35d-157">Aguarde por 48 horas.</span><span class="sxs-lookup"><span data-stu-id="ad35d-157">Wait for 48 hours.</span></span>

3. <span data-ttu-id="ad35d-158">Após as 48 horas de espera, experimente criar uma equipe, grupo ou site e confirme se o rótulo não está mais visível.</span><span class="sxs-lookup"><span data-stu-id="ad35d-158">After the 48 hours wait, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="ad35d-159">Se a etiqueta de confidencialidade não estiver visível, agora você pode modificá-la ou excluí-la com segurança.</span><span class="sxs-lookup"><span data-stu-id="ad35d-159">If the sensitivity label isn't visible, you can now safely modify or delete the label.</span></span> <span data-ttu-id="ad35d-160">Se o rótulo ainda estiver visível, contate o [suporte da Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="ad35d-160">If the label is still visible, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

## <a name="assign-sensitivity-labels-to-office-365-groups"></a><span data-ttu-id="ad35d-161">Atribuir rótulos de confidencialidade a grupos do Office 365</span><span class="sxs-lookup"><span data-stu-id="ad35d-161">Assign sensitivity labels to Office 365 groups</span></span>

<span data-ttu-id="ad35d-162">Agora você está pronto para aplicar os rótulos ou rótulos de confidencialidade aos grupos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ad35d-162">You're now ready to apply the sensitivity label or labels to Office 365 groups.</span></span> <span data-ttu-id="ad35d-163">Retorne à documentação do Azure AD para obter instruções:</span><span class="sxs-lookup"><span data-stu-id="ad35d-163">Return to the Azure AD documentation for instructions:</span></span>

- [<span data-ttu-id="ad35d-164">Atribuir um rótulo a um novo grupo no portal do Azure</span><span class="sxs-lookup"><span data-stu-id="ad35d-164">Assign a label to a new group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)

-  [<span data-ttu-id="ad35d-165">Atribuir um rótulo a um grupo existente no portal do Azure</span><span class="sxs-lookup"><span data-stu-id="ad35d-165">Assign a label to an existing group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

-  <span data-ttu-id="ad35d-166">[Remover um rótulo de um grupo existente no portal do Azure](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="ad35d-166">[Remove a label from an existing group in Azure portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="ad35d-167">Aplicar um rótulo de confidencialidade a uma nova equipe</span><span class="sxs-lookup"><span data-stu-id="ad35d-167">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="ad35d-168">Os usuários podem selecionar os rótulos de confidencialidade ao criar novas equipes no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ad35d-168">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="ad35d-169">Quando eles selecionam o nível de confidencialidade, a configuração de privacidade é alterada conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="ad35d-169">When they select the sensitivity level, the privacy setting changes as necessary.</span></span> <span data-ttu-id="ad35d-170">Dependendo da configuração de acesso de usuários externos que você selecionou para o rótulo, os usuários podem ou não adicionar pessoas de fora da organização à equipe.</span><span class="sxs-lookup"><span data-stu-id="ad35d-170">Depending on the external users access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="ad35d-171">Saiba mais sobre Rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="ad35d-171">Learn more about sensitivity labels for Teams</span></span>](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![A configuração de privacidade ao criar uma nova equipe](../media/privacy-setting-new-team.png)

<span data-ttu-id="ad35d-173">Depois de criar a equipe, o rótulo de confidencialidade aparecerá no canto superior direito de todos os canais.</span><span class="sxs-lookup"><span data-stu-id="ad35d-173">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![O rótulo de confidencialidade aparece na equipe](../media/privacy-setting-teams.png)

<span data-ttu-id="ad35d-175">O serviço aplica automaticamente o mesmo rótulo de confidencialidade ao grupo do Office 365 e ao site de equipe do SharePoint conectado.</span><span class="sxs-lookup"><span data-stu-id="ad35d-175">The service automatically applies the same sensitivity label to the Office 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a><span data-ttu-id="ad35d-176">Aplicar um rótulo de confidencialidade a um novo grupo no Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="ad35d-176">Apply a sensitivity label to a new group in Outlook on the web</span></span>

<span data-ttu-id="ad35d-177">No Outlook na Web, ao criar um novo grupo, você pode selecionar ou alterar a opção de **Confidencialidade** para rótulos publicados:</span><span class="sxs-lookup"><span data-stu-id="ad35d-177">In Outlook on the web, when you create a new group, you can select or change the **Sensitivity** option for published labels:</span></span>

![Criando um grupo e selecionando uma opção em Confidencialidade](../media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="ad35d-179">Aplicar um rótulo de confidencialidade a um novo site</span><span class="sxs-lookup"><span data-stu-id="ad35d-179">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="ad35d-180">Os administradores e os usuários finais podem selecionar os rótulos de confidencialidade ao [criar sites de equipe e sites de comunicação modernos](/sharepoint/create-site-collection).</span><span class="sxs-lookup"><span data-stu-id="ad35d-180">Admins and end users can select sensitivity labels when they [create modern team sites and communication sites](/sharepoint/create-site-collection).</span></span>

<span data-ttu-id="ad35d-181">Quando os usuários criam sites modernos de comunicação e equipe, um rótulo de confidencialidade já estará selecionado por padrão.</span><span class="sxs-lookup"><span data-stu-id="ad35d-181">When users create modern team and communication sites, a sensitivity label is already selected by default.</span></span> <span data-ttu-id="ad35d-182">Os usuários podem selecionar o ícone de ajuda para saber mais sobre os rótulos.</span><span class="sxs-lookup"><span data-stu-id="ad35d-182">Users can select the help icon to learn more about the labels.</span></span>

![Criando um site e selecionando uma opção de confidencialidade](../media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="ad35d-184">Quando os usuários acessam o site, eles podem ver o nome do rótulo e as políticas aplicadas.</span><span class="sxs-lookup"><span data-stu-id="ad35d-184">When users browse to the site, they can see the name of the label and applied policies.</span></span>

![Um site com uma etiqueta de confidencialidade aplicada](../media/sensitivity-label-site.png)

## <a name="view-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="ad35d-186">Exibir os rótulos de confidencialidade no centro de administração do SharePoint</span><span class="sxs-lookup"><span data-stu-id="ad35d-186">View sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="ad35d-187">Para exibir e editar os rótulos de confidencialidade, use a página de **Sites ativos** no novo centro de administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ad35d-187">To view the applied sensitivity labels, use the **Active sites** page in the new SharePoint admin center.</span></span> <span data-ttu-id="ad35d-188">Talvez seja necessário adicionar primeiro a coluna **Confidencialidade**:</span><span class="sxs-lookup"><span data-stu-id="ad35d-188">You might need to first add the **Sensitivity** column:</span></span>

![A coluna Confidencialidade na página sites ativos](../media/manage-site-sensitivity-labels.png)

<span data-ttu-id="ad35d-190">[Saiba mais sobre como gerenciar sites no novo centro de administração do SharePoint](/sharepoint/manage-sites-in-new-admin-center).</span><span class="sxs-lookup"><span data-stu-id="ad35d-190">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="ad35d-191">Alterar as configurações de um título</span><span class="sxs-lookup"><span data-stu-id="ad35d-191">Change site and group settings for a label</span></span>

<span data-ttu-id="ad35d-192">Sempre que você alterar as configurações de site e grupo de um rótulo, deverá executar os seguintes comandos do PowerShell para que suas equipes, sites e grupos possam usar as novas configurações.</span><span class="sxs-lookup"><span data-stu-id="ad35d-192">Whenever you make a change to site and group settings for a label, you must run the following PowerShell commands so that your teams, sites, and groups can use the new settings.</span></span> <span data-ttu-id="ad35d-193">Como prática recomendada, não altere as configurações de site e grupo de um rótulo após aplicá-lo a várias equipes, grupos ou sites.</span><span class="sxs-lookup"><span data-stu-id="ad35d-193">As a best practice, don't the change site and group settings for a label after you've applied the label to several teams, groups, or sites.</span></span>

1. <span data-ttu-id="ad35d-194">Execute os seguintes comandos para se conectar ao PowerShell do Centro de Conformidade e Segurança do Office 365, e obter a lista de rótulos de confidencialidade e seus GUIDs.</span><span class="sxs-lookup"><span data-stu-id="ad35d-194">Run the following commands to connect to Office 365 Security & Compliance Center PowerShell and get the list of sensitivity labels and their GUIDs.</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid
    ```

2. <span data-ttu-id="ad35d-195">Anote o GUID do rótulo ou os rótulos que você alterou.</span><span class="sxs-lookup"><span data-stu-id="ad35d-195">Make a note of the GUID for the label or labels you have changed.</span></span>

3. <span data-ttu-id="ad35d-196">Conecte-se agora ao PowerShell do Exchange Online e execute o cmdlet Get-UnifiedGroup, especificando o GUID do rótulo no lugar do GUID de exemplo de "e48058ea-98e8-4940-8db0-ba1310fd955e":</span><span class="sxs-lookup"><span data-stu-id="ad35d-196">Now connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span> 
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    $Groups= Get-UnifiedGroup | Where {$_.SensitivityLabel  -eq "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

4. <span data-ttu-id="ad35d-197">Para cada grupo, aplique novamente o rótulo de confidencialidade, especificando o GUID do rótulo no lugar do GUID de exemplo de "e48058ea-98e8-4940-8db0-ba1310fd955e":</span><span class="sxs-lookup"><span data-stu-id="ad35d-197">For each group, reapply the sensitivity label, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span>
    
    ```powershell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

## <a name="support-for-the-sensitivity-labels"></a><span data-ttu-id="ad35d-198">Suporte para os rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="ad35d-198">Support for the sensitivity labels</span></span>

<span data-ttu-id="ad35d-199">Você pode usar os rótulos de confidencialidade definidos para as configurações de site e grupo com os seguintes aplicativos e serviços:</span><span class="sxs-lookup"><span data-stu-id="ad35d-199">You can use the sensitivity labels that you've configured for site and group settings with the following apps and services:</span></span>

- <span data-ttu-id="ad35d-200">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ad35d-200">SharePoint Online</span></span>
- <span data-ttu-id="ad35d-201">Teams</span><span class="sxs-lookup"><span data-stu-id="ad35d-201">Teams</span></span>
- <span data-ttu-id="ad35d-202">Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="ad35d-202">Outlook on the web</span></span>
- <span data-ttu-id="ad35d-203">Centro de administração do SharePoint</span><span class="sxs-lookup"><span data-stu-id="ad35d-203">SharePoint admin center</span></span>
- <span data-ttu-id="ad35d-204">Centro de Administração do Microsoft Azure AD</span><span class="sxs-lookup"><span data-stu-id="ad35d-204">Azure AD admin center</span></span>

<span data-ttu-id="ad35d-205">Outros aplicativos e serviços onde você não pode usar atualmente os rótulos de confidencialidade definidos para as configurações de site e grupo incluem:</span><span class="sxs-lookup"><span data-stu-id="ad35d-205">Other apps and services that you can't currently use the sensitivity labels that you've configured for site and group settings include:</span></span>

- <span data-ttu-id="ad35d-206">Outlook para Mac</span><span class="sxs-lookup"><span data-stu-id="ad35d-206">Outlook for the Mac</span></span>
- <span data-ttu-id="ad35d-207">Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="ad35d-207">Outlook mobile</span></span>
- <span data-ttu-id="ad35d-208">Área de trabalho do Outlook para Windows</span><span class="sxs-lookup"><span data-stu-id="ad35d-208">Outlook desktop for Windows</span></span>
- <span data-ttu-id="ad35d-209">Forms</span><span class="sxs-lookup"><span data-stu-id="ad35d-209">Forms</span></span>
- <span data-ttu-id="ad35d-210">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="ad35d-210">Dynamics 365</span></span>
- <span data-ttu-id="ad35d-211">Yammer</span><span class="sxs-lookup"><span data-stu-id="ad35d-211">Yammer</span></span>
- <span data-ttu-id="ad35d-212">Stream</span><span class="sxs-lookup"><span data-stu-id="ad35d-212">Stream</span></span>
- <span data-ttu-id="ad35d-213">Planner</span><span class="sxs-lookup"><span data-stu-id="ad35d-213">Planner</span></span>
- <span data-ttu-id="ad35d-214">Project</span><span class="sxs-lookup"><span data-stu-id="ad35d-214">Project</span></span>
- <span data-ttu-id="ad35d-215">PowerBI</span><span class="sxs-lookup"><span data-stu-id="ad35d-215">PowerBI</span></span>
- <span data-ttu-id="ad35d-216">Centro de administração do Teams</span><span class="sxs-lookup"><span data-stu-id="ad35d-216">Teams admin center</span></span>
- <span data-ttu-id="ad35d-217">Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ad35d-217">Microsoft 365 admin center</span></span>
- <span data-ttu-id="ad35d-218">Centro de administração do Exchange</span><span class="sxs-lookup"><span data-stu-id="ad35d-218">Exchange admin center</span></span>


## <a name="classic-azure-ad-site-classification"></a><span data-ttu-id="ad35d-219">Classificação de site clássica do Azure AD</span><span class="sxs-lookup"><span data-stu-id="ad35d-219">Classic Azure AD site classification</span></span>

<span data-ttu-id="ad35d-220">O Office 365 já não será mais compatível com as classificações antigas para novos grupos e sites do SharePoint quando você habilitar essa visualização.</span><span class="sxs-lookup"><span data-stu-id="ad35d-220">Office 365 no longer supports the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="ad35d-221">No entanto, grupos e sites existentes ainda exibem as classificações antigas, a menos que você as converta para usar rótulos de confidencialidade.</span><span class="sxs-lookup"><span data-stu-id="ad35d-221">However, existing groups and sites still display the old classifications unless you convert them to use sensitivity labels.</span></span> <span data-ttu-id="ad35d-222">As classificações antigas incluem a classificação de sites "modernos" que você configurou, possivelmente por meio do Azure AD PowerShell ou da biblioteca PnP Core, que definiu valores para a configuração do `ClassificationList`.</span><span class="sxs-lookup"><span data-stu-id="ad35d-222">Old classifications include the "modern" sites classification you set up, possibly through Azure AD PowerShell or the PnP Core library, that defined values for the `ClassificationList` setting.</span></span>

<span data-ttu-id="ad35d-223">Por exemplo, no PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ad35d-223">For example, in PowerShell:</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="ad35d-224">Para obter mais informações sobre o método antigo de classificação, confira [Classificação de sites "modernos" do SharePoint](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span><span class="sxs-lookup"><span data-stu-id="ad35d-224">For more information about the old classification method, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="ad35d-225">Para converter suas classificações antigas em rótulos de confidencialidade, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="ad35d-225">To convert your old classifications to sensitivity labels, do one of the following:</span></span>

- <span data-ttu-id="ad35d-226">Usar rótulos existentes: Especifique as configurações de rótulo desejadas para sites e grupos editando rótulos de confidencialidade existentes que já foram publicados.</span><span class="sxs-lookup"><span data-stu-id="ad35d-226">Use existing labels: Specify the label settings you want for sites and groups by editing existing sensitivity labels that are already published.</span></span>

- <span data-ttu-id="ad35d-227">Criar novos rótulos: Especifique as configurações de rótulos desejados para sites e grupos, criando e publicando novos rótulos de confidencialidade que tenham os mesmos nomes das suas classificações existentes.</span><span class="sxs-lookup"><span data-stu-id="ad35d-227">Create new labels: Specify the label settings you want for sites and groups by creating and publishing new sensitivity labels that have the same names as your existing classifications.</span></span>

<span data-ttu-id="ad35d-228">Depois:</span><span class="sxs-lookup"><span data-stu-id="ad35d-228">Then:</span></span> 

1. <span data-ttu-id="ad35d-229">Use o PowerShell para aplicar os novos rótulos de confidencialidade a grupos existentes do Office 365 e a sites do SharePoint usando mapeamento de nomes.</span><span class="sxs-lookup"><span data-stu-id="ad35d-229">Use PowerShell to apply the sensitivity labels to existing Office 365 groups and SharePoint sites by using name mapping.</span></span> <span data-ttu-id="ad35d-230">Confira a seção a seguir para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="ad35d-230">See the next section for instructions.</span></span>

2. <span data-ttu-id="ad35d-231">Remova as classificações antigas dos grupos e sites existentes.</span><span class="sxs-lookup"><span data-stu-id="ad35d-231">Remove the old classifications from the existing groups and sites.</span></span>

<span data-ttu-id="ad35d-232">Embora você não possa impedir que os usuários criem novos grupos em aplicativos e serviços que ainda não suportam rótulos de confidencialidade, é possível executar um script recorrente do PowerShell para procurar novos grupos que os usuários criaram com as classificações antigas e convertê-los para uso de rótulos de confidencialidade.</span><span class="sxs-lookup"><span data-stu-id="ad35d-232">Although you can't prevent users from creating new groups in apps and services that don't yet support sensitivity labels, you can run a recurring PowerShell script to look for new groups that users have created with the old classifications, and convert these to use sensitivity labels.</span></span> 

#### <a name="use-powershell-to-convert-classifications-for-office-365-groups-to-sensitivity-labels"></a><span data-ttu-id="ad35d-233">Usar o PowerShell para converter classificações de grupos do Office 365 em rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="ad35d-233">Use PowerShell to convert classifications for Office 365 groups to sensitivity labels</span></span>

1. <span data-ttu-id="ad35d-234">Verifique se você está executando o Shell de Gerenciamento do SharePoint Online, versão 16.0.19418.12000 ou superior.</span><span class="sxs-lookup"><span data-stu-id="ad35d-234">Ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or above.</span></span> <span data-ttu-id="ad35d-235">Se você já tiver a versão mais recente, vá para a etapa 4.</span><span class="sxs-lookup"><span data-stu-id="ad35d-235">If you already have the latest version, skip to step 4.</span></span>

2. <span data-ttu-id="ad35d-236">Se você tiver instalado uma versão anterior do Shell de Gerenciamento do SharePoint Online na galeria do PowerShell, poderá atualizar o módulo executando o cmdlet a seguir.</span><span class="sxs-lookup"><span data-stu-id="ad35d-236">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>
    
    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

3. <span data-ttu-id="ad35d-237">Se você tiver instalado uma versão anterior do Shell de Gerenciamento do SharePoint Online no Centro de Download da Microsoft, vá para **Adicionar ou remover programas** e desinstale o Shell de Gerenciamento do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ad35d-237">If you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span> <span data-ttu-id="ad35d-238">Em seguida, instale o Shell de Gerenciamento do SharePoint Online mais recente no [Centro de Download](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="ad35d-238">Then, install the latest SharePoint Online Management Shell from the [Download Center](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="ad35d-239">Usando uma conta corporativa ou de estudante com privilégios de administrador global ou de administrador do SharePoint no Office 365, conecte-se ao Shell de gerenciamento do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ad35d-239">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint Online Management Shell.</span></span> <span data-ttu-id="ad35d-240">Veja como em [Introdução ao Shell de Gerenciamento do SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="ad35d-240">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

5. <span data-ttu-id="ad35d-241">Execute o seguinte comando para obter a lista de rótulos de confidencialidade e seus GUIDs.</span><span class="sxs-lookup"><span data-stu-id="ad35d-241">Run the following commands to get the list of sensitivity labels and their GUIDs.</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

6. <span data-ttu-id="ad35d-242">Anote os GUIDs dos rótulos de confidencialidade que você deseja aplicar aos grupos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ad35d-242">Make a note of the GUIDs for the sensitivity labels you want to apply to your Office 365 groups.</span></span>

7. <span data-ttu-id="ad35d-243">Use o seguinte comando como exemplo para obter a lista de grupos que atualmente têm a classificação "Geral":</span><span class="sxs-lookup"><span data-stu-id="ad35d-243">Use the following command as an example to get the list of groups that currently have the classification of "General":</span></span>

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. <span data-ttu-id="ad35d-244">Para cada grupo, adicione o novo GUID de rótulo de confidencialidade.</span><span class="sxs-lookup"><span data-stu-id="ad35d-244">For each group, add the new sensitivity label GUID.</span></span> <span data-ttu-id="ad35d-245">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ad35d-245">For example:</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

## <a name="auditing-sensitivity-label-activities"></a><span data-ttu-id="ad35d-246">Atividades de rótulo de confidencialidade de auditoria</span><span class="sxs-lookup"><span data-stu-id="ad35d-246">Auditing sensitivity label activities</span></span>

<span data-ttu-id="ad35d-247">Se alguém enviar um documento para um site protegido por um rótulo de confidencialidade e o documento tiver um rótulo de confidencialidade com [prioridade mais alta](sensitivity-labels.md#label-priority-order-matters) que o rótulo de confidencialidade aplicado ao site, essa ação não será bloqueada.</span><span class="sxs-lookup"><span data-stu-id="ad35d-247">If somebody uploads a document to a site that's protected with a sensitivity label and their document has a [higher priority](sensitivity-labels.md#label-priority-order-matters) sensitivity label than the sensitivity label applied to the site, this action isn't blocked.</span></span> <span data-ttu-id="ad35d-248">Por exemplo, você aplicou o rótulo **Geral** a um site do SharePoint e alguém carrega neste site um documento chamado **Confidencial**.</span><span class="sxs-lookup"><span data-stu-id="ad35d-248">For example, you've applied the **General** label to a SharePoint site, and somebody uploads to this site a document labeled **Confidential**.</span></span> <span data-ttu-id="ad35d-249">Como um rótulo de confidencialidade com prioridade mais alta identifica o conteúdo que é mais confidencial do que o conteúdo com ordem de prioridade mais baixa, essa situação pode ser um problema de segurança.</span><span class="sxs-lookup"><span data-stu-id="ad35d-249">Because a sensitivity label with a higher priority identifies content that is more sensitivity than content that has a lower priority order, this situation could be a security concern.</span></span>

<span data-ttu-id="ad35d-250">Embora a ação não seja bloqueada, ela é auditada, para que você possa identificar documentos com esse desalinhamento da prioridade do rótulo e tomar medidas, se necessário.</span><span class="sxs-lookup"><span data-stu-id="ad35d-250">Although the action isn't blocked, it is audited, so you can identify documents that have this misalignment of label priority and take action if needed.</span></span> <span data-ttu-id="ad35d-251">Por exemplo, excluir ou mover o documento carregado do site.</span><span class="sxs-lookup"><span data-stu-id="ad35d-251">For example, delete or move the uploaded document from the site.</span></span> 

<span data-ttu-id="ad35d-252">Não seria um problema de segurança se o documento tivesse um rótulo de confidencialidade de prioridade mais baixa que o rótulo de confidencialidade aplicado ao site.</span><span class="sxs-lookup"><span data-stu-id="ad35d-252">It wouldn't be a security concern if the document has a lower priority sensitivity label than the sensitivity label applied to the site.</span></span> <span data-ttu-id="ad35d-253">Por exemplo, um documento chamado **Geral** é carregado em um site chamado **Confidencial**.</span><span class="sxs-lookup"><span data-stu-id="ad35d-253">For example, a document labeled **General** is uploaded to a site labeled **Confidential**.</span></span> <span data-ttu-id="ad35d-254">Neste cenário, um evento de auditoria não é gerado.</span><span class="sxs-lookup"><span data-stu-id="ad35d-254">In this scenario, an auditing event isn't generated.</span></span>

<span data-ttu-id="ad35d-255">Para pesquisar o log de auditoria para esse evento, procure por **Incompatibilidade de confidencialidade em documento detectada** na categoria **Atividades de arquivo e página**.</span><span class="sxs-lookup"><span data-stu-id="ad35d-255">To search the audit log for this event, look for **Detected document sensitivity mismatch** from the **File and page activities** category.</span></span> 

<span data-ttu-id="ad35d-256">Quando alguém adiciona ou remove um rótulo de confidencialidade para ou de um site ou grupo, essas atividades também são auditadas.</span><span class="sxs-lookup"><span data-stu-id="ad35d-256">When somebody adds or removes a sensitivity label to or from a site or group, these activities are also audited.</span></span> <span data-ttu-id="ad35d-257">Esses eventos podem ser encontrados na categoria [Atividades de rótulo de confidencialidade](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities).</span><span class="sxs-lookup"><span data-stu-id="ad35d-257">These events can be found in the [Sensitivity label activities](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) category.</span></span> 

<span data-ttu-id="ad35d-258">Para obter instruções sobre como pesquisar o log de auditoria, confira [Pesquisar o log de auditoria no Centro de Conformidade e Segurança](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="ad35d-258">For instructions to search the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="troubleshoot-sensitivity-label-deployment"></a><span data-ttu-id="ad35d-259">Solucionar problemas de implantação de rótulo de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="ad35d-259">Troubleshoot sensitivity label deployment</span></span>

<span data-ttu-id="ad35d-260">Está tendo problemas com os rótulos de confidencialidade do Microsoft Teams, grupos do Office 365 e sites do SharePoint?</span><span class="sxs-lookup"><span data-stu-id="ad35d-260">Having problems with sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites?</span></span> <span data-ttu-id="ad35d-261">Verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ad35d-261">Check the following:</span></span>

### <a name="labels-not-visible-after-publishing"></a><span data-ttu-id="ad35d-262">Rótulos não visíveis após a publicação</span><span class="sxs-lookup"><span data-stu-id="ad35d-262">Labels not visible after publishing</span></span>
<span data-ttu-id="ad35d-263">Se você tiver problemas ao criar uma equipe ou grupo do Office 365 depois de habilitar essas configurações ou modificar a descrição de um rótulo de confidencialidade, aguarde algumas horas após salvar as alterações no rótulo e tente criar a equipe ou grupo novamente.</span><span class="sxs-lookup"><span data-stu-id="ad35d-263">If you experience issues when you create a team or Office 365 group after you enable these settings or modify a sensitivity label's description, wait a few hours after saving the label changes, and then try to create the team or group again.</span></span> <span data-ttu-id="ad35d-264">Para saber mais, confira [Agendar a distribuição após criar ou alterar um rótulo de confidencialidade](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span><span class="sxs-lookup"><span data-stu-id="ad35d-264">For information, see [Schedule roll-out after you create or change a sensitivity label](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span></span>

<span data-ttu-id="ad35d-265">Se você ainda não conseguir ver o novo rótulo de confidencialidade do SharePoint Online, contate o [suporte da Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="ad35d-265">If you are still not able to see the new sensitivity label from SharePoint Online, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

### <a name="team-group-or-sharepoint-site-creation-errors"></a><span data-ttu-id="ad35d-266">Erros de criação de site de equipe, grupo ou SharePoint</span><span class="sxs-lookup"><span data-stu-id="ad35d-266">Team, group, or SharePoint site creation errors</span></span>
<span data-ttu-id="ad35d-267">Se ocorrerem erros de criação durante a visualização pública, você tem duas opções:</span><span class="sxs-lookup"><span data-stu-id="ad35d-267">If you experience creation errors during the public preview, you have two options:</span></span>

- <span data-ttu-id="ad35d-268">Certifique-se de que os rótulos de confidencialidade não sejam obrigatórios para qualquer usuário.</span><span class="sxs-lookup"><span data-stu-id="ad35d-268">Ensure that sensitivity labels are not mandatory for any user.</span></span>

- <span data-ttu-id="ad35d-269">Você pode desativar os rótulos de confidencialidade do Microsoft Teams, grupos do Office 365 e sites do SharePoint usando as mesmas instruções em [Habilitar o suporte a rótulo de confidencialidade no PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span><span class="sxs-lookup"><span data-stu-id="ad35d-269">You can turn off sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites by using the same instructions from [Enable sensitivity label support in PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span></span> <span data-ttu-id="ad35d-270">No entanto, para desabilitar a visualização, na etapa 5, desabilite o recurso usando o `$setting["EnableMIPLabels"] = "False"`.</span><span class="sxs-lookup"><span data-stu-id="ad35d-270">However, to disable the preview, in step 5, disable the feature by using `$setting["EnableMIPLabels"] = "False"`.</span></span>

