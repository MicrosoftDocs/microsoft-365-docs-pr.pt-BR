---
title: Impedir que convidados são adicionados a um grupo específico
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Saiba como impedir que convidados são adicionados a um grupo específico
ms.openlocfilehash: 8bee26bf5ec323536ca1ac6f25ce96927634cee7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49660043"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a>Impedir que convidados são adicionados a um grupo específico do Microsoft 365 ou equipe do Microsoft Teams

Se você deseja permitir o acesso de convidados à maioria dos grupos e equipes, mas tem algumas onde deseja impedir o acesso de convidados, você pode bloquear o acesso de convidados para grupos e equipes individuais. (Bloquear o acesso de convidados a uma equipe é feito bloqueando o acesso de convidados ao grupo associado.) Isso impede que novos convidados sejam adicionados, mas não remove convidados que já estão no grupo ou na equipe.

Se você usa rótulos de sensibilidade em sua organização, recomendamos usá-los para controlar o acesso de convidados por grupo. Para obter informações sobre como fazer isso, use rótulos de sensibilidade para proteger o conteúdo no Microsoft Teams, grupos do [Microsoft 365 e sites do SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) Esta é a abordagem recomendada.

## <a name="change-group-settings-using-microsoft-powershell"></a>Alterar configurações de grupo usando o Microsoft PowerShell

Você também pode impedir a adição de novos convidados a grupos individuais usando o PowerShell. (Lembre-se de que o site do SharePoint associado da equipe tem controles de compartilhamento [de convidados separados.)](https://docs.microsoft.com/sharepoint/change-external-sharing-site)

Você deve usar a versão de visualização do PowerShell do [Azure Active Directory](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) para Graph (nome do módulo **AzureADPreview**) para alterar a configuração de acesso de convidado em nível de grupo:

- Caso ainda não tenha instalado uma versão do módulo Azure AD PowerShell antes, confira [instalando o módulo Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) e siga as instruções para instalar a versão de visualização pública.

- Se você tiver a versão de disponibilidade geral 2.0 do módulo do Azure AD PowerShell (AzureAD) instalada, desinstale-a executando `Uninstall-Module AzureAD` em sua sessão do PowerShell e instale a versão de visualização executando `Install-Module AzureADPreview`.

- Se você já tiver instalado a versão de visualização, execute `Install-Module AzureADPreview` para ter certeza de que esta é a versão mais recente deste módulo.

> [!NOTE]
> Você deve ter direitos de administrador global para executar esses comandos. 

Execute o script a seguir, */<GroupName/>* alterando para o nome do grupo no qual você deseja bloquear o acesso de convidados.

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

Para verificar suas configurações, execute este comando:

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

A verificação tem esta aparência:
    
![Captura de tela da janela do PowerShell mostrando que o acesso ao grupo de convidados foi definido como falso.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a>Permitir ou bloquear o acesso de convidados com base em seu domínio

Você pode permitir ou bloquear convidados que estão usando um domínio específico. Por exemplo, se sua empresa (Contoso) tem uma parceria com outra empresa (Fabrikam), você pode adicionar Fabrikam à sua lista de Permitir para que os usuários possam adicionar esses convidados aos grupos.

Para obter mais informações, [consulte Permitir ou bloquear convites para usuários B2B de organizações específicas.](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)

## <a name="add-guests-to-the-global-address-list"></a>Adicionar convidados à lista de endereços global

Por padrão, os convidados não estão visíveis na Lista de Endereços Global do Exchange. Use as etapas listadas abaixo para tornar um convidado visível na lista de endereços global.

Encontre o ObjectID do convidado executando:

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

Em seguida, execute o seguinte usando os valores apropriados para ObjectID, GivenName, Surname, DisplayName e TelephoneNumber.

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a>Tópicos relacionados

[Planejamento de governança de colaboração passo a passo](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Criar seu plano de governança de colaboração](collaboration-governance-first.md)

[Gerenciar a associação de grupo no centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)
  
[Revisões de acesso do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
