---
title: Gerenciar os grupos do Microsoft 365 com o PowerShell
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BSA160
- BCS160
ms.assetid: aeb669aa-1770-4537-9de2-a82ac11b0540
description: Neste artigo, saiba como realizar tarefas comuns de gerenciamento para os grupos do Microsoft 365 no PowerShell.
ms.openlocfilehash: c1aa551597644b7f41c3445a791ea27579464f7b
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277474"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a><span data-ttu-id="fa7cd-103">Gerenciar os grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="fa7cd-103">Manage Microsoft 365 Groups with PowerShell</span></span>

<span data-ttu-id="fa7cd-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="fa7cd-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="fa7cd-105">Este artigo fornece as etapas para realizar tarefas comuns de gerenciamento para grupos no Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-105">This article provides the steps for doing common management tasks for Groups in Microsoft PowerShell.</span></span> <span data-ttu-id="fa7cd-106">Ele também lista os cmdlets do PowerShell para grupos.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-106">It also lists the PowerShell cmdlets for Groups.</span></span> <span data-ttu-id="fa7cd-107">Para obter informações sobre como gerenciar sites do SharePoint, confira [gerenciar sites do SharePoint online usando o PowerShell](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell).</span><span class="sxs-lookup"><span data-stu-id="fa7cd-107">For info about managing SharePoint sites, see [Manage SharePoint Online sites using PowerShell](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell).</span></span>

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a><span data-ttu-id="fa7cd-108">Link para suas diretrizes de uso de grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fa7cd-108">Link to your Microsoft 365 Groups usage guidelines</span></span>
<span data-ttu-id="fa7cd-109"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="fa7cd-109"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="fa7cd-110">Quando os usuários [criarem ou editarem um grupo no Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx), você poderá mostrar um link para as diretrizes de uso da sua organização.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-110">When users [create or edit a group in Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx), you can show them a link to your organization's usage guidelines.</span></span> <span data-ttu-id="fa7cd-111">Por exemplo, se você precisar adicionar um prefixo ou sufixo específico a um nome de grupo.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-111">For example, if you require a specific prefix or suffix to be added to a group name.</span></span>

