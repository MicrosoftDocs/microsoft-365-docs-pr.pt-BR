---
title: Gerenciar grupos do Microsoft 365 com o PowerShell
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
description: Neste artigo, saiba como realizar tarefas comuns de gerenciamento para grupos do Microsoft 365 no PowerShell.
ms.openlocfilehash: 1cad2aa39a6b106cbb4dbfbafa995899b2442ed1
ms.sourcegitcommit: 9d1351ea6d9942550b52132817f9f9693ddef2fd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/02/2020
ms.locfileid: "48830610"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a><span data-ttu-id="bd822-103">Gerenciar grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd822-103">Manage Microsoft 365 Groups with PowerShell</span></span>

<span data-ttu-id="bd822-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="bd822-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="bd822-105">Este artigo fornece as etapas para realizar tarefas comuns de gerenciamento para Grupos no Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd822-105">This article provides the steps for doing common management tasks for Groups in Microsoft PowerShell.</span></span> <span data-ttu-id="bd822-106">Ele também lista os cmdlets do PowerShell para Grupos.</span><span class="sxs-lookup"><span data-stu-id="bd822-106">It also lists the PowerShell cmdlets for Groups.</span></span> <span data-ttu-id="bd822-107">Para obter informações sobre como gerenciar sites do SharePoint, consulte [Gerenciar sites do SharePoint Online usando o PowerShell.](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="bd822-107">For info about managing SharePoint sites, see [Manage SharePoint Online sites using PowerShell](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell).</span></span>

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a><span data-ttu-id="bd822-108">Link para suas diretrizes de uso dos Grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bd822-108">Link to your Microsoft 365 Groups usage guidelines</span></span>
<span data-ttu-id="bd822-109"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="bd822-109"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="bd822-110">Quando os [usuários criam ou editam um grupo](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx)no Outlook, você pode mostrar a eles um link para as diretrizes de uso da sua organização.</span><span class="sxs-lookup"><span data-stu-id="bd822-110">When users [create or edit a group in Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx), you can show them a link to your organization's usage guidelines.</span></span> <span data-ttu-id="bd822-111">Por exemplo, se você precisar que um prefixo ou sufixo específico seja adicionado a um nome de grupo.</span><span class="sxs-lookup"><span data-stu-id="bd822-111">For example, if you require a specific prefix or suffix to be added to a group name.</span></span>

<span data-ttu-id="bd822-112">Use o PowerShell do Azure Active Directory (Azure AD) para apontar os usuários para as diretrizes de uso da sua organização para grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bd822-112">Use the Azure Active Directory (Azure AD) PowerShell to point your users to your organization's usage guidelines for Microsoft 365 groups.</span></span> <span data-ttu-id="bd822-113">Confira os [cmdlets do Azure Active Directory](https://go.microsoft.com/fwlink/?LinkID=827484) para definir  as configurações de grupo e siga as etapas nas configurações Criar no nível de diretório para definir o hiperlink de diretriz de uso.</span><span class="sxs-lookup"><span data-stu-id="bd822-113">Check out [Azure Active Directory cmdlets for configuring group settings](https://go.microsoft.com/fwlink/?LinkID=827484) and follow the steps in the **Create settings at the directory level** to define the usage guideline hyperlink.</span></span> <span data-ttu-id="bd822-114">Depois de executar o cmdlet do AAD, os usuários verão o link para suas diretrizes quando criarem ou editarem um grupo no Outlook.</span><span class="sxs-lookup"><span data-stu-id="bd822-114">Once you run the AAD cmdlet, user's will see the link to your guidelines when they create or edit a group in Outlook.</span></span>

