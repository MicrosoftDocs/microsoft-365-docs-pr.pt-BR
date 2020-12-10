---
title: Impedir que convidados sejam adicionados a um grupo específico
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
description: Saiba como impedir que convidados sejam adicionados a um grupo específico
ms.openlocfilehash: 99e78932b29d25054922b56fcadb608a7dfca432
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613051"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a>Impedir que convidados sejam adicionados a um grupo do Microsoft 365 específico ou a uma equipe do Microsoft Teams

Se você quiser permitir o acesso de convidados à maioria dos grupos e equipes, mas tiver algumas situações em que você deseja impedir o acesso de convidados, é possível bloquear o acesso de convidados para grupos e equipes individuais. (Bloquear o acesso de convidados a uma equipe é feito bloqueando o acesso de convidados ao grupo associado.) Isso impede que novos convidados sejam adicionados, mas não remove convidados que já estão no grupo ou na equipe.

Se você usar rótulos de confidencialidade em sua organização, recomendamos usá-los para controlar o acesso de convidados por grupo. Para obter informações sobre como fazer isso, [use rótulos de confidencialidade para proteger o conteúdo no Microsoft Teams, microsoft 365 Groups e sites do SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites). Esta é a abordagem recomendada.

## <a name="change-group-settings-using-microsoft-powershell"></a>Alterar as configurações de grupo usando o Microsoft PowerShell

Você também pode impedir a adição de novos convidados a grupos individuais usando o PowerShell.

Você deve usar a versão de visualização do [PowerShell do Azure Active Directory para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (nome do módulo **AzureADPreview**) para alterar a configuração de acesso de convidados em nível de Grupo:

- Caso ainda não tenha instalado uma versão do módulo Azure AD PowerShell antes, confira [instalando o módulo Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) e siga as instruções para instalar a versão de visualização pública.

- Se você tiver a versão de disponibilidade geral 2.0 do módulo do Azure AD PowerShell (AzureAD) instalada, desinstale-a executando `Uninstall-Module AzureAD` em sua sessão do PowerShell e instale a versão de visualização executando `Install-Module AzureADPreview`.

- Se você já tiver instalado a versão de visualização, execute `Install-Module AzureADPreview` para ter certeza de que esta é a versão mais recente deste módulo.

> [!NOTE]
> Você deve ter direitos de administrador global para executar esses comandos. 

Execute o script a seguir, mudando */<GroupName/>* para o nome do grupo onde você deseja bloquear o acesso de convidados.

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

A verificação tem a seguinte aparência:
    
![Captura de tela da janela do PowerShell mostrando que o acesso ao grupo de convidados foi definido como false.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a>Permitir ou bloquear o acesso de convidados com base em seu domínio

Você pode permitir ou bloquear convidados que estejam usando um domínio específico. Por exemplo, se sua empresa (contoso) tem uma parceria com outra empresa (Fabrikam), você pode adicionar a Fabrikam à sua lista de permissões para que os usuários possam adicionar esses convidados aos seus grupos.

Para obter mais informações, consulte [permitir ou bloquear convites para usuários B2B de organizações específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).

## <a name="add-guests-to-the-global-address-list"></a>Adicionar convidados à lista de endereços global

Por padrão, os convidados não estão visíveis na lista de endereços global do Exchange. Use as etapas listadas abaixo para tornar um convidado visível na lista de endereços global.

Encontre o ObjectID do convidado executando:

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

Em seguida, execute o seguinte usando os valores apropriados para ObjectID, excertoname, sobrenome, DisplayName e TelephoneNumber.

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a>Tópicos relacionados

[Passo a passo de planejamento de governança de colaboração](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Criar seu plano de governança de colaboração](collaboration-governance-first.md)

[Gerenciar a associação de grupo no centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)
  
[Revisões do acesso ao Active Directory do Azure](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
