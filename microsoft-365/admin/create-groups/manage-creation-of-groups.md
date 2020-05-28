---
title: Gerenciar quem pode criar grupos
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MSP160
- MST160
- MET150
- MOE150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Saiba como controlar quais usuários podem criar grupos do Microsoft 365.
ms.openlocfilehash: f3de4ac0856f1281151e6d1c686d90559a5e8544
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387988"
---
# <a name="manage-who-can-create-groups"></a>Gerenciar quem pode criar grupos

  
Como é muito fácil para os usuários criarem grupos do Microsoft 365, você não é inundado com solicitações para criá-los em nome de outras pessoas. Dependendo da sua empresa, no entanto, talvez você queira controlar quem tem a capacidade de criar grupos.
  
Este artigo explica como desabilitar a capacidade de criar grupos em todos os serviços do Microsoft 365 que usam grupos, incluindo:
  
- Outlook
    
- SharePoint
    
- Yammer
    
- Microsoft Teams

- Microsoft Stream
    
- StaffHub
    
- Planner
    
- PowerBI

- Roteiro
    
Você pode restringir a criação de grupos do Microsoft 365 aos membros de um determinado grupo de segurança. Para configurar isso, use o Windows PowerShell. Este artigo orienta você pelas etapas necessárias.
  
As etapas neste artigo não impedem que os membros de determinadas funções criem grupos. Os administradores globais podem criar grupos por meio de qualquer meio, como o centro de administração do 365, o Planner, o Microsoft Teams, o Exchange e o SharePoint Online. Outras funções podem criar grupos por meio limitado, listados abaixo.
        
  - Administrador do Exchange: centro de administração do Exchange, Azure AD
    
  - Suporte à camada 1 do parceiro: centro de administração do Microsoft 365, centro de administração do Exchange, Azure AD
    
  - Suporte à camada 2 do parceiro: centro de administração do Microsoft 365, centro de administração do Exchange, Azure AD
    
  - Gravadores de diretório: Azure AD

  - Administrador do SharePoint: centro de administração do SharePoint, Azure AD
  
  - Administrador do teams Service: centro de administração do Microsoft Teams, Azure AD
  
  - Administrador de gerenciamento de usuários: centro de administração do Microsoft 365, Yammer, Azure AD
     
Se você for um membro de uma dessas funções, poderá criar grupos do Microsoft 365 para usuários restritos e atribuir o usuário como o proprietário do grupo. Os usuários que possuem essa função podem criar grupos conectados no Yammer, independentemente de qualquer configuração do PowerShell que possa impedir a criação.

## <a name="licensing-requirements"></a>Requisitos de licença

Para gerenciar quem cria grupos, as seguintes pessoas precisam de licenças do Azure AD Premium ou licenças do Azure AD Basic EDU atribuídas a eles:

- O administrador que configura essas definições de criação de grupos
- Os membros do grupo de segurança que têm permissão para criar grupos

> [!NOTE]
> Consulte [atribuir ou remover licenças no portal do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) para obter mais detalhes sobre como atribuir licenças do Azure.

As seguintes pessoas não precisam de licenças do Azure AD Premium ou do Azure AD Basic EDU atribuídas:

- Pessoas que são membros de grupos do Microsoft 365 e que não têm a capacidade de criar outros grupos.

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a>Etapa 1: criar um grupo de segurança para os usuários que precisam criar grupos do Microsoft 365

Somente um grupo de segurança em sua organização pode ser usado para controlar quem é capaz de criar grupos. Mas você pode aninhar outros grupos de segurança como membros deste grupo. Por exemplo, o grupo chamado Permitir a criação de grupo é o grupo de segurança designado e os grupos chamados Usuários do Microsoft Planner e Usuários do Exchange Online são membros daquele grupo.

Os administradores nas funções listadas acima não precisam ser membros desse grupo: Eles retêm a capacidade de criar grupos.

> [!IMPORTANT]
> Certifique-se de usar um **grupo de segurança** para restringir quem pode criar grupos. Se você tentar usar um grupo do Microsoft 365, os membros não poderão criar um grupo do SharePoint, pois ele verifica se há um grupo de segurança. 
    
1. No centro de administração, vá para a página grupos de **grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> .