![Criar um novo grupo com o link de diretrizes de uso](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![Clique em Diretrizes de uso do grupo para ver as diretrizes de grupos do Office 365 de suas organizações](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a><span data-ttu-id="bd822-117">Permitir que os usuários enviem como o grupo do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bd822-117">Allow users to Send as the Microsoft 365 Group</span></span>
<span data-ttu-id="bd822-118"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="bd822-118"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="bd822-119">Se você quiser habilitar seus grupos do Microsoft 365 para "Enviar como", use os cmdlets [Add-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/add-recipientpermission) e [Get-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/get-recipientpermission) para configurar isso.</span><span class="sxs-lookup"><span data-stu-id="bd822-119">If you want to enable your Microsoft 365 groups to "Send As", use the [Add-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/add-recipientpermission) and [Get-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/get-recipientpermission) cmdlets to configure this.</span></span> <span data-ttu-id="bd822-120">Depois de habilitar essa configuração, os usuários do grupo do Microsoft 365 podem usar o Outlook ou o Outlook na Web para enviar e responder a emails como o grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bd822-120">Once you enable this setting, Microsoft 365 group users can use Outlook or Outlook on the web to send and reply to email as the Microsoft 365 group.</span></span> <span data-ttu-id="bd822-121">Os usuários podem ir para o grupo, criar um novo email e alterar o campo "Enviar como" para o endereço de email do grupo.</span><span class="sxs-lookup"><span data-stu-id="bd822-121">Users can go to the group, create a new email, and change the "Send As" field to the group's email address.</span></span>

<span data-ttu-id="bd822-122">([Você também pode fazer isso no Centro de Administração do Exchange.)](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group)</span><span class="sxs-lookup"><span data-stu-id="bd822-122">([You can also do this in the Exchange Admin Center](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group).)</span></span>

<span data-ttu-id="bd822-123">Use o script a seguir, substituindo pelo alias do grupo que você deseja atualizar e pelo alias do usuário para o qual você *\<GroupAlias\>* *\<UserAlias\>* deseja conceder permissões.</span><span class="sxs-lookup"><span data-stu-id="bd822-123">Use the following script, replacing *\<GroupAlias\>* with the alias of the group that you want to update, and *\<UserAlias\>* with the alias of the user to whom you want to grant permissions.</span></span> <span data-ttu-id="bd822-124">[Conecte-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) para executar esse script.</span><span class="sxs-lookup"><span data-stu-id="bd822-124">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) to run this script.</span></span>

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

<span data-ttu-id="bd822-125">Depois que o cmdlet é executado, os usuários podem ir para o Outlook ou o Outlook na Web para enviar como o grupo, adicionando o endereço de email do grupo ao **campo** De.</span><span class="sxs-lookup"><span data-stu-id="bd822-125">Once the cmdlet is executed, users can go to Outlook or Outlook on the web to send as the group, by adding the group email address to the **From** field.</span></span>

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a><span data-ttu-id="bd822-126">Criar classificações para Grupos do Microsoft 365 em sua organização</span><span class="sxs-lookup"><span data-stu-id="bd822-126">Create classifications for Microsoft 365 Groups in your organization</span></span>

<span data-ttu-id="bd822-127">Você pode criar rótulos de sensibilidade que os usuários em sua organização podem definir ao criar um Grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bd822-127">You can create sensitivity labels that the users in your organization can set when they create a Microsoft 365 Group.</span></span> <span data-ttu-id="bd822-128">Se você quiser classificar grupos, recomendamos usar rótulos de sensibilidade em vez do recurso de classificação de grupos anteriores.</span><span class="sxs-lookup"><span data-stu-id="bd822-128">If you want to classify groups, we recommend using sensitivity labels instead of the previous groups classification feature.</span></span> <span data-ttu-id="bd822-129">Para saber mais sobre como usar rótulos de sensibilidade, confira Usar rótulos de sensibilidade para proteger o conteúdo no Microsoft Teams, grupos do [Microsoft 365 e sites do SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)</span><span class="sxs-lookup"><span data-stu-id="bd822-129">For information about using sensitivity labels, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd822-130">Se você estiver usando rótulos de classificação no momento, eles não estarão mais disponíveis para usuários que criam grupos depois que os rótulos de sensibilidade são habilitados.</span><span class="sxs-lookup"><span data-stu-id="bd822-130">If you are currently using classification labels, they will no longer be available to users who create groups once sensitivity labels are enabled.</span></span>

<span data-ttu-id="bd822-131">Você ainda pode usar o recurso de classificação de grupos anterior.</span><span class="sxs-lookup"><span data-stu-id="bd822-131">You can still use the previous groups classification feature.</span></span> <span data-ttu-id="bd822-132">Você pode criar classificações que os usuários em sua organização podem definir ao criar um Grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bd822-132">You can create classifications that the users in your organization can set when they create an Microsoft 365 Group.</span></span> <span data-ttu-id="bd822-133">Por exemplo, você pode permitir que os usuários de definir "Padrão", "Segredo" e "Segredo Superior" em grupos que eles criam.</span><span class="sxs-lookup"><span data-stu-id="bd822-133">For example, you can allow users to set "Standard", "Secret", and "Top Secret" on groups they create.</span></span> <span data-ttu-id="bd822-134">As classificações de grupo não são definidas por padrão e você precisa criar para que seus usuários as deem.</span><span class="sxs-lookup"><span data-stu-id="bd822-134">Group classifications aren't set by default and you need to create it in order for your users to set it.</span></span> <span data-ttu-id="bd822-135">Use o PowerShell do Azure Active Directory para apontar seus usuários para as diretrizes de uso da sua organização para Grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bd822-135">Use Azure Active Directory PowerShell to point your users to your organization's usage guidelines for Microsoft 365 Groups.</span></span>

<span data-ttu-id="bd822-136">Confira os [cmdlets do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets) para definir  as configurações de grupo e siga as etapas nas configurações Criar no nível de diretório para definir a classificação dos Grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bd822-136">Check out [Azure Active Directory cmdlets for configuring group settings](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets) and follow the steps in the **Create settings at the directory level** to define the classification for Microsoft 365 Groups.</span></span>

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

<span data-ttu-id="bd822-137">Para associar uma descrição a cada classificação, você pode usar o atributo  *ClassificationDescriptions de configurações* para definir.</span><span class="sxs-lookup"><span data-stu-id="bd822-137">In order to associate a description to each classification you can use the settings attribute  *ClassificationDescriptions* to define.</span></span>

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

<span data-ttu-id="bd822-138">onde Classificação corresponde às cadeias de caracteres na ClassificationList.</span><span class="sxs-lookup"><span data-stu-id="bd822-138">where Classification matches the strings in the ClassificationList.</span></span>

<span data-ttu-id="bd822-139">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="bd822-139">Example:</span></span>

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

<span data-ttu-id="bd822-140">Depois de executar o cmdlet acima do Azure Active Directory para definir sua classificação, execute o cmdlet [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) se quiser definir a classificação para um grupo específico.</span><span class="sxs-lookup"><span data-stu-id="bd822-140">After you run the above Azure Active Directory cmdlet to set your classification, run the [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) cmdlet if you want to set the classification for a specific group.</span></span>

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

<span data-ttu-id="bd822-141">Ou crie um novo grupo com uma classificação.</span><span class="sxs-lookup"><span data-stu-id="bd822-141">Or create a new group with a classification.</span></span>

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

<span data-ttu-id="bd822-142">Confira o [uso do PowerShell com o Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) e conecte-se ao [PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) do Exchange Online para obter mais detalhes sobre como usar o PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="bd822-142">Check out [Using PowerShell with Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) for more details on using Exchange Online PowerShell.</span></span>

<span data-ttu-id="bd822-143">Depois que essas configurações são habilitadas, o proprietário do grupo poderá escolher uma classificação no menu  suspenso no Outlook na Web e no Outlook e salvá-la na página Editar grupo.</span><span class="sxs-lookup"><span data-stu-id="bd822-143">Once these settings are enabled, the group owner will be able to choose a classification from the drop down menu in Outlook on the Web and Outlook, and save it from the **Edit** group page.</span></span>

![Escolha a classificação de grupo do Microsoft 365](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a><span data-ttu-id="bd822-145">Ocultar grupos do Microsoft 365 da lista de endereços global.</span><span class="sxs-lookup"><span data-stu-id="bd822-145">Hide Microsoft 365 Groups from the global address list.</span></span>
<span data-ttu-id="bd822-146"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="bd822-146"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="bd822-147">Você pode especificar se um Grupo do Microsoft 365 aparece na GAL (lista de endereços global) e em outras listas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="bd822-147">You can specify whether a Microsoft 365 Group appears in the global address list (GAL) and other lists in your organization.</span></span> <span data-ttu-id="bd822-148">Por exemplo, se você tiver um grupo de departamento jurídico que não deseja exibir na lista de endereços, poderá impedir que esse grupo apareça na GAL.</span><span class="sxs-lookup"><span data-stu-id="bd822-148">For example, if you have a legal department group that you don't want to show up in the address list, you can stop that group from appearing in the GAL.</span></span> <span data-ttu-id="bd822-149">Execute o cmdlet Set-Unified Group para ocultar o grupo da lista de endereços da forma a seguir:</span><span class="sxs-lookup"><span data-stu-id="bd822-149">Run the Set-Unified Group cmdlet to hide the group from the address list like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a><span data-ttu-id="bd822-150">Permitir que apenas usuários internos enviem mensagens aos Grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bd822-150">Allow only internal users to send message to Microsoft 365 Groups</span></span>
<span data-ttu-id="bd822-151"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="bd822-151"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="bd822-152">Se não quiser que os usuários de outras organizações enviem emails para um grupo do Microsoft 365, você pode alterar as configurações para esse grupo.</span><span class="sxs-lookup"><span data-stu-id="bd822-152">If you don't want users from other organizations to send emails to a Microsoft 365 Group, you can change the settings for that group.</span></span> <span data-ttu-id="bd822-153">Ele permitirá que apenas usuários internos enviem um email para o seu grupo.</span><span class="sxs-lookup"><span data-stu-id="bd822-153">It will allow only internal users to send an email to your group.</span></span> <span data-ttu-id="bd822-154">Se um usuário externo tentar enviar uma mensagem para esse grupo, ela será rejeitada.</span><span class="sxs-lookup"><span data-stu-id="bd822-154">If an external user tries to send a message to that group, it will be rejected.</span></span>

<span data-ttu-id="bd822-155">Execute o Set-UnifiedGroup cmdlet para atualizar essa configuração, desta forma:</span><span class="sxs-lookup"><span data-stu-id="bd822-155">Run the Set-UnifiedGroup cmdlet to update this setting, like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a><span data-ttu-id="bd822-156">Adicionar Dicas de Email aos Grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bd822-156">Add MailTips to Microsoft 365 Groups</span></span>
<span data-ttu-id="bd822-157"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="bd822-157"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="bd822-158">Sempre que um remetente tentar enviar um email para um grupo do Microsoft 365, uma Dica de Email poderá ser mostrada a ele.</span><span class="sxs-lookup"><span data-stu-id="bd822-158">Whenever a sender tries to send an email to a Microsoft 365 Group, a MailTip can be shown to them.</span></span>

<span data-ttu-id="bd822-159">Execute o cmdlet Set-Unified Group para adicionar uma dica de email ao grupo:</span><span class="sxs-lookup"><span data-stu-id="bd822-159">Run the Set-Unified Group cmdlet to add a mailTip to the group:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

<span data-ttu-id="bd822-160">Além de MailTip, você também pode definir MailTipTranslations, que especifica idiomas adicionais para a Dica de Email.</span><span class="sxs-lookup"><span data-stu-id="bd822-160">Along with MailTip, you can also set MailTipTranslations, which specifies additional languages for the MailTip.</span></span> <span data-ttu-id="bd822-161">Suponha que você queira ter a tradução em espanhol e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="bd822-161">Suppose you want to have the Spanish translation, then run the following command:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a><span data-ttu-id="bd822-162">Alterar o nome de exibição do Grupo do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bd822-162">Change the display name of the Microsoft 365 Group</span></span>

<span data-ttu-id="bd822-163">O nome de exibição especifica o nome do Grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bd822-163">The display name specifies the name of the Microsoft 365 Group.</span></span> <span data-ttu-id="bd822-164">Você pode ver esse nome no centro de administração do Exchange ou no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bd822-164">You can see this name in your exchange admin center or Microsoft 365 admin center.</span></span> <span data-ttu-id="bd822-165">Você pode editar o nome de exibição do grupo ou atribuir um nome de exibição a um grupo existente do Microsoft 365 executando o Set-UnifiedGroup comando:</span><span class="sxs-lookup"><span data-stu-id="bd822-165">You can edit the display name of the group or assign a display name to an existing Microsoft 365 Group by running the Set-UnifiedGroup command:</span></span>

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a><span data-ttu-id="bd822-166">Alterar a configuração padrão dos Grupos do Microsoft 365 para Outlook para Público ou Privado</span><span class="sxs-lookup"><span data-stu-id="bd822-166">Change the default setting of Microsoft 365 Groups for Outlook to Public or Private</span></span>
<span data-ttu-id="bd822-167"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="bd822-167"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="bd822-168">Os Grupos do Microsoft 365 no Outlook são criados como Particulares por padrão.</span><span class="sxs-lookup"><span data-stu-id="bd822-168">Microsoft 365 Groups in Outlook are created as Private by default.</span></span> <span data-ttu-id="bd822-169">Se sua organização deseja que os Grupos do Microsoft 365 sejam criados como Públicos por padrão (ou de volta para Privado), use esta sintaxe de cmdlet do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bd822-169">If your organization wants Microsoft 365 Groups to be created as Public by default (or back to Private), use this PowerShell cmdlet syntax:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

<span data-ttu-id="bd822-170">Para definir como Private:</span><span class="sxs-lookup"><span data-stu-id="bd822-170">To set to Private:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

<span data-ttu-id="bd822-171">Para verificar a configuração:</span><span class="sxs-lookup"><span data-stu-id="bd822-171">To verify the setting:</span></span>

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

<span data-ttu-id="bd822-172">Para saber mais, consulte [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) e [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig).</span><span class="sxs-lookup"><span data-stu-id="bd822-172">To learn more, see [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) and [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig).</span></span>

## <a name="microsoft-365-groups-cmdlets"></a><span data-ttu-id="bd822-173">Cmdlets de grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bd822-173">Microsoft 365 Groups cmdlets</span></span>

<span data-ttu-id="bd822-174">Os cmdlets a seguir podem ser usados com grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bd822-174">The following cmdlets can be used with Microsoft 365 Groups.</span></span>

|<span data-ttu-id="bd822-175">**Nome do cmdlet**</span><span class="sxs-lookup"><span data-stu-id="bd822-175">**Cmdlet name**</span></span>|<span data-ttu-id="bd822-176">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="bd822-176">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="bd822-177">Get-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="bd822-177">Get-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616182) <br/> |<span data-ttu-id="bd822-178">Use este cmdlet para procurar grupos existentes do Microsoft 365 e para exibir as propriedades do objeto de grupo</span><span class="sxs-lookup"><span data-stu-id="bd822-178">Use this cmdlet to look up existing Microsoft 365 Groups, and to view properties of the group object</span></span>  <br/> |
|[<span data-ttu-id="bd822-179">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="bd822-179">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189) <br/> |<span data-ttu-id="bd822-180">Atualizar as propriedades de um grupo específico do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bd822-180">Update the properties of a specific Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="bd822-181">New-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="bd822-181">New-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616183) <br/> |<span data-ttu-id="bd822-182">Crie um novo Grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bd822-182">Create a new Microsoft 365 Group.</span></span> <span data-ttu-id="bd822-183">Este cmdlet fornece um conjunto mínimo de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="bd822-183">This cmdlet provides a minimal set of parameters.</span></span> <span data-ttu-id="bd822-184">Para definir valores para propriedades estendidas, use Set-UnifiedGroup depois de criar o novo grupo</span><span class="sxs-lookup"><span data-stu-id="bd822-184">To set values for extended properties, use Set-UnifiedGroup after creating the new group</span></span>  <br/> |
|[<span data-ttu-id="bd822-185">Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="bd822-185">Remove-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616186) <br/> |<span data-ttu-id="bd822-186">Excluir um grupo existente do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bd822-186">Delete an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="bd822-187">Get-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="bd822-187">Get-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616194) <br/> |<span data-ttu-id="bd822-188">Recuperar informações de associação e proprietário de um grupo do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bd822-188">Retrieve membership and owner information for a Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="bd822-189">Add-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="bd822-189">Add-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616191) <br/> |<span data-ttu-id="bd822-190">Adicionar membros, proprietários e assinantes a um grupo existente do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bd822-190">Add members, owners, and subscribers to an existing Microsoft 365 Group</span></span> <br/> |
|[<span data-ttu-id="bd822-191">Remove-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="bd822-191">Remove-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616195) <br/> |<span data-ttu-id="bd822-192">Remover proprietários e membros de um grupo existente do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bd822-192">Remove owners and members from an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="bd822-193">Get-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="bd822-193">Get-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536510) <br/> |<span data-ttu-id="bd822-194">Usado para exibir informações sobre a foto do usuário associada a uma conta.</span><span class="sxs-lookup"><span data-stu-id="bd822-194">Used to view information about the user photo associated with an account.</span></span> <span data-ttu-id="bd822-195">As fotos do usuário são armazenadas no Active Directory</span><span class="sxs-lookup"><span data-stu-id="bd822-195">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="bd822-196">Set-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="bd822-196">Set-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536511) <br/> |<span data-ttu-id="bd822-197">Usado para associar uma foto de usuário a uma conta.</span><span class="sxs-lookup"><span data-stu-id="bd822-197">Used to associate a user photo with an account.</span></span> <span data-ttu-id="bd822-198">As fotos do usuário são armazenadas no Active Directory</span><span class="sxs-lookup"><span data-stu-id="bd822-198">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="bd822-199">Remove-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="bd822-199">Remove-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536512) <br/> |<span data-ttu-id="bd822-200">Remover a foto de um grupo do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bd822-200">Remove the photo for an Microsoft 365 Group</span></span>  <br/> |

## <a name="related-topics"></a><span data-ttu-id="bd822-201">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="bd822-201">Related topics</span></span>

[<span data-ttu-id="bd822-202">Atualizar listas de distribuição para Grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bd822-202">Upgrade distribution lists to Microsoft 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)

[<span data-ttu-id="bd822-203">Gerenciar quem pode criar Grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bd822-203">Manage who can create Microsoft 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)

[<span data-ttu-id="bd822-204">Gerenciar o acesso de convidados aos Grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bd822-204">Manage guest access to Microsoft 365 Groups</span></span>](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[<span data-ttu-id="bd822-205">Alterar a associação de grupo estático para dinâmica em</span><span class="sxs-lookup"><span data-stu-id="bd822-205">Change static group membership to dynamic in</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)
