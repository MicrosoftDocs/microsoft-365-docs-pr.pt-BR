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
description: Saiba como impedir que os convidados são adicionados a um grupo específico
ms.openlocfilehash: 572746a666586920ad85dafddbd78997940490d7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907935"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a>Impedir que os convidados seja adicionado a um grupo específico do Microsoft 365 ou à equipe do Microsoft Teams

Se você deseja permitir o acesso de convidados à maioria dos grupos e equipes, mas tem alguns onde deseja impedir o acesso de convidados, você pode bloquear o acesso de convidados para grupos e equipes individuais. (O bloqueio do acesso de convidados a uma equipe é feito bloqueando o acesso de convidados ao grupo associado.) Isso impede que novos convidados sejam adicionados, mas não remove os convidados que já estão no grupo ou na equipe.

Se você usar rótulos de sensibilidade em sua organização, recomendamos usá-los para controlar o acesso de convidados por grupo. Para obter informações sobre como fazer isso, use rótulos de sensibilidade para proteger o conteúdo no Microsoft Teams, nos grupos do [Microsoft 365 e nos sites do SharePoint.](../compliance/sensitivity-labels-teams-groups-sites.md) Esta é a abordagem recomendada.

## <a name="change-group-settings-using-microsoft-powershell"></a>Alterar configurações de grupo usando o Microsoft PowerShell

Você também pode impedir a adição de novos convidados a grupos individuais usando o PowerShell. (Lembre-se de que o site do SharePoint associado da equipe tem controles de compartilhamento de [convidados separados](/sharepoint/change-external-sharing-site).)

Você deve usar a versão de visualização do [Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2) (nome do módulo **AzureADPreview**) para alterar a configuração de acesso de convidado no nível de grupo:

- Caso ainda não tenha instalado uma versão do módulo Azure AD PowerShell antes, confira [instalando o módulo Azure AD](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) e siga as instruções para instalar a versão de visualização pública.

- Se você tiver a versão de disponibilidade geral 2.0 do módulo do Azure AD PowerShell (AzureAD) instalada, desinstale-a executando `Uninstall-Module AzureAD` em sua sessão do PowerShell e instale a versão de visualização executando `Install-Module AzureADPreview`.

- Se você já tiver instalado a versão de visualização, execute `Install-Module AzureADPreview` para ter certeza de que esta é a versão mais recente deste módulo.

> [!NOTE]
> Você deve ter direitos de administrador global para executar esses comandos. 

Execute o script a seguir, alterando para o nome do */<GroupName/>* grupo onde você deseja bloquear o acesso de convidados.

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
    
![Captura de tela da janela do PowerShell mostrando que o acesso ao grupo de convidados foi definido como false.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a>Permitir ou bloquear o acesso de convidados com base em seu domínio

Você pode permitir ou bloquear convidados que estão usando um domínio específico. Por exemplo, se sua empresa (Contoso) tiver uma parceria com outra empresa (Fabrikam), você poderá adicionar Fabrikam à sua lista Permitir para que os usuários possam adicionar esses convidados aos seus grupos.

Para obter mais informações, consulte [Permitir ou bloquear convites para usuários B2B de organizações específicas.](/azure/active-directory/b2b/allow-deny-list)

## <a name="add-guests-to-the-global-address-list"></a>Adicionar convidados à lista de endereços global

Por padrão, os convidados não estão visíveis na Lista de Endereços Globais do Exchange. Use as etapas listadas abaixo para tornar um convidado visível na lista de endereços global.

Encontre ObjectID do convidado executando:

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

[Gerenciar associação ao grupo no centro de administração do Microsoft 365](../admin/create-groups/add-or-remove-members-from-groups.md)
  
[Avaliações de acesso do Azure Active Directory](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](/powershell/module/azuread/set-azureaduser)