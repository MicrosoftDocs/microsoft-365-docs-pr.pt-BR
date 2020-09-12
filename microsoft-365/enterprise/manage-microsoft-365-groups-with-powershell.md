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
ms.openlocfilehash: a02990b2890d9fdfd523209e1d912aafdaeac091
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547921"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a>Gerenciar os grupos do Microsoft 365 com o PowerShell

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

Este artigo fornece as etapas para realizar tarefas comuns de gerenciamento para grupos no Microsoft PowerShell. Ele também lista os cmdlets do PowerShell para grupos. Para obter informações sobre como gerenciar sites do SharePoint, confira [gerenciar sites do SharePoint online usando o PowerShell](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell).

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a>Link para suas diretrizes de uso de grupos do Microsoft 365
<a name="BK_LinkToGuideLines"> </a>

Quando os usuários [criarem ou editarem um grupo no Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx), você poderá mostrar um link para as diretrizes de uso da sua organização. Por exemplo, se você precisar adicionar um prefixo ou sufixo específico a um nome de grupo.

Use o PowerShell do Azure Active Directory (Azure AD) para apontar seus usuários para as diretrizes de uso da sua organização para os grupos do Microsoft 365. Confira os [cmdlets do Azure Active Directory para definir as configurações de grupo](https://go.microsoft.com/fwlink/?LinkID=827484) e siga as etapas em **criar configurações no nível do diretório** para definir o hiperlink de diretriz de uso. Depois de executar o cmdlet AAD, o usuário verá o link para suas diretrizes ao criar ou editar um grupo no Outlook.

![Criar um novo grupo com o link de diretrizes de uso](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![Clique em diretrizes de uso de grupo para ver as diretrizes de grupos do Office 365](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a>Permitir que os usuários enviem como o grupo Microsoft 365
<a name="BK_LinkToGuideLines"> </a>

Se você deseja habilitar seus grupos do Microsoft 365 para "enviar como", use os cmdlets [Add-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/add-recipientpermission) e [Get-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/get-recipientpermission) para configurá-lo. Após habilitar essa configuração, os usuários do grupo do Microsoft 365 podem usar o Outlook ou o Outlook na Web para enviar e responder a email como o grupo do Microsoft 365. Os usuários podem ir para o grupo, criar um novo email e alterar o campo "enviar como" para o endereço de email do grupo.

([Você também pode fazer isso no centro de administração do Exchange](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group).)

Use o script a seguir, substituindo *\<GroupAlias\>* com o alias do grupo que você deseja atualizar e *\<UserAlias\>* com o alias do usuário para o qual você deseja conceder permissões. [Conectar-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) para executar esse script.

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

Depois que o cmdlet é executado, os usuários podem acessar o Outlook ou o Outlook na Web para enviar como o grupo, adicionando o endereço de email do grupo ao campo **de** .

## <a name="create-classifications-for-office-groups-in-your-organization"></a>Criar classificações para grupos do Office em sua organização

Você pode criar rótulos de confidencialidade que os usuários em sua organização podem definir quando criarem um grupo do Microsoft 365. Se você quiser classificar grupos, recomendamos usar rótulos de confidencialidade em vez do recurso de classificação de grupos anterior. Para obter informações sobre como usar rótulos de confidencialidade, confira [usar rótulos de sensibilidade para proteger o conteúdo no Microsoft Teams, microsoft 365 Groups e sites do SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

> [!IMPORTANT]
> Se você estiver usando rótulos de classificação no momento, eles não estarão mais disponíveis aos usuários que criam grupos depois que os rótulos de sensibilidade estiverem habilitados.

Você ainda pode usar o recurso de classificação de grupos anterior. Você pode criar classificações que os usuários em sua organização podem definir quando criarem um grupo do Office 365. Por exemplo, você pode permitir que os usuários definam "Standard", "Secret" e "Top Secret" em grupos criados. As classificações de grupo não são definidas por padrão e você precisa criá-las para que os usuários a definam. Use o PowerShell do Azure Active Directory para apontar seus usuários para as diretrizes de uso da sua organização para grupos do Office 365.

Confira os [cmdlets do Azure Active Directory para definir as configurações de grupo](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets) e siga as etapas em **criar configurações no nível do diretório** para definir a classificação dos grupos do Office 365.

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

Para associar uma descrição a cada classificação, você pode usar o atributo de configurações  *ClassificationDescriptions* para definir.

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

em que a classificação corresponde às cadeias de caracteres na classificação.

Exemplo:

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

Depois de executar o cmdlet acima do Active Directory do Azure para definir sua classificação, execute o cmdlet [set-unificado](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) , se quiser definir a classificação de um grupo específico.

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

Ou criar um novo grupo com uma classificação.

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

Confira [usando o PowerShell com o Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) e [Conecte-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) para obter mais detalhes sobre como usar o PowerShell do Exchange Online.

Depois que essas configurações forem habilitadas, o proprietário do grupo poderá escolher uma classificação no menu suspenso no Outlook na Web e no Outlook e salvá-la na página **Editar** grupo.

![Escolha a classificação de grupo do Office 365](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-office-365-groups-from-gal"></a>Ocultar grupos do Office 365 da GAL
<a name="BKMK_CreateClassification"> </a>

Você pode especificar se um grupo do Office 365 aparece na lista de endereços global (GAL) e em outras listas em sua organização. Por exemplo, se você tiver um grupo de departamento jurídico que não deseja exibir na lista de endereços, você pode impedir que esse grupo apareça na GAL. Execute o cmdlet Set-Unified Group para ocultar o grupo da lista de endereços da seguinte maneira:

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-office-365-group"></a>Permitir que somente usuários internos enviem mensagens para o grupo do Office 365
<a name="BKMK_CreateClassification"> </a>

Se não quiser que os usuários de outra organização enviem emails para um grupo do Office 365, você poderá alterar as configurações desse grupo. Ele permitirá que apenas usuários internos enviem um email para o seu grupo. Se o usuário externo tentar enviar uma mensagem para esse grupo, ele será rejeitado.

Execute o cmdlet Set-unificado para atualizar essa configuração, da seguinte maneira:

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-the-office-365-groups"></a>Adicionar dicas de correio aos grupos do Office 365
<a name="BKMK_CreateClassification"> </a>

Sempre que um remetente tenta enviar um email a um grupo do Office 365, uma dica de email pode ser exibida para eles.

Execute o cmdlet Set-Unified Group para adicionar uma dica de tela ao grupo:

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

Juntamente com as dicas de dicas, você também pode definir MailTipTranslations, que especifica idiomas adicionais para a dica de a. Suponha que você deseja ter a tradução para espanhol e, em seguida, execute o seguinte comando:

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-display-name-of-the-office-365-group"></a>Alterar o nome de exibição do grupo do Office 365

Nome para exibição especifica o nome do grupo do Office 365. Você pode ver esse nome no centro de administração do Exchange ou no centro de administração do Microsoft 365. Você pode editar o nome de exibição do grupo ou atribuir um nome para exibição a um grupo existente do Office 365 executando o comando Set-Unified Group:

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-office-365-groups-for-outlook-to-public-or-private"></a>Alterar a configuração padrão dos grupos do Office 365 para o Outlook para público ou privado
<a name="BKMK_CreateClassification"> </a>

Os grupos do Office 365 no Outlook são criados como particulares por padrão. Se sua organização deseja que os grupos do Office 365 sejam criados como públicos por padrão (ou de volta para privado), use esta sintaxe de cmdlet do PowerShell:

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

Para definir como particular:

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

Para verificar a configuração:

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

Para saber mais, confira [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) e [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig).

## <a name="office-365-groups-cmdlets"></a>Cmdlets de grupos do Office 365

Os cmdlets a seguir podem ser usados com grupos do Office 365.

|**Nome do cmdlet**|**Descrição**|
|:-----|:-----|
|[Obter-Unificação de um](https://go.microsoft.com/fwlink/p/?LinkId=616182) <br/> |Use este cmdlet para pesquisar grupos existentes do Office 365 e para exibir as propriedades do objeto Group  <br/> |
|[Conjunto-unificado](https://go.microsoft.com/fwlink/p/?LinkId=616189) <br/> |Atualizar as propriedades de um grupo específico do Office 365  <br/> |
|[Novo-unificado](https://go.microsoft.com/fwlink/p/?LinkId=616183) <br/> |Criar um novo grupo do Office 365. Este cmdlet fornece um conjunto mínimo de parâmetros, para definir valores para propriedades estendidas use set-Unified Group depois de criar o novo grupo  <br/> |
|[Remover-unificado](https://go.microsoft.com/fwlink/p/?LinkId=616186) <br/> |Excluir um grupo existente do Office 365  <br/> |
|[Get-UnifiedGroupLinks](https://go.microsoft.com/fwlink/p/?LinkId=616194) <br/> |Recuperar informações de associação e de proprietário de um grupo do Office 365  <br/> |
|[Add-UnifiedGroupLinks](https://go.microsoft.com/fwlink/p/?LinkId=616191) <br/> |Adicionar centenas ou milhares de usuários, ou novos proprietários, a um grupo existente do Office 365  <br/> |
|[Remove-UnifiedGroupLinks](https://go.microsoft.com/fwlink/p/?LinkId=616195) <br/> |Remover proprietários e membros de um grupo existente do Office 365  <br/> |
|[Get-UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536510) <br/> |Usado para exibir informações sobre a foto do usuário associada a uma conta. As fotos do usuário são armazenadas no Active Directory  <br/> |
|[Set-UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536511) <br/> |Usado para associar uma foto de usuário a uma conta. As fotos do usuário são armazenadas no Active Directory  <br/> |
|[Remove-UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536512) <br/> |Remover a foto de um grupo do Office 365  <br/> |

## <a name="related-topics"></a>Tópicos relacionados

[Atualizar listas de distribuição para grupos do Office 365](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)

[Gerenciar quem pode criar grupos do Office 365](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)

[Gerenciar o acesso de convidados aos Grupos do Office 365](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Alterar a associação de grupo estático para dinâmico no](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)