<span data-ttu-id="fa7cd-112">Use o PowerShell do Azure Active Directory (Azure AD) para apontar seus usuários para as diretrizes de uso da sua organização para os grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-112">Use the Azure Active Directory (Azure AD) PowerShell to point your users to your organization's usage guidelines for Microsoft 365 groups.</span></span> <span data-ttu-id="fa7cd-113">Confira os [cmdlets do Azure Active Directory para definir as configurações de grupo](https://go.microsoft.com/fwlink/?LinkID=827484) e siga as etapas em **criar configurações no nível do diretório** para definir o hiperlink de diretriz de uso.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-113">Check out [Azure Active Directory cmdlets for configuring group settings](https://go.microsoft.com/fwlink/?LinkID=827484) and follow the steps in the **Create settings at the directory level** to define the usage guideline hyperlink.</span></span> <span data-ttu-id="fa7cd-114">Depois de executar o cmdlet AAD, o usuário verá o link para suas diretrizes ao criar ou editar um grupo no Outlook.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-114">Once you run the AAD cmdlet, user's will see the link to your guidelines when they create or edit a group in Outlook.</span></span>

![Criar um novo grupo com o link de diretrizes de uso](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![Clique em diretrizes de uso de grupo para ver as diretrizes de grupos do Office 365](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a><span data-ttu-id="fa7cd-117">Permitir que os usuários enviem como o grupo Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fa7cd-117">Allow users to Send as the Microsoft 365 Group</span></span>
<span data-ttu-id="fa7cd-118"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="fa7cd-118"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="fa7cd-119">Se você deseja habilitar seus grupos do Microsoft 365 para "enviar como", use os cmdlets [Add-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/add-recipientpermission) e [Get-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/get-recipientpermission) para configurá-lo.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-119">If you want to enable your Microsoft 365 groups to "Send As", use the [Add-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/add-recipientpermission) and [Get-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/get-recipientpermission) cmdlets to configure this.</span></span> <span data-ttu-id="fa7cd-120">Após habilitar essa configuração, os usuários do grupo do Microsoft 365 podem usar o Outlook ou o Outlook na Web para enviar e responder a email como o grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-120">Once you enable this setting, Microsoft 365 group users can use Outlook or Outlook on the web to send and reply to email as the Microsoft 365 group.</span></span> <span data-ttu-id="fa7cd-121">Os usuários podem ir para o grupo, criar um novo email e alterar o campo "enviar como" para o endereço de email do grupo.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-121">Users can go to the group, create a new email, and change the "Send As" field to the group's email address.</span></span>

<span data-ttu-id="fa7cd-122">([Você também pode fazer isso no centro de administração do Exchange](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group).)</span><span class="sxs-lookup"><span data-stu-id="fa7cd-122">([You can also do this in the Exchange Admin Center](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group).)</span></span>

<span data-ttu-id="fa7cd-123">Use o script a seguir, substituindo *\<GroupAlias\>* com o alias do grupo que você deseja atualizar e *\<UserAlias\>* com o alias do usuário para o qual você deseja conceder permissões.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-123">Use the following script, replacing *\<GroupAlias\>* with the alias of the group that you want to update, and *\<UserAlias\>* with the alias of the user to whom you want to grant permissions.</span></span> <span data-ttu-id="fa7cd-124">[Conectar-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) para executar esse script.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-124">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) to run this script.</span></span>

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

<span data-ttu-id="fa7cd-125">Depois que o cmdlet é executado, os usuários podem acessar o Outlook ou o Outlook na Web para enviar como o grupo, adicionando o endereço de email do grupo ao campo **de** .</span><span class="sxs-lookup"><span data-stu-id="fa7cd-125">Once the cmdlet is executed, users can go to Outlook or Outlook on the web to send as the group, by adding the group email address to the **From** field.</span></span>

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a><span data-ttu-id="fa7cd-126">Criar classificações para os grupos da Microsoft 365 em sua organização</span><span class="sxs-lookup"><span data-stu-id="fa7cd-126">Create classifications for Microsoft 365 Groups in your organization</span></span>

<span data-ttu-id="fa7cd-127">Você pode criar rótulos de confidencialidade que os usuários em sua organização podem definir quando criarem um grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-127">You can create sensitivity labels that the users in your organization can set when they create a Microsoft 365 Group.</span></span> <span data-ttu-id="fa7cd-128">Se você quiser classificar grupos, recomendamos usar rótulos de confidencialidade em vez do recurso de classificação de grupos anterior.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-128">If you want to classify groups, we recommend using sensitivity labels instead of the previous groups classification feature.</span></span> <span data-ttu-id="fa7cd-129">Para obter informações sobre como usar rótulos de confidencialidade, confira [usar rótulos de sensibilidade para proteger o conteúdo no Microsoft Teams, microsoft 365 Groups e sites do SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="fa7cd-129">For information about using sensitivity labels, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fa7cd-130">Se você estiver usando rótulos de classificação no momento, eles não estarão mais disponíveis aos usuários que criam grupos depois que os rótulos de sensibilidade estiverem habilitados.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-130">If you are currently using classification labels, they will no longer be available to users who create groups once sensitivity labels are enabled.</span></span>

<span data-ttu-id="fa7cd-131">Você ainda pode usar o recurso de classificação de grupos anterior.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-131">You can still use the previous groups classification feature.</span></span> <span data-ttu-id="fa7cd-132">Você pode criar classificações que os usuários em sua organização podem definir quando criarem um grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-132">You can create classifications that the users in your organization can set when they create an Microsoft 365 Group.</span></span> <span data-ttu-id="fa7cd-133">Por exemplo, você pode permitir que os usuários definam "Standard", "Secret" e "Top Secret" em grupos criados.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-133">For example, you can allow users to set "Standard", "Secret", and "Top Secret" on groups they create.</span></span> <span data-ttu-id="fa7cd-134">As classificações de grupo não são definidas por padrão e você precisa criá-las para que os usuários a definam.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-134">Group classifications aren't set by default and you need to create it in order for your users to set it.</span></span> <span data-ttu-id="fa7cd-135">Use o PowerShell do Azure Active Directory para apontar seus usuários para as diretrizes de uso da sua organização para os grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-135">Use Azure Active Directory PowerShell to point your users to your organization's usage guidelines for Microsoft 365 Groups.</span></span>

<span data-ttu-id="fa7cd-136">Confira os [cmdlets do Azure Active Directory para definir as configurações de grupo](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets) e siga as etapas em **criar configurações no nível do diretório** para definir a classificação de grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-136">Check out [Azure Active Directory cmdlets for configuring group settings](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets) and follow the steps in the **Create settings at the directory level** to define the classification for Microsoft 365 Groups.</span></span>

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

<span data-ttu-id="fa7cd-137">Para associar uma descrição a cada classificação, você pode usar o atributo de configurações  *ClassificationDescriptions* para definir.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-137">In order to associate a description to each classification you can use the settings attribute  *ClassificationDescriptions* to define.</span></span>

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

<span data-ttu-id="fa7cd-138">em que a classificação corresponde às cadeias de caracteres na classificação.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-138">where Classification matches the strings in the ClassificationList.</span></span>

<span data-ttu-id="fa7cd-139">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="fa7cd-139">Example:</span></span>

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

<span data-ttu-id="fa7cd-140">Depois de executar o cmdlet acima do Active Directory do Azure para definir sua classificação, execute o cmdlet [set-unificado](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) , se quiser definir a classificação de um grupo específico.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-140">After you run the above Azure Active Directory cmdlet to set your classification, run the [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) cmdlet if you want to set the classification for a specific group.</span></span>

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

<span data-ttu-id="fa7cd-141">Ou criar um novo grupo com uma classificação.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-141">Or create a new group with a classification.</span></span>

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

<span data-ttu-id="fa7cd-142">Confira [usando o PowerShell com o Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) e [Conecte-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) para obter mais detalhes sobre como usar o PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-142">Check out [Using PowerShell with Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) for more details on using Exchange Online PowerShell.</span></span>

<span data-ttu-id="fa7cd-143">Depois que essas configurações forem habilitadas, o proprietário do grupo poderá escolher uma classificação no menu suspenso no Outlook na Web e no Outlook e salvá-la na página **Editar** grupo.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-143">Once these settings are enabled, the group owner will be able to choose a classification from the drop down menu in Outlook on the Web and Outlook, and save it from the **Edit** group page.</span></span>

![Escolha a classificação de grupo do Microsoft 365](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a><span data-ttu-id="fa7cd-145">Ocultar os grupos do Microsoft 365 da lista de endereços global.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-145">Hide Microsoft 365 Groups from the global address list.</span></span>
<span data-ttu-id="fa7cd-146"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="fa7cd-146"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="fa7cd-147">Você pode especificar se um grupo do Microsoft 365 aparece na lista de endereços global (GAL) e em outras listas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-147">You can specify whether a Microsoft 365 Group appears in the global address list (GAL) and other lists in your organization.</span></span> <span data-ttu-id="fa7cd-148">Por exemplo, se você tiver um grupo de departamento jurídico que não deseja exibir na lista de endereços, você pode impedir que esse grupo apareça na GAL.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-148">For example, if you have a legal department group that you don't want to show up in the address list, you can stop that group from appearing in the GAL.</span></span> <span data-ttu-id="fa7cd-149">Execute o cmdlet Set-Unified Group para ocultar o grupo da lista de endereços da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="fa7cd-149">Run the Set-Unified Group cmdlet to hide the group from the address list like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a><span data-ttu-id="fa7cd-150">Permitir que somente usuários internos enviem mensagens para grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fa7cd-150">Allow only internal users to send message to Microsoft 365 Groups</span></span>
<span data-ttu-id="fa7cd-151"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="fa7cd-151"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="fa7cd-152">Se você não quiser que os usuários de outras organizações enviem emails para um grupo do Microsoft 365, poderá alterar as configurações desse grupo.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-152">If you don't want users from other organizations to send emails to a Microsoft 365 Group, you can change the settings for that group.</span></span> <span data-ttu-id="fa7cd-153">Ele permitirá que apenas usuários internos enviem um email para o seu grupo.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-153">It will allow only internal users to send an email to your group.</span></span> <span data-ttu-id="fa7cd-154">Se um usuário externo tentar enviar uma mensagem para esse grupo, ele será rejeitado.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-154">If an external user tries to send a message to that group, it will be rejected.</span></span>

<span data-ttu-id="fa7cd-155">Execute o cmdlet Set-unificado para atualizar essa configuração, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="fa7cd-155">Run the Set-UnifiedGroup cmdlet to update this setting, like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a><span data-ttu-id="fa7cd-156">Adicionar dicas de dicas aos grupos da Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fa7cd-156">Add MailTips to Microsoft 365 Groups</span></span>
<span data-ttu-id="fa7cd-157"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="fa7cd-157"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="fa7cd-158">Sempre que um remetente tenta enviar um email a um grupo do Microsoft 365, uma dica de email pode ser exibida para eles.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-158">Whenever a sender tries to send an email to a Microsoft 365 Group, a MailTip can be shown to them.</span></span>

<span data-ttu-id="fa7cd-159">Execute o cmdlet Set-Unified Group para adicionar uma dica de tela ao grupo:</span><span class="sxs-lookup"><span data-stu-id="fa7cd-159">Run the Set-Unified Group cmdlet to add a mailTip to the group:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

<span data-ttu-id="fa7cd-160">Juntamente com as dicas de dicas, você também pode definir MailTipTranslations, que especifica idiomas adicionais para a dica de a.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-160">Along with MailTip, you can also set MailTipTranslations, which specifies additional languages for the MailTip.</span></span> <span data-ttu-id="fa7cd-161">Suponha que você deseja ter a tradução para espanhol e, em seguida, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="fa7cd-161">Suppose you want to have the Spanish translation, then run the following command:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a><span data-ttu-id="fa7cd-162">Alterar o nome de exibição do grupo Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fa7cd-162">Change the display name of the Microsoft 365 Group</span></span>

<span data-ttu-id="fa7cd-163">O nome de exibição especifica o nome do grupo Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-163">The display name specifies the name of the Microsoft 365 Group.</span></span> <span data-ttu-id="fa7cd-164">Você pode ver esse nome no centro de administração do Exchange ou no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-164">You can see this name in your exchange admin center or Microsoft 365 admin center.</span></span> <span data-ttu-id="fa7cd-165">Você pode editar o nome de exibição do grupo ou atribuir um nome de exibição a um grupo existente do Microsoft 365 executando o comando Set-Unified Group:</span><span class="sxs-lookup"><span data-stu-id="fa7cd-165">You can edit the display name of the group or assign a display name to an existing Microsoft 365 Group by running the Set-UnifiedGroup command:</span></span>

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a><span data-ttu-id="fa7cd-166">Alterar a configuração padrão de grupos do Microsoft 365 para Outlook para público ou privado</span><span class="sxs-lookup"><span data-stu-id="fa7cd-166">Change the default setting of Microsoft 365 Groups for Outlook to Public or Private</span></span>
<span data-ttu-id="fa7cd-167"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="fa7cd-167"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="fa7cd-168">Os grupos do Microsoft 365 no Outlook são criados como particulares por padrão.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-168">Microsoft 365 Groups in Outlook are created as Private by default.</span></span> <span data-ttu-id="fa7cd-169">Se sua organização deseja que os grupos do Microsoft 365 sejam criados como públicos por padrão (ou de volta para privado), use esta sintaxe de cmdlet do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fa7cd-169">If your organization wants Microsoft 365 Groups to be created as Public by default (or back to Private), use this PowerShell cmdlet syntax:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

<span data-ttu-id="fa7cd-170">Para definir como particular:</span><span class="sxs-lookup"><span data-stu-id="fa7cd-170">To set to Private:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

<span data-ttu-id="fa7cd-171">Para verificar a configuração:</span><span class="sxs-lookup"><span data-stu-id="fa7cd-171">To verify the setting:</span></span>

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

<span data-ttu-id="fa7cd-172">Para saber mais, confira [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) e [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig).</span><span class="sxs-lookup"><span data-stu-id="fa7cd-172">To learn more, see [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) and [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig).</span></span>

## <a name="microsoft-365-groups-cmdlets"></a><span data-ttu-id="fa7cd-173">Cmdlets de grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fa7cd-173">Microsoft 365 Groups cmdlets</span></span>

<span data-ttu-id="fa7cd-174">Os cmdlets a seguir podem ser usados com os grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-174">The following cmdlets can be used with Microsoft 365 Groups.</span></span>

|<span data-ttu-id="fa7cd-175">**Nome do cmdlet**</span><span class="sxs-lookup"><span data-stu-id="fa7cd-175">**Cmdlet name**</span></span>|<span data-ttu-id="fa7cd-176">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="fa7cd-176">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="fa7cd-177">Obter-Unificação de um</span><span class="sxs-lookup"><span data-stu-id="fa7cd-177">Get-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616182) <br/> |<span data-ttu-id="fa7cd-178">Use este cmdlet para pesquisar os grupos existentes do Microsoft 365 e para exibir as propriedades do objeto Group</span><span class="sxs-lookup"><span data-stu-id="fa7cd-178">Use this cmdlet to look up existing Microsoft 365 Groups, and to view properties of the group object</span></span>  <br/> |
|[<span data-ttu-id="fa7cd-179">Conjunto-unificado</span><span class="sxs-lookup"><span data-stu-id="fa7cd-179">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189) <br/> |<span data-ttu-id="fa7cd-180">Atualizar as propriedades de um grupo específico do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fa7cd-180">Update the properties of a specific Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="fa7cd-181">Novo-unificado</span><span class="sxs-lookup"><span data-stu-id="fa7cd-181">New-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616183) <br/> |<span data-ttu-id="fa7cd-182">Criar um novo grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-182">Create a new Microsoft 365 Group.</span></span> <span data-ttu-id="fa7cd-183">Este cmdlet fornece um conjunto mínimo de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-183">This cmdlet provides a minimal set of parameters.</span></span> <span data-ttu-id="fa7cd-184">Para definir valores para propriedades estendidas, use set-Unified Group após criar o novo grupo</span><span class="sxs-lookup"><span data-stu-id="fa7cd-184">To set values for extended properties, use Set-UnifiedGroup after creating the new group</span></span>  <br/> |
|[<span data-ttu-id="fa7cd-185">Remover-unificado</span><span class="sxs-lookup"><span data-stu-id="fa7cd-185">Remove-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616186) <br/> |<span data-ttu-id="fa7cd-186">Excluir um grupo existente do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fa7cd-186">Delete an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="fa7cd-187">Get-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="fa7cd-187">Get-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616194) <br/> |<span data-ttu-id="fa7cd-188">Recuperar informações de associação e proprietário para um grupo do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fa7cd-188">Retrieve membership and owner information for a Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="fa7cd-189">Add-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="fa7cd-189">Add-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616191) <br/> |<span data-ttu-id="fa7cd-190">Adicionar centenas ou milhares de usuários ou novos proprietários a um grupo existente do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fa7cd-190">Add hundreds or thousands of users, or new owners, to an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="fa7cd-191">Remove-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="fa7cd-191">Remove-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616195) <br/> |<span data-ttu-id="fa7cd-192">Remover proprietários e membros de um grupo existente do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fa7cd-192">Remove owners and members from an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="fa7cd-193">Get-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="fa7cd-193">Get-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536510) <br/> |<span data-ttu-id="fa7cd-194">Usado para exibir informações sobre a foto do usuário associada a uma conta.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-194">Used to view information about the user photo associated with an account.</span></span> <span data-ttu-id="fa7cd-195">As fotos do usuário são armazenadas no Active Directory</span><span class="sxs-lookup"><span data-stu-id="fa7cd-195">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="fa7cd-196">Set-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="fa7cd-196">Set-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536511) <br/> |<span data-ttu-id="fa7cd-197">Usado para associar uma foto de usuário a uma conta.</span><span class="sxs-lookup"><span data-stu-id="fa7cd-197">Used to associate a user photo with an account.</span></span> <span data-ttu-id="fa7cd-198">As fotos do usuário são armazenadas no Active Directory</span><span class="sxs-lookup"><span data-stu-id="fa7cd-198">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="fa7cd-199">Remove-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="fa7cd-199">Remove-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536512) <br/> |<span data-ttu-id="fa7cd-200">Remover a foto de um grupo do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fa7cd-200">Remove the photo for an Microsoft 365 Group</span></span>  <br/> |

## <a name="related-topics"></a><span data-ttu-id="fa7cd-201">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="fa7cd-201">Related topics</span></span>

[<span data-ttu-id="fa7cd-202">Atualizar listas de distribuição para grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fa7cd-202">Upgrade distribution lists to Microsoft 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)

[<span data-ttu-id="fa7cd-203">Gerenciar quem pode criar grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fa7cd-203">Manage who can create Microsoft 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)

[<span data-ttu-id="fa7cd-204">Gerenciar o acesso de convidados aos grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fa7cd-204">Manage guest access to Microsoft 365 Groups</span></span>](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[<span data-ttu-id="fa7cd-205">Alterar a associação de grupo estático para dinâmico no</span><span class="sxs-lookup"><span data-stu-id="fa7cd-205">Change static group membership to dynamic in</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)