2. Clique em **Adicionar um grupo**.

3. Escolha **segurança** como o tipo de grupo. Lembre-se do nome do grupo! Você precisará disso posteriormente.
  
4. Conclua a configuração do grupo de segurança, adicionando pessoas ou outros grupos de segurança que você deseja poder criar grupos na sua organização.
    
Para obter instruções detalhadas, consulte [criar, editar ou excluir um grupo de segurança no centro de administração do Microsoft 365](../email/create-edit-or-delete-a-security-group.md).
 
## <a name="step-2-run-powershell-commands"></a>Etapa 2: Executar comandos do PowerShell

Você deve usar a versão de visualização do [PowerShell do Azure Active Directory para Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (nome do módulo **AzureADPreview**) para alterar a configuração de acesso de convidados em nível de Grupo:

- Caso ainda não tenha instalado uma versão do módulo Azure AD PowerShell antes, confira [instalando o módulo Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) e siga as instruções para instalar a versão de visualização pública.

- Se você tiver a versão de disponibilidade geral 2.0 do módulo do Azure AD PowerShell (AzureAD) instalada, desinstale-a executando `Uninstall-Module AzureAD` em sua sessão do PowerShell e instale a versão de visualização executando `Install-Module AzureADPreview`.

- Se você já tiver instalado a versão de visualização, execute `Install-Module AzureADPreview` para ter certeza de que esta é a versão mais recente deste módulo.



Copie o script abaixo para um editor de texto, como o bloco de notas, ou o [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).

Substitua *\<SecurityGroupName\>* pelo nome do grupo de segurança que você criou. Por exemplo:

`$GroupName = "Group Creators"`

Salve o arquivo como GroupCreators. ps1. 

Na janela do PowerShell, navegue até o local onde você salvou o arquivo (digite "CD <FileLocation> ").

Execute o script digitando:

`.\GroupCreators.ps1`

e [entre com sua conta de administrador](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) quando solicitado.

```PowerShell
$GroupName = "<SecurityGroupName>"
$AllowGroupCreation = "False"

Connect-AzureAD

$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
if(!$settingsObjectID)
{
      $template = Get-AzureADDirectorySettingTemplate | Where-object {$_.displayname -eq "group.unified"}
    $settingsCopy = $template.CreateDirectorySetting()
    New-AzureADDirectorySetting -DirectorySetting $settingsCopy
    $settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
}

$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID
$settingsCopy["EnableGroupCreation"] = $AllowGroupCreation

if($GroupName)
{
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -Filter "DisplayName eq '$GroupName'").objectId
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

A última linha do script exibirá as configurações atualizadas:

![This is what your settings will look like when you're done.](../../media/952cd982-5139-4080-9add-24bafca0830c.png)

Se no futuro você quiser alterar o grupo de segurança usado, poderá executar novamente o script com o nome do novo grupo de segurança.

Se você deseja desativar a restrição de criação de grupo e novamente permitir que todos os usuários criem grupos, defina $GroupName como "" e $AllowGroupCreation como "true" e execute novamente o script.
    
## <a name="step-4-verify-that-it-works"></a>Etapa 4: verificar se funciona

As alterações podem levar trinta minutos ou mais para entrar em vigor. Você pode verificar as novas configurações fazendo o seguinte:

1. Entre com uma conta de usuário de alguém que não deve ter a capacidade de criar grupos. Ou seja, eles não são membros do grupo de segurança que você criou ou de um administrador.
    
2. Selecione o bloco do **Planner** . 
    
3. No Planner, selecione **novo plano** no painel de navegação à esquerda para criar um plano. 
  
4. Você deve obter uma mensagem informando que o plano e a criação de grupos estão desabilitados.

Tente o mesmo procedimento novamente com um membro do grupo de segurança.

> [!NOTE]
> Se os membros do grupo de segurança não puderem criar grupos, verifique se eles não estão sendo bloqueados por meio da [política de caixa de correio do OWA](https://go.microsoft.com/fwlink/?linkid=852135).
    
## <a name="related-articles"></a>Artigos relacionados

[Introdução ao Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[Configurar o gerenciamento de grupo de autoatendimento no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[Cmdlets do Azure Active Directory para definição de configurações de grupo](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
