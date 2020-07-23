---
title: Use rótulos de confidencialidade do Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint
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
description: Use rótulos de confidencialidade para proteger o conteúdo nos sites do SharePoint, Microsoft Teams e grupos do Microsoft 365.
ms.openlocfilehash: b9168320b5764a3d7ed4e1570c32f0f35ccbc44d
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/21/2020
ms.locfileid: "45199621"
---
# <a name="use-sensitivity-labels-to-protect-content-in-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a><span data-ttu-id="398d1-103">Use rótulos de confidencialidade para proteger o conteúdo do Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint</span><span class="sxs-lookup"><span data-stu-id="398d1-103">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>

><span data-ttu-id="398d1-104">*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="398d1-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="398d1-105">Além de usar [rótulos de confidencialidade](sensitivity-labels.md) para classificar e proteger documentos e emails, você também pode usar rótulos de confidencialidade para proteger o conteúdo nos seguintes contêineres: sites de Microsoft Teams, grupos de Microsoft 365 groups ([antigos grupos do Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) e sites do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="398d1-105">In addition to using [sensitivity labels](sensitivity-labels.md) to classify and protect documents and emails, you can also use sensitivity labels to protect content in the following containers: Microsoft Teams sites, Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)), and SharePoint sites.</span></span> <span data-ttu-id="398d1-106">Para a classificação e a proteção de nível de contêiner, use as seguintes configurações de etiqueta:</span><span class="sxs-lookup"><span data-stu-id="398d1-106">For this container-level classification and protection, use the following label settings:</span></span>

- <span data-ttu-id="398d1-107">Privacidade (pública ou privada) dos sites de equipes conectadas ao grupo do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="398d1-107">Privacy (public or private) of Microsoft 365 group-connected teams sites</span></span>
- <span data-ttu-id="398d1-108">Acesso de usuários externos</span><span class="sxs-lookup"><span data-stu-id="398d1-108">External users access</span></span>
- <span data-ttu-id="398d1-109">Acesso de dispositivos não gerenciados</span><span class="sxs-lookup"><span data-stu-id="398d1-109">Access from unmanaged devices</span></span> 

<span data-ttu-id="398d1-110">Quando você aplica esse rótulo de confidencialidade a um contêiner suportado, o rótulo aplica automaticamente as opções configuradas ao site ou grupo conectado.</span><span class="sxs-lookup"><span data-stu-id="398d1-110">When you apply this sensitivity label to a supported container, the label automatically applies the classification and protection settings to the connected site or group.</span></span>

