---
title: Bloquear usuários convidados de um grupo específico
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
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Bloquear usuários convidados de um grupo específico
ms.openlocfilehash: 2e9c9cae13932a33b8c486148f93901904e80006
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328012"
---
# <a name="block-guest-users-from-a-specific-microsoft-365-group-or-microsoft-teams-team"></a>Bloquear usuários convidados de um grupo específico do Microsoft 365 ou uma equipe do Microsoft Teams

Se você quiser permitir o acesso de convidados à maioria dos grupos e equipes, mas tiver algumas situações em que você deseja impedir o acesso de convidados, é possível bloquear o acesso de convidados para grupos e equipes individuais. (Bloquear o acesso de convidados a uma equipe é feito bloqueando o acesso de convidados ao grupo associado.)

Se você usar rótulos de confidencialidade em sua organização, recomendamos usá-los para controlar o acesso de convidados por grupo. Para obter informações sobre como fazer isso, [use rótulos de confidencialidade para proteger o conteúdo no Microsoft Teams, microsoft 365 Groups e sites do SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites). Esta é a abordagem recomendada.

Você também pode bloquear o acesso de convidados a grupos individuais usando o Microsoft PowerShell.

Você deve usar a versão de visualização do [PowerShell do Azure Active Directory para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (nome do módulo **AzureADPreview**) para alterar a configuração de acesso de convidados em nível de Grupo:

- Caso ainda não tenha instalado uma versão do módulo Azure AD PowerShell antes, confira [instalando o módulo Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) e siga as instruções para instalar a versão de visualização pública.

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

Você pode permitir ou bloquear usuários convidados que usam um domínio específico. Por exemplo, se sua empresa (contoso) tem uma parceria com outra empresa (Fabrikam), você pode adicionar a Fabrikam à sua lista de permissões para que os usuários possam adicionar esses convidados aos seus grupos.

Para obter mais informações, consulte [permitir ou bloquear convites para usuários B2B de organizações específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).

## <a name="add-guests-to-the-global-address-list"></a>Adicionar convidados à lista de endereços global

Por padrão, os convidados não estão visíveis na lista de endereços global do Exchange. Use as etapas listadas abaixo para tornar um convidado visível na lista de endereços global.

Encontre o ObjectID do usuário convidado executando:

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

Em seguida, execute o seguinte usando os valores apropriados para ObjectID, excertoname, sobrenome, DisplayName e TelephoneNumber.

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a>Artigos relacionados

[Gerenciar a associação de grupo no centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)
  
[Revisões do acesso ao Active Directory do Azure](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)