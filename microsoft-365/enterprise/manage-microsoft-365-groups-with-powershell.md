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
# <a name="manage-microsoft-365-groups-with-powershell"></a>Gerenciar grupos do Microsoft 365 com o PowerShell

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Este artigo fornece as etapas para realizar tarefas comuns de gerenciamento para Grupos no Microsoft PowerShell. Ele também lista os cmdlets do PowerShell para Grupos. Para obter informações sobre como gerenciar sites do SharePoint, consulte [Gerenciar sites do SharePoint Online usando o PowerShell.](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell)

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a>Link para suas diretrizes de uso dos Grupos do Microsoft 365
<a name="BK_LinkToGuideLines"> </a>

Quando os [usuários criam ou editam um grupo](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx)no Outlook, você pode mostrar a eles um link para as diretrizes de uso da sua organização. Por exemplo, se você precisar que um prefixo ou sufixo específico seja adicionado a um nome de grupo.

Use o PowerShell do Azure Active Directory (Azure AD) para apontar os usuários para as diretrizes de uso da sua organização para grupos do Microsoft 365. Confira os [cmdlets do Azure Active Directory](https://go.microsoft.com/fwlink/?LinkID=827484) para definir  as configurações de grupo e siga as etapas nas configurações Criar no nível de diretório para definir o hiperlink de diretriz de uso. Depois de executar o cmdlet do AAD, os usuários verão o link para suas diretrizes quando criarem ou editarem um grupo no Outlook.

![Criar um novo grupo com o link de diretrizes de uso](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![Clique em Diretrizes de uso do grupo para ver as diretrizes de grupos do Office 365 de suas organizações](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a>Permitir que os usuários enviem como o grupo do Microsoft 365
<a name="BK_LinkToGuideLines"> </a>

Se você quiser habilitar seus grupos do Microsoft 365 para "Enviar como", use os cmdlets [Add-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/add-recipientpermission) e [Get-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/get-recipientpermission) para configurar isso. Depois de habilitar essa configuração, os usuários do grupo do Microsoft 365 podem usar o Outlook ou o Outlook na Web para enviar e responder a emails como o grupo do Microsoft 365. Os usuários podem ir para o grupo, criar um novo email e alterar o campo "Enviar como" para o endereço de email do grupo.

([Você também pode fazer isso no Centro de Administração do Exchange.)](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group)

Use o script a seguir, substituindo pelo alias do grupo que você deseja atualizar e pelo alias do usuário para o qual você *\<GroupAlias\>* *\<UserAlias\>* deseja conceder permissões. [Conecte-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) para executar esse script.

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

Depois que o cmdlet é executado, os usuários podem ir para o Outlook ou o Outlook na Web para enviar como o grupo, adicionando o endereço de email do grupo ao **campo** De.

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a>Criar classificações para Grupos do Microsoft 365 em sua organização

Você pode criar rótulos de sensibilidade que os usuários em sua organização podem definir ao criar um Grupo do Microsoft 365. Se você quiser classificar grupos, recomendamos usar rótulos de sensibilidade em vez do recurso de classificação de grupos anteriores. Para saber mais sobre como usar rótulos de sensibilidade, confira Usar rótulos de sensibilidade para proteger o conteúdo no Microsoft Teams, grupos do [Microsoft 365 e sites do SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

> [!IMPORTANT]
> Se você estiver usando rótulos de classificação no momento, eles não estarão mais disponíveis para usuários que criam grupos depois que os rótulos de sensibilidade são habilitados.

Você ainda pode usar o recurso de classificação de grupos anterior. Você pode criar classificações que os usuários em sua organização podem definir ao criar um Grupo do Microsoft 365. Por exemplo, você pode permitir que os usuários de definir "Padrão", "Segredo" e "Segredo Superior" em grupos que eles criam. As classificações de grupo não são definidas por padrão e você precisa criar para que seus usuários as deem. Use o PowerShell do Azure Active Directory para apontar seus usuários para as diretrizes de uso da sua organização para Grupos do Microsoft 365.

Confira os [cmdlets do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets) para definir  as configurações de grupo e siga as etapas nas configurações Criar no nível de diretório para definir a classificação dos Grupos do Microsoft 365.

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

Para associar uma descrição a cada classificação, você pode usar o atributo  *ClassificationDescriptions de configurações* para definir.

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

onde Classificação corresponde às cadeias de caracteres na ClassificationList.

Exemplo:

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

Depois de executar o cmdlet acima do Azure Active Directory para definir sua classificação, execute o cmdlet [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) se quiser definir a classificação para um grupo específico.

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

Ou crie um novo grupo com uma classificação.

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

Confira o [uso do PowerShell com o Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) e conecte-se ao [PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) do Exchange Online para obter mais detalhes sobre como usar o PowerShell do Exchange Online.

Depois que essas configurações são habilitadas, o proprietário do grupo poderá escolher uma classificação no menu  suspenso no Outlook na Web e no Outlook e salvá-la na página Editar grupo.

![Escolha a classificação de grupo do Microsoft 365](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a>Ocultar grupos do Microsoft 365 da lista de endereços global.
<a name="BKMK_CreateClassification"> </a>

Você pode especificar se um Grupo do Microsoft 365 aparece na GAL (lista de endereços global) e em outras listas em sua organização. Por exemplo, se você tiver um grupo de departamento jurídico que não deseja exibir na lista de endereços, poderá impedir que esse grupo apareça na GAL. Execute o cmdlet Set-Unified Group para ocultar o grupo da lista de endereços da forma a seguir:

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a>Permitir que apenas usuários internos enviem mensagens aos Grupos do Microsoft 365
<a name="BKMK_CreateClassification"> </a>

Se não quiser que os usuários de outras organizações enviem emails para um grupo do Microsoft 365, você pode alterar as configurações para esse grupo. Ele permitirá que apenas usuários internos enviem um email para o seu grupo. Se um usuário externo tentar enviar uma mensagem para esse grupo, ela será rejeitada.

Execute o Set-UnifiedGroup cmdlet para atualizar essa configuração, desta forma:

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a>Adicionar Dicas de Email aos Grupos do Microsoft 365
<a name="BKMK_CreateClassification"> </a>

Sempre que um remetente tentar enviar um email para um grupo do Microsoft 365, uma Dica de Email poderá ser mostrada a ele.

Execute o cmdlet Set-Unified Group para adicionar uma dica de email ao grupo:

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

Além de MailTip, você também pode definir MailTipTranslations, que especifica idiomas adicionais para a Dica de Email. Suponha que você queira ter a tradução em espanhol e execute o seguinte comando:

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a>Alterar o nome de exibição do Grupo do Microsoft 365

O nome de exibição especifica o nome do Grupo do Microsoft 365. Você pode ver esse nome no centro de administração do Exchange ou no Centro de administração do Microsoft 365. Você pode editar o nome de exibição do grupo ou atribuir um nome de exibição a um grupo existente do Microsoft 365 executando o Set-UnifiedGroup comando:

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a>Alterar a configuração padrão dos Grupos do Microsoft 365 para Outlook para Público ou Privado
<a name="BKMK_CreateClassification"> </a>

Os Grupos do Microsoft 365 no Outlook são criados como Particulares por padrão. Se sua organização deseja que os Grupos do Microsoft 365 sejam criados como Públicos por padrão (ou de volta para Privado), use esta sintaxe de cmdlet do PowerShell:

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

Para definir como Private:

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

Para verificar a configuração:

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

Para saber mais, consulte [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) e [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig).

## <a name="microsoft-365-groups-cmdlets"></a>Cmdlets de grupos do Microsoft 365

Os cmdlets a seguir podem ser usados com grupos do Microsoft 365.

|**Nome do cmdlet**|**Descrição**|
|:-----|:-----|
|[Get-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616182) <br/> |Use este cmdlet para procurar grupos existentes do Microsoft 365 e para exibir as propriedades do objeto de grupo  <br/> |
|[Set-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616189) <br/> |Atualizar as propriedades de um grupo específico do Microsoft 365  <br/> |
|[New-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616183) <br/> |Crie um novo Grupo do Microsoft 365. Este cmdlet fornece um conjunto mínimo de parâmetros. Para definir valores para propriedades estendidas, use Set-UnifiedGroup depois de criar o novo grupo  <br/> |
|[Remove-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616186) <br/> |Excluir um grupo existente do Microsoft 365  <br/> |
|[Get-UnifiedGroupLinks](https://go.microsoft.com/fwlink/p/?LinkId=616194) <br/> |Recuperar informações de associação e proprietário de um grupo do Microsoft 365  <br/> |
|[Add-UnifiedGroupLinks](https://go.microsoft.com/fwlink/p/?LinkId=616191) <br/> |Adicionar membros, proprietários e assinantes a um grupo existente do Microsoft 365 <br/> |
|[Remove-UnifiedGroupLinks](https://go.microsoft.com/fwlink/p/?LinkId=616195) <br/> |Remover proprietários e membros de um grupo existente do Microsoft 365  <br/> |
|[Get-UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536510) <br/> |Usado para exibir informações sobre a foto do usuário associada a uma conta. As fotos do usuário são armazenadas no Active Directory  <br/> |
|[Set-UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536511) <br/> |Usado para associar uma foto de usuário a uma conta. As fotos do usuário são armazenadas no Active Directory  <br/> |
|[Remove-UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536512) <br/> |Remover a foto de um grupo do Microsoft 365  <br/> |

## <a name="related-topics"></a>Tópicos relacionados

[Atualizar listas de distribuição para Grupos do Microsoft 365](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)

[Gerenciar quem pode criar Grupos do Microsoft 365](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)

[Gerenciar o acesso de convidados aos Grupos do Microsoft 365](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Alterar a associação de grupo estático para dinâmica em](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)