<span data-ttu-id="398d1-111">O conteúdo desses contêineres, no entanto, não herda os rótulos da classificação e configurações como marcações visuais ou criptografia.</span><span class="sxs-lookup"><span data-stu-id="398d1-111">Content in these containers however, do not inherit the labels for the classification and settings such as visual markings, or encryption.</span></span> <span data-ttu-id="398d1-112">Para que os usuários possam rotular seus documentos em sites do SharePoint ou em sites de equipe, [habilite rótulos de confidencialidade para arquivos do Office no Microsoft Office SharePoint Online e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="398d1-112">So that users can label their documents in SharePoint sites or team sites, make sure you've [enabled sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

> [!NOTE]
> <span data-ttu-id="398d1-113">Os rótulos de confidencialidade de contêineres não têm suporte com o CDNs (redes de distribuição de conteúdo) do Office 365.</span><span class="sxs-lookup"><span data-stu-id="398d1-113">Sensitivity labels for containers aren't supported with Office 365 Content Delivery Networks (CDNs).</span></span>

## <a name="using-sensitivity-labels-for-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a><span data-ttu-id="398d1-114">Use rótulos de confidencialidade para Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint</span><span class="sxs-lookup"><span data-stu-id="398d1-114">Using sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="398d1-115">Antes de habilitar os rótulos de confidencialidade para contêineres e configurar rótulos de confidencialidade para as novas configurações, os usuários podem ver e aplicar rótulos de confidencialidade em seus aplicativos.</span><span class="sxs-lookup"><span data-stu-id="398d1-115">Before you enable sensitivity labels for containers and configure sensitivity labels for the new settings, users can see and apply sensitivity labels in their apps.</span></span> <span data-ttu-id="398d1-116">Por exemplo, no Word:</span><span class="sxs-lookup"><span data-stu-id="398d1-116">For example, from Word:</span></span>

![Um rótulo de confidencialidade exibido no aplicativo Word para área de trabalho](../media/sensitivity-label-word.png)

<span data-ttu-id="398d1-118">Depois de habilitar e configurar os rótulos de confidencialidade para os contêineres, os usuários também podem ver e aplicar rótulos de confidencialidade ao Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="398d1-118">After you enable and configure sensitivity labels for containers, users can additionally see and apply sensitivity labels to Microsoft team sites, Microsoft 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="398d1-119">Por exemplo, quando você cria um novo site de equipe no SharePoint:</span><span class="sxs-lookup"><span data-stu-id="398d1-119">For example, when you create a new team site from SharePoint:</span></span>

![Um rótulo de confidencialidade ao criar um site de equipe do SharePoint](../media/sensitivity-labels-new-team-site.png)

## <a name="how-to-enable-sensitivity-labels-for-containers-and-synchronize-labels"></a><span data-ttu-id="398d1-121">Como habilitar rótulos de confidencialidade para contêineres e sincronizar rótulos</span><span class="sxs-lookup"><span data-stu-id="398d1-121">How to enable sensitivity labels for containers and synchronize labels</span></span>

1. <span data-ttu-id="398d1-122">Como esse recurso usa a funcionalidade do Azure Active Directory, siga as instruções na documentação do Azure Active Directory para habilitar o suporte de rótulos de confidencialidade: [Atribuir rótulos de confidencialidade aos grupos do Microsoft 365 no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="398d1-122">Because this feature uses Azure AD functionality, follow the instructions from the Azure AD documentation to enable sensitivity label support: [Assign sensitivity labels to Microsoft 365 groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span></span>

2. <span data-ttu-id="398d1-123">Agora, você precisa sincronizar seus rótulos de sensibilidade com o Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="398d1-123">You now need to synchronize your sensitivity labels to Azure AD.</span></span> <span data-ttu-id="398d1-124">Primeiro, [conecte-se ao PowerShell do Centro de Conformidade e Segurança do Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="398d1-124">First, [connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span> 
    
    <span data-ttu-id="398d1-125">Por exemplo, em uma sessão do PowerShell que você executa como administrador, entre com uma conta de administrador global:</span><span class="sxs-lookup"><span data-stu-id="398d1-125">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

3. <span data-ttu-id="398d1-126">Execute o seguinte comando para assegurar seus rótulos de confidencialidade possam ser usados com os grupos do Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="398d1-126">Then run the following command to ensure your sensitivity labels can be used with Microsoft 365 groups:</span></span>
    
    ```powershell
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-site-and-group-settings"></a><span data-ttu-id="398d1-127">Como definir as configurações de site e grupo</span><span class="sxs-lookup"><span data-stu-id="398d1-127">How to configure site and group settings</span></span>

<span data-ttu-id="398d1-128">Agora você está pronto para criar ou editar os rótulos de confidencialidade que deseja disponibilizar para sites e grupos.</span><span class="sxs-lookup"><span data-stu-id="398d1-128">You're now ready to create or edit sensitivity labels that you want to be available for sites and groups.</span></span> <span data-ttu-id="398d1-129">Habilitar os rótulos de confidencialidade para contêineres torna uma nova página visível nas assistentes de rotulagem de confidencialidade: **Configurações de site e grupo**</span><span class="sxs-lookup"><span data-stu-id="398d1-129">Enabling sensitivity labels for containers makes a new page visible in the sensitivity labeling wizards: **Site and group settings**</span></span>

<span data-ttu-id="398d1-130">Se precisar de ajuda para criar ou editar um rótulo de confidencialidade, confira as instruções em [Criar e configurar os rótulos de confidencialidade](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="398d1-130">If you need help with creating or editing a sensitivity label, see the instructions from [Create and configure sensitivity labels](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span></span>

<span data-ttu-id="398d1-131">Nesta nova página **Configurações de site e grupo**, defina as configurações:</span><span class="sxs-lookup"><span data-stu-id="398d1-131">On this new **Site and group settings** page, configure the settings:</span></span>

- <span data-ttu-id="398d1-132">**Privacidade dos sites de equipes conectados ao grupo do Office 365**: Manter a configuração padrão de \*\*Público - qualquer pessoa em sua organização pode acessar o site \*\*se você quiser que todos na sua organização acessem o site de equipe ou grupo no qual o rótulo foi aplicado.</span><span class="sxs-lookup"><span data-stu-id="398d1-132">**Privacy of Office 365 group-connected teams sites**: Keep the default of **Public - anyone in the organization can access the site** if you want anyone in your organization to access the team site or group where this label is applied.</span></span>
    
    <span data-ttu-id="398d1-133">Selecione **Particular** se desejar que o acesso seja restrito apenas a membros aprovados da sua organização.</span><span class="sxs-lookup"><span data-stu-id="398d1-133">Select **Private** if you want access to be restricted to only approved members in your organization.</span></span>
    
    <span data-ttu-id="398d1-134">Selecione **Nenhuma - permita que o usuário tenha acesso ao site** quando desejar proteger o conteúdo do contêiner usando o rótulo de confidencialidade, mas ainda permita que os usuários configurem a própria configuração de privacidade.</span><span class="sxs-lookup"><span data-stu-id="398d1-134">Select **None - let user chose who can access the site** when you want to protect content in the container by using the sensitivity label, but still let users configure the privacy setting themselves.</span></span>
    
    <span data-ttu-id="398d1-135">Selecione **Pública** ou **Privada** para definir e bloquear a configuração de privacidade quando você aplicar esse rótulo ao contêiner.</span><span class="sxs-lookup"><span data-stu-id="398d1-135">The settings of **Public** or **Private** set and lock the privacy setting when you apply this label to the container.</span></span> <span data-ttu-id="398d1-136">A configuração escolhida substituirá qualquer configuração de privacidade anterior que possa ser configurada para a equipe ou grupo, e bloqueará o valor de privacidade para que ele possa ser alterado apenas pela primeira remoção da etiqueta de confidencialidade do contêiner.</span><span class="sxs-lookup"><span data-stu-id="398d1-136">Your chosen setting replaces any previous privacy setting that might be configured for the team or group, and locks the privacy value so it can be changed only by first removing the sensitivity label from the container.</span></span> <span data-ttu-id="398d1-137">Depois de remover o rótulo de confidencialidade, a configuração de privacidade do rótulo permanece e os usuários agora podem alterá-lo novamente.</span><span class="sxs-lookup"><span data-stu-id="398d1-137">After you remove the sensitivity label, the privacy setting from the label remains and users can now change it again.</span></span>

- <span data-ttu-id="398d1-138">**Acesso de usuários externos**: Controle se o proprietário do grupo pode [adicionar convidados ao grupo](/office365/admin/create-groups/manage-guest-access-in-groups).</span><span class="sxs-lookup"><span data-stu-id="398d1-138">**External users access**: Control whether the group owner can [add guests to the group](/office365/admin/create-groups/manage-guest-access-in-groups).</span></span>

- <span data-ttu-id="398d1-139">**Dispositivos não gerenciados**: Para [dispositivos não gerenciados](/sharepoint/control-access-from-unmanaged-devices), permita acesso total, acesso somente Web ou bloqueio total de acesso.</span><span class="sxs-lookup"><span data-stu-id="398d1-139">**Unmanaged devices**: For [unmanaged devices](/sharepoint/control-access-from-unmanaged-devices), allow full access, web only access, or block access completely.</span></span> <span data-ttu-id="398d1-140">Se você definiu essa configuração no nível do locatário ou em um site específico, a configuração especificada aqui será aplicada apenas se for mais restritiva.</span><span class="sxs-lookup"><span data-stu-id="398d1-140">If you have configured this setting at the tenant level or for a specific site, the setting you specify here will be applied only if it's more restrictive.</span></span>

![Guia configurações de site e grupo](../media/edit-sensitivity-label-site-group2.png)

> [!IMPORTANT]
> <span data-ttu-id="398d1-142">Somente essas configurações de site e grupo entrarão em vigor quando você aplicar um rótulo a uma equipe, grupo ou site.</span><span class="sxs-lookup"><span data-stu-id="398d1-142">Only these site and group settings take effect when you apply the label to a team, group, or site.</span></span> <span data-ttu-id="398d1-143">Outras configurações de rótulo, como criptografia e marcação de conteúdo, não são aplicadas ao conteúdo da equipe, grupo ou site.</span><span class="sxs-lookup"><span data-stu-id="398d1-143">Other label settings, such as encryption and content marking, aren't applied to the content within the team, group, or site.</span></span>
> 
> <span data-ttu-id="398d1-144">Implementação gradual para locatários: Somente os rótulos com as configurações de site e grupo estarão disponíveis para seleção quando os usuários criarem equipes, grupos e sites.</span><span class="sxs-lookup"><span data-stu-id="398d1-144">Gradually rolling out to tenants: Only labels with the site and group settings will be available to select when users create teams, groups, and sites.</span></span> <span data-ttu-id="398d1-145">Se você pode aplicar um rótulo a um contêiner quando o rótulo não possui as configurações de site e grupo ativadas, apenas o nome do rótulo é aplicado ao contêiner.</span><span class="sxs-lookup"><span data-stu-id="398d1-145">If you can currently apply a label to a container when the label doesn't have the site and group settings enabled, only the label name is applied to the container.</span></span>

<span data-ttu-id="398d1-146">Se o seu rótulo de confidencialidade ainda não estiver publicado, publique-o agora [adicionando-o a uma política de rótulo de confidencialidade](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span><span class="sxs-lookup"><span data-stu-id="398d1-146">If your sensitivity label isn't already published, now publish it by [adding it to a sensitivity label policy](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span> <span data-ttu-id="398d1-147">Os usuários aos quais tenha sido atribuída uma política de rótulo de confidencialidade que inclua esse rótulo poderão selecioná-lo para sites e grupos.</span><span class="sxs-lookup"><span data-stu-id="398d1-147">The users who are assigned a sensitivity label policy that includes this label will be able to select it for sites and groups.</span></span>

<span data-ttu-id="398d1-148">Na política de rótulo, apenas a configuração de política **Aplicar esta etiqueta por padrão aos documentos e o email** é válida quando você aplica esse rótulo aos contêineres.</span><span class="sxs-lookup"><span data-stu-id="398d1-148">From the label policy, only the policy setting **Apply this label by default to documents and email** is applicable when you apply this label to containers.</span></span> <span data-ttu-id="398d1-149">Outras configurações de política não são aplicadas, as que incluem rotulagem obrigatória, exigindo justificativa do usuário e um link para a página de ajuda personalizada.</span><span class="sxs-lookup"><span data-stu-id="398d1-149">Other policy settings are not applied, which include mandatory labeling, requiring user justification, and a link to the custom help page.</span></span>

## <a name="sensitivity-label-management"></a><span data-ttu-id="398d1-150">Gerenciamento de rótulo de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="398d1-150">Sensitivity label management</span></span>

<span data-ttu-id="398d1-151">Use as diretrizes a seguir para criar, modificar ou excluir rótulos de confidencialidade que estão configurados para sites e grupos.</span><span class="sxs-lookup"><span data-stu-id="398d1-151">Use the following guidance for when you create, modify, or delete sensitivity labels that are configured for sites and groups.</span></span>

### <a name="creating-and-publishing-labels-that-are-configured-for-sites-and-groups"></a><span data-ttu-id="398d1-152">Criar e publicar rótulos configurados para sites e grupos</span><span class="sxs-lookup"><span data-stu-id="398d1-152">Creating and publishing labels that are configured for sites and groups</span></span>

<span data-ttu-id="398d1-153">Quando um novo rótulo de confidencialidade é criado e publicado, torna-se visível para os usuários em equipes, grupos e sites dentro de uma hora.</span><span class="sxs-lookup"><span data-stu-id="398d1-153">When a new sensitivity label is created and published, it's visible for users in teams, groups, and sites within one hour.</span></span> <span data-ttu-id="398d1-154">No entanto, se tiver modificado um rótulo existente será preciso aguardar até 24 horas.</span><span class="sxs-lookup"><span data-stu-id="398d1-154">However, if you modify an existing label, allow up to 24 hours.</span></span> <span data-ttu-id="398d1-155">Use as diretrizes a seguir para publicar um rótulo para seus usuários quando esse rótulo estiver configurado para as configurações de site e de grupo:</span><span class="sxs-lookup"><span data-stu-id="398d1-155">Use the following guidance to publish a label for your users when that label is configured for site and group settings:</span></span>

1. <span data-ttu-id="398d1-156">Depois de criar e configurar o rótulo de confidencialidade, adicione esse rótulo a uma política de rótulo que se aplica a apenas alguns usuários de teste.</span><span class="sxs-lookup"><span data-stu-id="398d1-156">After you create and configure the sensitivity label, add this label to a label policy that applies to just a few test users.</span></span>

2. <span data-ttu-id="398d1-157">Aguarde o seguinte prazo para que a alteração seja replicada:</span><span class="sxs-lookup"><span data-stu-id="398d1-157">Wait for the change to replicate:</span></span>
    - <span data-ttu-id="398d1-158">Rótulo novo: aguarde uma hora.</span><span class="sxs-lookup"><span data-stu-id="398d1-158">New label: Wait for one hour.</span></span>
    - <span data-ttu-id="398d1-159">Rótulo existente: aguarde 24 horas.</span><span class="sxs-lookup"><span data-stu-id="398d1-159">Existing label: Wait for 24 hours.</span></span>

3. <span data-ttu-id="398d1-160">Após esse período de espera, use uma das contas de usuário de teste para criar uma equipe, grupo do Microsoft 365 ou site do SharePoint com o rótulo que você criou na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="398d1-160">After this wait period, use one of the test user accounts to create a team, Microsoft 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="398d1-161">Se não houver erros durante a operação de criação, você saberá que é seguro publicar o rótulo para todos os usuários em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="398d1-161">If there are no errors during this creation operation, you know it's safe to publish the label to all users in your tenant.</span></span>

### <a name="modifying-published-labels-that-are-configured-for-sites-and-groups"></a><span data-ttu-id="398d1-162">Modificar rótulos publicados que estão configurados para sites e grupos</span><span class="sxs-lookup"><span data-stu-id="398d1-162">Modifying published labels that are configured for sites and groups</span></span>

<span data-ttu-id="398d1-163">Como prática recomendada, não altere as configurações de site e grupo de um rótulo de confidencialidade após aplicá-lo a várias equipes, grupos ou sites.</span><span class="sxs-lookup"><span data-stu-id="398d1-163">As a best practice, don't change the site and group settings for a sensitivity label after the label has been applied to teams, groups, or sites.</span></span> <span data-ttu-id="398d1-164">Se decidir fazer isso, lembre-se de aguardar até 24 horas para que as alterações sejam replicadas para todos os contêineres que têm o rótulo aplicado.</span><span class="sxs-lookup"><span data-stu-id="398d1-164">If you do, remember to wait for 24 hours for the changes to replicate to all containers that have the label applied.</span></span> 

<span data-ttu-id="398d1-165">Além disso, se suas alterações incluírem a configuração de **Acesso de usuários externos**:</span><span class="sxs-lookup"><span data-stu-id="398d1-165">In addition, if your changes include the **External users access** setting:</span></span>

- <span data-ttu-id="398d1-166">A nova configuração aplica-se a novos usuários, mas não a usuários existentes.</span><span class="sxs-lookup"><span data-stu-id="398d1-166">The new setting applies to new users but not to existing users.</span></span> <span data-ttu-id="398d1-167">Por exemplo, se essa configuração tiver sido selecionada anteriormente e, como resultado, os usuários convidados acessarem o site. esses usuários convidados ainda poderão acessar o site depois que essa configuração for limpa na configuração do rótulo.</span><span class="sxs-lookup"><span data-stu-id="398d1-167">For example, if this setting was previously selected and as a result, guest users accessed the site, these guest users can still access the site after this setting is cleared in the label configuration.</span></span>

- <span data-ttu-id="398d1-168">As configurações de privacidade para as propriedades do grupo hiddenMembership e roleEnabled não são atualizadas.</span><span class="sxs-lookup"><span data-stu-id="398d1-168">The privacy settings for the group properties hiddenMembership and roleEnabled aren't updated.</span></span>


### <a name="deleting-published-labels-that-are-configured-for-sites-and-groups"></a><span data-ttu-id="398d1-169">Excluindo rótulos publicados que estão configurados para sites e grupos</span><span class="sxs-lookup"><span data-stu-id="398d1-169">Deleting published labels that are configured for sites and groups</span></span>

<span data-ttu-id="398d1-170">Se você excluir um rótulo de confidencialidade com as configurações de site e grupo ativadas e esse rótulo estiver incluído em uma ou mais políticas de rótulo, essas ações poderão resultar em falhas na criação de todas as equipes, grupos e sites.</span><span class="sxs-lookup"><span data-stu-id="398d1-170">If you delete a sensitivity label that has the site and group settings enabled, and that label is included in one or more label policies, this action can result in creation failures for new teams, groups, and sites.</span></span> <span data-ttu-id="398d1-171">Para evitar essa situação, use as instruções a seguir:</span><span class="sxs-lookup"><span data-stu-id="398d1-171">To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="398d1-172">Remova o rótulo de confidencialidade de todas as políticas de rótulo que incluam o rótulo.</span><span class="sxs-lookup"><span data-stu-id="398d1-172">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="398d1-173">Aguarde uma hora.</span><span class="sxs-lookup"><span data-stu-id="398d1-173">Wait for one hour.</span></span>

3. <span data-ttu-id="398d1-174">Após esse período de espera, tente criar uma equipe, grupo ou site e confirme se o rótulo não está mais visível.</span><span class="sxs-lookup"><span data-stu-id="398d1-174">After this wait period, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="398d1-175">Se a etiqueta de confidencialidade não estiver visível, agora você pode excluí-la com segurança.</span><span class="sxs-lookup"><span data-stu-id="398d1-175">If the sensitivity label isn't visible, you can now safely delete the label.</span></span>

## <a name="how-to-apply-sensitivity-labels-to-containers"></a><span data-ttu-id="398d1-176">Como aplicar rótulos de confidencialidade aos contêineres</span><span class="sxs-lookup"><span data-stu-id="398d1-176">How to apply sensitivity labels to containers</span></span>

<span data-ttu-id="398d1-177">Agora você está pronto para aplicar os rótulos ou rótulos de confidencialidade aos seguintes contêineres:</span><span class="sxs-lookup"><span data-stu-id="398d1-177">You're now ready to apply the sensitivity label or labels to the following containers:</span></span>

- [<span data-ttu-id="398d1-178">Grupo do Microsoft 365 no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="398d1-178">Microsoft 365 group in Azure AD</span></span>](#apply-sensitivity-labels-to-microsoft-365-groups)
- [<span data-ttu-id="398d1-179">Site de equipe do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="398d1-179">Microsoft Teams team site</span></span>](#apply-a-sensitivity-label-to-a-new-team)
- [<span data-ttu-id="398d1-180">Grupo do Microsoft 365 no Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="398d1-180">Microsoft 365 group in Outlook on the web</span></span>](#apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web)
- [<span data-ttu-id="398d1-181">Site do Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="398d1-181">SharePoint site</span></span>](#apply-a-sensitivity-label-to-a-new-site)

<span data-ttu-id="398d1-182">Você pode usar o Windows PowerShell se precisar [aplicar um rótulo de confidencialidade a vários sites](#use-powershell-to-apply-a-sensitivity-label-to-multiple-sites).</span><span class="sxs-lookup"><span data-stu-id="398d1-182">You can use PowerShell if you need to [apply a sensitivity label to multiple sites](#use-powershell-to-apply-a-sensitivity-label-to-multiple-sites).</span></span>

### <a name="apply-sensitivity-labels-to-microsoft-365-groups"></a><span data-ttu-id="398d1-183">Aplicar rótulos de confidencialidade aos grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="398d1-183">Apply sensitivity labels to Microsoft 365 groups</span></span>

<span data-ttu-id="398d1-184">Agora você está pronto para aplicar os rótulos ou rótulos de confidencialidade aos grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="398d1-184">You're now ready to apply the sensitivity label or labels to Microsoft 365 groups.</span></span> <span data-ttu-id="398d1-185">Retorne à documentação do Azure AD para obter instruções:</span><span class="sxs-lookup"><span data-stu-id="398d1-185">Return to the Azure AD documentation for instructions:</span></span>

- [<span data-ttu-id="398d1-186">Atribuir um rótulo a um novo grupo no portal do Azure</span><span class="sxs-lookup"><span data-stu-id="398d1-186">Assign a label to a new group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)

-  [<span data-ttu-id="398d1-187">Atribuir um rótulo a um grupo existente no portal do Azure</span><span class="sxs-lookup"><span data-stu-id="398d1-187">Assign a label to an existing group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

-  <span data-ttu-id="398d1-188">[Remover um rótulo de um grupo existente no portal do Azure](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="398d1-188">[Remove a label from an existing group in Azure portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span></span>

### <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="398d1-189">Aplicar um rótulo de confidencialidade a uma nova equipe</span><span class="sxs-lookup"><span data-stu-id="398d1-189">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="398d1-190">Os usuários podem selecionar os rótulos de confidencialidade ao criar novas equipes no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="398d1-190">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="398d1-191">Quando eles selecionam o rótulo na lista suspensa **Confidencialidade**, a configuração de privacidade pode mudar para refletir a configuração de rótulo.</span><span class="sxs-lookup"><span data-stu-id="398d1-191">When they select the label from the **Sensitivity** dropdown, the privacy setting might change to reflect the label configuration.</span></span> <span data-ttu-id="398d1-192">Dependendo da configuração de acesso de usuários externos que você selecionou para o rótulo, os usuários podem ou não adicionar pessoas de fora da organização à equipe.</span><span class="sxs-lookup"><span data-stu-id="398d1-192">Depending on the external users access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="398d1-193">Saiba mais sobre Rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="398d1-193">Learn more about sensitivity labels for Teams</span></span>](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![A configuração de privacidade ao criar uma nova equipe](../media/privacy-setting-new-team.png)

<span data-ttu-id="398d1-195">Depois de criar a equipe, o rótulo de confidencialidade aparecerá no canto superior direito de todos os canais.</span><span class="sxs-lookup"><span data-stu-id="398d1-195">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![O rótulo de confidencialidade aparece na equipe](../media/privacy-setting-teams.png)

<span data-ttu-id="398d1-197">O serviço aplica automaticamente o mesmo rótulo de confidencialidade ao grupo do Microsoft 365 e ao site de equipe do SharePoint conectado.</span><span class="sxs-lookup"><span data-stu-id="398d1-197">The service automatically applies the same sensitivity label to the Microsoft 365 group and the connected SharePoint team site.</span></span>

### <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a><span data-ttu-id="398d1-198">Aplicar um rótulo de confidencialidade a um novo grupo no Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="398d1-198">Apply a sensitivity label to a new group in Outlook on the web</span></span>

<span data-ttu-id="398d1-199">No Outlook na Web, ao criar um novo grupo, você pode selecionar ou alterar a opção de **Confidencialidade** para rótulos publicados:</span><span class="sxs-lookup"><span data-stu-id="398d1-199">In Outlook on the web, when you create a new group, you can select or change the **Sensitivity** option for published labels:</span></span>

![Criando um grupo e selecionando uma opção em Confidencialidade](../media/sensitivity-label-new-group.png)

### <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="398d1-201">Aplicar um rótulo de confidencialidade a um novo site</span><span class="sxs-lookup"><span data-stu-id="398d1-201">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="398d1-202">Os administradores e os usuários finais podem selecionar os rótulos de confidencialidade ao [criar sites de equipe e sites de comunicação modernos](/sharepoint/create-site-collection) e expandir as **Configurações avançadas**:</span><span class="sxs-lookup"><span data-stu-id="398d1-202">Admins and end users can select sensitivity labels when they [create modern team sites and communication sites](/sharepoint/create-site-collection), and expand **Advanced settings**:</span></span>

![Criando um site e selecionando uma opção de confidencialidade](../media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="398d1-204">A caixa suspensa exibe os nomes dos rótulos para a seleção e o ícone de ajuda exibe todos os nomes dos rótulos com a dica de ferramenta, o que pode ajudar os usuários a determinar o rótulo correto a ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="398d1-204">The dropdown box displays the label names for the selection, and the help icon displays all the label names with their tooltip, which can help users determine the correct label to apply.</span></span>

<span data-ttu-id="398d1-205">Quando o rótulo é aplicado e os usuários navegam no site, eles veem o nome do rótulo e as políticas aplicadas.</span><span class="sxs-lookup"><span data-stu-id="398d1-205">When the label is applied, and users browse to the site, they see the name of the label and applied policies.</span></span> <span data-ttu-id="398d1-206">Por exemplo, este site foi rotulado como **Confidencial** e a configuração de privacidade está definida como **Privada**:</span><span class="sxs-lookup"><span data-stu-id="398d1-206">For example, this site has been labeled as **Confidential**, and the privacy setting is set to **Private**:</span></span>

![Um site com uma etiqueta de confidencialidade aplicada](../media/sensitivity-label-site.png)

### <a name="use-powershell-to-apply-a-sensitivity-label-to-multiple-sites"></a><span data-ttu-id="398d1-208">Usar o Windows PowerShell para aplicar um rótulo de confidencialidade a vários sites</span><span class="sxs-lookup"><span data-stu-id="398d1-208">Use PowerShell to apply a sensitivity label to multiple sites</span></span>

<span data-ttu-id="398d1-209">Você pode usar o cmdlet [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite?view=sharepoint-ps) e [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) com o parâmetro *SensitivityLabel* do Shell de gerenciamento do SharePoint Online atual para aplicar um rótulo de confidencialidade a vários sites.</span><span class="sxs-lookup"><span data-stu-id="398d1-209">You can use the [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite?view=sharepoint-ps) and [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet with the *SensitivityLabel* parameter from the current SharePoint Online Management Shell to apply a sensitivity label to many sites.</span></span> <span data-ttu-id="398d1-210">Os sites podem ser um conjunto de sites do Microsoft Office SharePoint Online ou um site do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="398d1-210">The sites can be any SharePoint site collection, or a OneDrive site.</span></span>

<span data-ttu-id="398d1-211">Verifique se você tem a versão 16.0.19418.12000 ou posterior do Shell de gerenciamento do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="398d1-211">Make sure you have version 16.0.19418.12000 or later of the SharePoint Online Management Shell.</span></span>

1. <span data-ttu-id="398d1-212">Abra uma sessão do Windows PowerShell com a opção **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="398d1-212">Open a PowerShell session with the **Run as Administrator** option.</span></span>

2. <span data-ttu-id="398d1-213">Se você não souber o GUID da etiqueta: [Conecte-se ao PowerShell do Centro de Segurança e Conformidade do Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) e obter a lista de rótulos de confidencialidade e seus GUIDs.</span><span class="sxs-lookup"><span data-stu-id="398d1-213">If you don't know your label GUID: [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) and get the list of sensitivity labels and their GUIDs.</span></span>
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

3. <span data-ttu-id="398d1-214">Agora [conectar-se ao Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps) e armazenar o GUID da etiqueta como uma variável.</span><span class="sxs-lookup"><span data-stu-id="398d1-214">Now [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps) and store your label GUID as a variable.</span></span> <span data-ttu-id="398d1-215">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="398d1-215">For example:</span></span> 
    
    ```powershell
    $Id = [GUID]("e48058ea-98e8-4940-8db0-ba1310fd955e")
    ```

4. <span data-ttu-id="398d1-216">Criar uma nova variável que identifique vários sites com uma cadeia de caracteres de identificação em comum na URL.</span><span class="sxs-lookup"><span data-stu-id="398d1-216">Create a new variable that identifies multiple sites that have an identifying string in common in their URL.</span></span> <span data-ttu-id="398d1-217">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="398d1-217">For example:</span></span>
    
    ```powershell
    $sites = Get-SPOSite -IncludePersonalSite $true -Limit all -Filter "Url -like 'documents" 
    ```

5. <span data-ttu-id="398d1-218">Execute o seguinte comando para aplicar o rótulo a esses sites.</span><span class="sxs-lookup"><span data-stu-id="398d1-218">Run the following command to apply the label to these sites.</span></span> <span data-ttu-id="398d1-219">Usando nossos exemplos:</span><span class="sxs-lookup"><span data-stu-id="398d1-219">Using our examples:</span></span>
    
    ```powershell
    $sites | ForEach-Object {Set-SpoTenant $_.url -SensitivityLabel $Id}
    ```

<span data-ttu-id="398d1-220">Para aplicar diferentes rótulos a diferentes sites, repita o seguinte comando para cada site: `Set-SPOSite -Identity <URL> -SensitivityLabel "<labelguid>"`</span><span class="sxs-lookup"><span data-stu-id="398d1-220">To apply different labels to different sites, repeat the following command for each site: `Set-SPOSite -Identity <URL> -SensitivityLabel "<labelguid>"`</span></span>

## <a name="view-and-manage-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="398d1-221">Exibir e gerenciar rótulos de confidencialidade no Centro de Administração do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="398d1-221">View and manage sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="398d1-222">Para exibir, classificar e pesquisar os rótulos de confidencialidade aplicados, use a página de **Sites ativos** no novo Centro de Administração do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="398d1-222">To view, sort, and search the applied sensitivity labels, use the **Active sites** page in the new SharePoint admin center.</span></span> <span data-ttu-id="398d1-223">Talvez seja necessário adicionar primeiro a coluna **Confidencialidade**:</span><span class="sxs-lookup"><span data-stu-id="398d1-223">You might need to first add the **Sensitivity** column:</span></span>

![A coluna Confidencialidade na página sites ativos](../media/manage-site-sensitivity-labels.png)

<span data-ttu-id="398d1-225">Para obter mais informações sobre como gerenciar sites na página de sites ativos, inclusive como adicionar uma coluna, confira [Gerenciar sites no novo Centro de Administração do SharePoint Online](/sharepoint/manage-sites-in-new-admin-center).</span><span class="sxs-lookup"><span data-stu-id="398d1-225">For more information about managing sites from the Active sites page, including how to add a column, see [Manage sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

<span data-ttu-id="398d1-226">Você também pode alterar e aplicar um rótulo da seguinte página:</span><span class="sxs-lookup"><span data-stu-id="398d1-226">You can also change and apply a label from this page:</span></span>

1. <span data-ttu-id="398d1-227">Selecione o nome do site para abrir o painel de detalhes.</span><span class="sxs-lookup"><span data-stu-id="398d1-227">Select the site name to open the details pane.</span></span>

2. <span data-ttu-id="398d1-228">Selecione a guia **Políticas** e, em seguida, selecione **Editar** para a configuração de **Confidencialidade**.</span><span class="sxs-lookup"><span data-stu-id="398d1-228">Select the **Policies** tab, and then select **Edit** for the **Sensitivity** setting.</span></span>

3. <span data-ttu-id="398d1-229">No painel **Editar configuração de confidencialidade**, selecione o rótulo de confidencialidade que você deseja aplicar ao site e, em seguida, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="398d1-229">From the **Edit sensitivity setting** pane, select the sensitivity label you want to apply to the site, and then select **Save**.</span></span>

## <a name="support-for-sensitivity-labels"></a><span data-ttu-id="398d1-230">Suporte de rótulos de confidencialidade.</span><span class="sxs-lookup"><span data-stu-id="398d1-230">Support for sensitivity labels</span></span>

<span data-ttu-id="398d1-231">Os seguintes aplicativos e serviços oferecem suporte as etiquetas de confidencialidade configuradas para configurações de sites e grupos:</span><span class="sxs-lookup"><span data-stu-id="398d1-231">The following apps and services support sensitivity labels configured for sites and group settings:</span></span>

- <span data-ttu-id="398d1-232">Centros de administração:</span><span class="sxs-lookup"><span data-stu-id="398d1-232">Admin centers:</span></span>
    - <span data-ttu-id="398d1-233">Centro de administração do SharePoint</span><span class="sxs-lookup"><span data-stu-id="398d1-233">SharePoint admin center</span></span>
    - <span data-ttu-id="398d1-234">Portal do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="398d1-234">Azure Active Directory portal</span></span>
    - <span data-ttu-id="398d1-235">O Centro de conformidade do Microsoft 365, o Centro de segurança do Microsoft 365 ou o Centro de Segurança e Conformidade do Office 365.</span><span class="sxs-lookup"><span data-stu-id="398d1-235">Microsoft 365 compliance center, Microsoft 365 security center, Office 365 Security & Compliance Center</span></span>

- <span data-ttu-id="398d1-236">Aplicativos e serviços do usuário:</span><span class="sxs-lookup"><span data-stu-id="398d1-236">User apps and services:</span></span>
    - <span data-ttu-id="398d1-237">Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="398d1-237">SharePoint</span></span>
    - <span data-ttu-id="398d1-238">Teams</span><span class="sxs-lookup"><span data-stu-id="398d1-238">Teams</span></span>
    - <span data-ttu-id="398d1-239">Outlook na Web e para Windows, MacOS, iOS e Android</span><span class="sxs-lookup"><span data-stu-id="398d1-239">Outlook on the web and for Windows, MacOS, iOS, and Android</span></span>
    - <span data-ttu-id="398d1-240">Formulários</span><span class="sxs-lookup"><span data-stu-id="398d1-240">Forms</span></span>
    - <span data-ttu-id="398d1-241">Fluxo</span><span class="sxs-lookup"><span data-stu-id="398d1-241">Stream</span></span>

<span data-ttu-id="398d1-242">Os seguintes aplicativos e serviços não oferecem suporte as etiquetas de confidencialidade configuradas para configurações de sites e grupos:</span><span class="sxs-lookup"><span data-stu-id="398d1-242">The following apps and services don't currently support sensitivity labels configured for sites and group settings:</span></span>

- <span data-ttu-id="398d1-243">Centros de administração:</span><span class="sxs-lookup"><span data-stu-id="398d1-243">Admin centers:</span></span>
    - <span data-ttu-id="398d1-244">Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="398d1-244">Microsoft 365 admin center</span></span>
    - <span data-ttu-id="398d1-245">Centro de administração do Teams</span><span class="sxs-lookup"><span data-stu-id="398d1-245">Teams admin center</span></span>
    - <span data-ttu-id="398d1-246">Centro de administração do Exchange</span><span class="sxs-lookup"><span data-stu-id="398d1-246">Exchange admin center</span></span>

- <span data-ttu-id="398d1-247">Aplicativos e serviços do usuário:</span><span class="sxs-lookup"><span data-stu-id="398d1-247">User apps and services:</span></span>
    - <span data-ttu-id="398d1-248">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="398d1-248">Dynamics 365</span></span>
    - <span data-ttu-id="398d1-249">Yammer</span><span class="sxs-lookup"><span data-stu-id="398d1-249">Yammer</span></span>
    - <span data-ttu-id="398d1-250">Planner</span><span class="sxs-lookup"><span data-stu-id="398d1-250">Planner</span></span>
    - <span data-ttu-id="398d1-251">Project</span><span class="sxs-lookup"><span data-stu-id="398d1-251">Project</span></span>
    - <span data-ttu-id="398d1-252">PowerBI</span><span class="sxs-lookup"><span data-stu-id="398d1-252">PowerBI</span></span>

## <a name="classic-azure-ad-group-classification"></a><span data-ttu-id="398d1-253">Classificação clássica de grupo do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="398d1-253">Classic Azure AD group classification</span></span>

<span data-ttu-id="398d1-254">O Microsoft 365 não oferece mais suporte às classificações antigas para novos grupos do Microsoft 365 e sites do SharePoint quando você habilita os rótulos de confidencialidade para contêineres.</span><span class="sxs-lookup"><span data-stu-id="398d1-254">Microsoft 365 no longer supports the old classifications for new Microsoft 365 groups and SharePoint sites after you enable sensitivity labels for containers.</span></span> <span data-ttu-id="398d1-255">No entanto, os grupos e sites existentes que oferecem suporte a rótulos de confidencialidade ainda exibem os valores de classificação antigos, até que você os converta para usar rótulos de confidencialidade.</span><span class="sxs-lookup"><span data-stu-id="398d1-255">However, existing groups and sites that support sensitivity labels still display the old classification values until you convert them to use sensitivity labels.</span></span>

<span data-ttu-id="398d1-256">Como um exemplo de como você pode ter usado a classificação de grupo antiga do SharePoint, confira [Classificação de sites “moderna”](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span><span class="sxs-lookup"><span data-stu-id="398d1-256">As an example of how you might have used the old group classification for SharePoint, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="398d1-257">Essas classificações foram configuradas usando o Azure AD PowerShell ou a biblioteca Principal do PnP e definindo valores para a configuração do `ClassificationList`.</span><span class="sxs-lookup"><span data-stu-id="398d1-257">These classifications were configured by using Azure AD PowerShell or the PnP Core library and defining values for the `ClassificationList` setting.</span></span> <span data-ttu-id="398d1-258">Se seu locatário tiver valores de classificação definidos, eles serão mostrados quando você executar o seguinte comando no [módulo AzureADPreview PowerShell](https://www.powershellgallery.com/packages/AzureADPreview):</span><span class="sxs-lookup"><span data-stu-id="398d1-258">If your tenant has classification values defined, they are shown when you run the following command from the [AzureADPreview PowerShell module](https://www.powershellgallery.com/packages/AzureADPreview):</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="398d1-259">Para converter suas classificações antigas em rótulos de confidencialidade, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="398d1-259">To convert your old classifications to sensitivity labels, do one of the following:</span></span>

- <span data-ttu-id="398d1-260">Usar rótulos existentes: Especifique as configurações de rótulo desejadas para sites e grupos editando rótulos de confidencialidade existentes que já foram publicados.</span><span class="sxs-lookup"><span data-stu-id="398d1-260">Use existing labels: Specify the label settings you want for sites and groups by editing existing sensitivity labels that are already published.</span></span>

- <span data-ttu-id="398d1-261">Criar novos rótulos: Especifique as configurações de rótulos desejados para sites e grupos, criando e publicando novos rótulos de confidencialidade que tenham os mesmos nomes das suas classificações existentes.</span><span class="sxs-lookup"><span data-stu-id="398d1-261">Create new labels: Specify the label settings you want for sites and groups by creating and publishing new sensitivity labels that have the same names as your existing classifications.</span></span>

<span data-ttu-id="398d1-262">Depois:</span><span class="sxs-lookup"><span data-stu-id="398d1-262">Then:</span></span> 

1. <span data-ttu-id="398d1-263">Use o PowerShell para aplicar os rótulos de confidencialidade a grupos existentes do Microsoft 365 e sites do SharePoint usando o mapeamento de nomes.</span><span class="sxs-lookup"><span data-stu-id="398d1-263">Use PowerShell to apply the sensitivity labels to existing Microsoft 365 groups and SharePoint sites by using name mapping.</span></span> <span data-ttu-id="398d1-264">Confira a seção a seguir para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="398d1-264">See the next section for instructions.</span></span>

2. <span data-ttu-id="398d1-265">Remova as classificações antigas dos grupos e sites existentes.</span><span class="sxs-lookup"><span data-stu-id="398d1-265">Remove the old classifications from the existing groups and sites.</span></span>

<span data-ttu-id="398d1-266">Embora você não possa impedir que os usuários criem novos grupos em aplicativos e serviços que ainda não suportam rótulos de confidencialidade, é possível executar um script recorrente do PowerShell para procurar novos grupos que os usuários criaram com as classificações antigas e convertê-los para uso de rótulos de confidencialidade.</span><span class="sxs-lookup"><span data-stu-id="398d1-266">Although you can't prevent users from creating new groups in apps and services that don't yet support sensitivity labels, you can run a recurring PowerShell script to look for new groups that users have created with the old classifications, and convert these to use sensitivity labels.</span></span> 

<span data-ttu-id="398d1-267">Para ajudar você a gerenciar a coexistência de rótulos de sensibilidade e classificações do Azure Active Directory para sites e grupos, confira [rótulos de classificação e confidencialidade do Azure Active Directory para grupos do Microsoft 365](migrate-aad-classification-sensitivity-labels.md).</span><span class="sxs-lookup"><span data-stu-id="398d1-267">To help you manage the coexistence of sensitivity labels and Azure AD classifications for sites and groups, see [Azure Active Directory classification and sensitivity labels for Microsoft 365 groups](migrate-aad-classification-sensitivity-labels.md).</span></span>

#### <a name="use-powershell-to-convert-classifications-for-microsoft-365-groups-to-sensitivity-labels"></a><span data-ttu-id="398d1-268">Use o PowerShell para converter classificações de grupos do Microsoft 365 em rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="398d1-268">Use PowerShell to convert classifications for Microsoft 365 groups to sensitivity labels</span></span>

1. <span data-ttu-id="398d1-269">Primeiro, [conecte-se ao PowerShell do Centro de Conformidade e Segurança do Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="398d1-269">First, [connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span> 
    
    <span data-ttu-id="398d1-270">Por exemplo, em uma sessão do PowerShell que você executa como administrador, entre com uma conta de administrador global:</span><span class="sxs-lookup"><span data-stu-id="398d1-270">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. <span data-ttu-id="398d1-271">Obtenha a lista de rótulos de confidencialidade e suas GUIDs usando o cmdlet [Get-Label](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps):</span><span class="sxs-lookup"><span data-stu-id="398d1-271">Get the list of sensitivity labels and their GUIDs by using the [Get-Label](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps) cmdlet:</span></span>
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

3. <span data-ttu-id="398d1-272">Anote o GUIDe dos rótulos de confidencialidade que você deseja aplicar a seus grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="398d1-272">Make a note of the GUIDs for the sensitivity labels you want to apply to your Microsoft 365 groups.</span></span>

4. <span data-ttu-id="398d1-273">Agora, [conecte-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="398d1-273">Now [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
    <span data-ttu-id="398d1-274">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="398d1-274">For example:</span></span>
    
    ```powershell
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    ```

5. <span data-ttu-id="398d1-275">Use o seguinte comando como exemplo para obter a lista de grupos que atualmente têm a classificação "Geral":</span><span class="sxs-lookup"><span data-stu-id="398d1-275">Use the following command as an example to get the list of groups that currently have the classification of "General":</span></span>

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. <span data-ttu-id="398d1-276">Para cada grupo, adicione o novo GUID de rótulo de confidencialidade.</span><span class="sxs-lookup"><span data-stu-id="398d1-276">For each group, add the new sensitivity label GUID.</span></span> <span data-ttu-id="398d1-277">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="398d1-277">For example:</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

7. <span data-ttu-id="398d1-278">Repita as etapas 5 e 6 para as classificações de grupo restantes.</span><span class="sxs-lookup"><span data-stu-id="398d1-278">Repeat steps 5 and 6 for your remaining group classifications.</span></span>

## <a name="auditing-sensitivity-label-activities"></a><span data-ttu-id="398d1-279">Atividades de rótulo de confidencialidade de auditoria</span><span class="sxs-lookup"><span data-stu-id="398d1-279">Auditing sensitivity label activities</span></span>

<span data-ttu-id="398d1-280">Se alguém enviar um documento para um site protegido por um rótulo de confidencialidade e o documento tiver um rótulo de confidencialidade com [prioridade mais alta](sensitivity-labels.md#label-priority-order-matters) que o rótulo de confidencialidade aplicado ao site, essa ação não será bloqueada.</span><span class="sxs-lookup"><span data-stu-id="398d1-280">If somebody uploads a document to a site that's protected with a sensitivity label and their document has a [higher priority](sensitivity-labels.md#label-priority-order-matters) sensitivity label than the sensitivity label applied to the site, this action isn't blocked.</span></span> <span data-ttu-id="398d1-281">Por exemplo, você aplicou o rótulo **Geral** a um site do SharePoint e alguém carrega neste site um documento chamado **Confidencial**.</span><span class="sxs-lookup"><span data-stu-id="398d1-281">For example, you've applied the **General** label to a SharePoint site, and somebody uploads to this site a document labeled **Confidential**.</span></span> <span data-ttu-id="398d1-282">Como um rótulo de confidencialidade com prioridade mais alta identifica o conteúdo que é mais confidencial do que o conteúdo com ordem de prioridade mais baixa, essa situação pode ser um problema de segurança.</span><span class="sxs-lookup"><span data-stu-id="398d1-282">Because a sensitivity label with a higher priority identifies content that is more sensitivity than content that has a lower priority order, this situation could be a security concern.</span></span>

<span data-ttu-id="398d1-283">Embora a ação não seja bloqueada, ela é auditada e gera automaticamente um email para a pessoa que carregou o documento e para o administrador do site.</span><span class="sxs-lookup"><span data-stu-id="398d1-283">Although the action isn't blocked, it is audited and automatically generates an email to the person who uploaded the document and the site administrator.</span></span> <span data-ttu-id="398d1-284">Como resultado, tanto o usuário como os administradores podem identificar documentos que tenham esse desalinhamento da prioridade do rótulo e tomar medidas, se necessário.</span><span class="sxs-lookup"><span data-stu-id="398d1-284">As a result, both the user and administrators can identify documents that have this misalignment of label priority and take action if needed.</span></span> <span data-ttu-id="398d1-285">Por exemplo, excluir ou mover o documento carregado do site.</span><span class="sxs-lookup"><span data-stu-id="398d1-285">For example, delete or move the uploaded document from the site.</span></span> 

<span data-ttu-id="398d1-286">Não seria um problema de segurança se o documento tivesse um rótulo de confidencialidade de prioridade mais baixa que o rótulo de confidencialidade aplicado ao site.</span><span class="sxs-lookup"><span data-stu-id="398d1-286">It wouldn't be a security concern if the document has a lower priority sensitivity label than the sensitivity label applied to the site.</span></span> <span data-ttu-id="398d1-287">Por exemplo, um documento chamado **Geral** é carregado em um site chamado **Confidencial**.</span><span class="sxs-lookup"><span data-stu-id="398d1-287">For example, a document labeled **General** is uploaded to a site labeled **Confidential**.</span></span> <span data-ttu-id="398d1-288">Neste cenário, um evento de auditoria e email não são gerados.</span><span class="sxs-lookup"><span data-stu-id="398d1-288">In this scenario, an auditing event and email aren't generated.</span></span>

<span data-ttu-id="398d1-289">Para pesquisar o log de auditoria para esse evento, procure por **Incompatibilidade de confidencialidade em documento detectada** na categoria **Atividades de arquivo e página**.</span><span class="sxs-lookup"><span data-stu-id="398d1-289">To search the audit log for this event, look for **Detected document sensitivity mismatch** from the **File and page activities** category.</span></span> 

<span data-ttu-id="398d1-290">O email gerado automaticamente tem o assunto **Rótulo de confidencialidade incompatível detectado** e a mensagem do email explica a incompatibilidade de rótulo com um link para o documento e o site carregados.</span><span class="sxs-lookup"><span data-stu-id="398d1-290">The automatically generated email has the subject **Incompatible sensitivity label detected** and the email message explains the labeling mismatch with a link to the uploaded document and site.</span></span> <span data-ttu-id="398d1-291">Ele também contém um link de documentação que explica como os usuários podem alterar o rótulo de confidencialidade.</span><span class="sxs-lookup"><span data-stu-id="398d1-291">It also contains a documentation link that explains how users can change the sensitivity label.</span></span> <span data-ttu-id="398d1-292">Atualmente, não é possível desabilitar ou personalizar esses emails.</span><span class="sxs-lookup"><span data-stu-id="398d1-292">Currently, these automated emails cannot be disabled or customized.</span></span>

<span data-ttu-id="398d1-293">Quando alguém adiciona ou remove um rótulo de confidencialidade para ou de um site ou grupo, essas atividades também são auditadas, mas não geram um email automático.</span><span class="sxs-lookup"><span data-stu-id="398d1-293">When somebody adds or removes a sensitivity label to or from a site or group, these activities are also audited but without automatically generating an email.</span></span> 

<span data-ttu-id="398d1-294">Todos esses eventos podem ser encontrados na categoria [Atividades de rótulo de confidencialidade](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities).</span><span class="sxs-lookup"><span data-stu-id="398d1-294">All these auditing events can be found in the [Sensitivity label activities](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) category.</span></span> <span data-ttu-id="398d1-295">Para obter instruções sobre como pesquisar o log de auditoria, confira [Pesquisar o log de auditoria no Centro de Conformidade e Segurança](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="398d1-295">For instructions to search the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="how-to-disable-sensitivity-labels-for-containers"></a><span data-ttu-id="398d1-296">Como desabilitar os rótulos de confidencialidade para contêineres</span><span class="sxs-lookup"><span data-stu-id="398d1-296">How to disable sensitivity labels for containers</span></span>

<span data-ttu-id="398d1-297">Você pode desativar os rótulos de confidencialidade do Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint usando as mesmas instruções de [Habilitar o suporte a rótulo de confidencialidade no PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span><span class="sxs-lookup"><span data-stu-id="398d1-297">You can turn off sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites by using the same instructions from [Enable sensitivity label support in PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span></span> <span data-ttu-id="398d1-298">No entanto, para desabilitar o recurso, na etapa 5, especifique `$setting["EnableMIPLabels"] = "False"`.</span><span class="sxs-lookup"><span data-stu-id="398d1-298">However, to disable the feature, in step 5, specify `$setting["EnableMIPLabels"] = "False"`.</span></span>

<span data-ttu-id="398d1-299">Além de ocultar a página de **Sites e configurações de grupo** quando você cria ou edita rótulos de confidencialidade, essa ação reverte qual propriedade os contêineres usam para a configuração.</span><span class="sxs-lookup"><span data-stu-id="398d1-299">In addition to hiding the **Sites and group settings** page when you create or edit sensitivity labels, this action reverts which property the containers use for their configuration.</span></span> <span data-ttu-id="398d1-300">Habilitar rótulos de confidencialidade para o Microsoft Teams, o Microsoft 365 Groups, e os sites do SharePoint altera a propriedade usada de **Classificação** (usada para [classificação de grupo do Azure Active Direcroty](#classic-azure-ad-group-classification)) para **Confidencialidade**.</span><span class="sxs-lookup"><span data-stu-id="398d1-300">Enabling sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites switches the property used from **Classification** (used for [Azure AD group classification](#classic-azure-ad-group-classification)) to **Sensitivity**.</span></span> <span data-ttu-id="398d1-301">Quando você desabilita os rótulos de confidencialidade para contêineres, os contêineres ignoram a propriedade Confidencialidade e usam novamente a propriedade de Classificação.</span><span class="sxs-lookup"><span data-stu-id="398d1-301">When you disable sensitivity labels for containers, the containers ignore the Sensitivity property and use the Classification property again.</span></span>

<span data-ttu-id="398d1-302">Isso significa que todas as configurações de rótulo de sites e grupos aplicados anteriormente aos contêineres não serão forçadas e os contêineres não exibirão mais os rótulos.</span><span class="sxs-lookup"><span data-stu-id="398d1-302">This means that any label settings from sites and groups previously applied to containers won't be enforced, and containers no longer display the labels.</span></span>

<span data-ttu-id="398d1-303">Se esses contêineres tiverem valores de classificação do Azure Active Directory aplicados, eles voltarão a usar as classificações novamente.</span><span class="sxs-lookup"><span data-stu-id="398d1-303">If these containers have Azure AD classification values applied to them, the containers revert to using the classifications again.</span></span> <span data-ttu-id="398d1-304">Lembre-se de que todos os novos sites ou grupos criados depois de habilitar o recurso não exibirão um rótulo ou terão uma classificação.</span><span class="sxs-lookup"><span data-stu-id="398d1-304">Be aware that any new sites or groups that were created after enabling the feature won't display a label or have a classification.</span></span> <span data-ttu-id="398d1-305">Para esses contêineres e todos os novos contêineres, você pode aplicar valores de classificação.</span><span class="sxs-lookup"><span data-stu-id="398d1-305">For these containers, and any new containers, you can now apply classification values.</span></span> <span data-ttu-id="398d1-306">Para saber mais, confira [Classificação de sites modernos do Microsoft Office SharePoint Online](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification) e [Criar classificações para grupos do Office em sua organização](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell).</span><span class="sxs-lookup"><span data-stu-id="398d1-306">For more information, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification) and [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="398d1-307">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="398d1-307">Additional resources</span></span>

<span data-ttu-id="398d1-308">Consulte a gravação do seminário on-line e as perguntas respondidas para [Usar rótulos de sensibilidade nos sites Microsoft Teams, O365 Groups e SharePoint Online](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380).</span><span class="sxs-lookup"><span data-stu-id="398d1-308">See the webinar recording and answered questions for [Using Sensitivity labels with Microsoft Teams, O365 Groups and SharePoint Online sites](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380).</span></span>

<span data-ttu-id="398d1-309">Esse webinar foi gravado quando o recurso ainda estava na visualização, para que você possa observar algumas discrepâncias na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="398d1-309">This webinar was recorded when the feature was still in preview, so you might notice some discrepancies in the UI.</span></span> <span data-ttu-id="398d1-310">No entanto, as informações para esse recurso ainda são precisas, com todos os novos recursos documentados nesta página.</span><span class="sxs-lookup"><span data-stu-id="398d1-310">However, the information for this feature is still accurate, with any new capabilities documented on this page.</span></span>
