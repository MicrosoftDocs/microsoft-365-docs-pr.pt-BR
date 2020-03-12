---
title: Gerenciar o acesso de convidados nos grupos do Office 365
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.date: 12/18/2019
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Saiba como adicionar convidados a um grupo do Office 365, exibir usuários convidados e usar o PowerShell para controlar o acesso de convidados.
ms.openlocfilehash: e4d71919fa5ebfb97a6bab8013fc6bc54ac071a4
ms.sourcegitcommit: 21338a9287017a66298e0ff557e80051946ebf13
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2020
ms.locfileid: "42603998"
---
# <a name="manage-guest-access-in-office-365-groups"></a>Gerenciar o acesso de convidados nos grupos do Office 365

Por padrão, o acesso de convidados para grupos do Office 365 está ativado para sua organização. Os administradores podem controlar a possibilidade de permitir o acesso de convidados a grupos para toda a sua organização ou para grupos individuais.

Quando ele está ativado, os membros do grupo podem convidar usuários convidados para um grupo do Office 365 por meio do Outlook na Web. Os convites são enviados ao proprietário do grupo para aprovação.

> [!Note]
> As redes corporativas do Yammer que estão no modo nativo ou na [Geografia da UE](https://go.microsoft.com/fwlink/?linkid=2107357) não dão suporte a convidados de rede.
> Os grupos do Yammer conectados ao Office 365 atualmente não dão suporte ao acesso de convidados, mas você pode criar grupos externos não conectados na sua rede do Yammer. Veja [criar e gerenciar grupos externos no Yammer](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a.aspx) para obter instruções.

### <a name="edit-guest-information"></a>Editar informações de convidados

Depois de aprovado, o usuário convidado é adicionado ao diretório e ao grupo.

O acesso de convidados em grupos é geralmente usado como parte de um cenário mais amplo que inclui o SharePoint ou o Teams. Esses serviços têm suas próprias configurações de compartilhamento de convidados. Para obter instruções completas sobre como configurar o compartilhamento de convidados entre grupos, SharePoint e equipes, consulte:

- [Colaborar com convidados em um site](https://docs.microsoft.com/Office365/Enterprise/collaborate-in-site)
- [Colaborar com convidados em uma equipe](https://docs.microsoft.com/Office365/Enterprise/collaborate-as-team)

## <a name="manage-groups-guest-access"></a>Gerenciar o acesso de convidados a grupos

Se quiser habilitar ou desabilitar o acesso de convidados em grupos, você pode fazer isso no centro de administração do Microsoft 365.

1. No centro de administração, vá para a página **configurações** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">&</a> de suplementos.

2. Selecione **grupos do Office 365**.
  
3. Na página **grupos do Office 365** , escolha se você deseja permitir que pessoas de fora da sua organização acessem os recursos do grupo ou permitir que os proprietários de grupos adicionem pessoas de fora da sua organização a grupos.

## <a name="add-guests-to-an-office-365-group-from-the-admin-center"></a>Adicionar convidados a um grupo do Office 365 a partir do centro de administração

Se o convidado já existir no seu diretório, você poderá adicioná-lo aos seus grupos no centro de administração do Microsoft 365.
  
1. No centro de administração, vá para**a página grupos** de **grupos** > .
  
2. Selecione o grupo ao qual você deseja adicionar o convidado e selecione **Exibir todos e gerenciar Membros** na guia **Membros** . 
  
4. Selecione **adicionar membros**e escolha o nome do convidado que você deseja adicionar.
    
5. Selecione **Salvar**.

Se quiser adicionar um convidado ao diretório diretamente, você poderá [Adicionar usuários de colaboração B2B do Azure Active Directory no portal do Azure](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).

Se quiser editar as informações de um convidado, você poderá [Adicionar ou atualizar as informações de perfil de um usuário usando o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).
  
## <a name="block-guest-users-from-a-specific-group"></a>Bloquear usuários convidados de um grupo específico

Se você quiser permitir o acesso de convidados à maioria dos grupos, mas tiver algumas situações em que você deseja impedir o acesso de convidados, poderá bloquear o acesso de convidados para grupos individuais usando o Microsoft PowerShell.

Você deve usar a versão de visualização do [PowerShell do Azure Active Directory para Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (nome do módulo **AzureADPreview**) para alterar a configuração de acesso de convidados em nível de Grupo:

- Caso ainda não tenha instalado uma versão do módulo Azure AD PowerShell antes, confira [instalando o módulo Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) e siga as instruções para instalar a versão de visualização pública.

- Se você tiver a versão de disponibilidade geral 2.0 do módulo do Azure AD PowerShell (AzureAD) instalada, desinstale-a executando `Uninstall-Module AzureAD` em sua sessão do PowerShell e instale a versão de visualização executando `Install-Module AzureADPreview`.

- Se você já tiver instalado a versão de visualização, execute `Install-Module AzureADPreview` para ter certeza de que esta é a versão mais recente deste módulo.

> [!NOTE]
> Você deve ter direitos de administrador global para executar esses comandos. 

Execute o script a seguir, * / * mudando para o nome do grupo onde você deseja bloquear o acesso de convidados.

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
    
![Captura de tela da janela do PowerShell mostrando que o acesso ao grupo de convidados foi definido como false.](../../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
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

[Gerenciar a associação de grupo no centro de administração do Microsoft 365](add-or-remove-members-from-groups.md)
  
[Revisões do acesso ao Active Directory do Azure](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
