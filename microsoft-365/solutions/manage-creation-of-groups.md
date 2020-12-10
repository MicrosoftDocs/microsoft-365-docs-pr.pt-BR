---
title: Gerenciar quem pode criar grupos do Microsoft 365
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Saiba como controlar quais usuários podem criar grupos do Microsoft 365.
ms.openlocfilehash: 2954f68dce289d43b37bf8f5c6ff43fe1b5c48c7
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613555"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a>Gerenciar quem pode criar grupos do Microsoft 365

Por padrão, todos os usuários podem criar grupos do Microsoft 365. Essa é a abordagem recomendada porque permite que os usuários comecem a colaborar sem precisar de assistência.

Se sua empresa requer que você restrinja quem pode criar grupos, faça isso seguindo os procedimentos deste artigo. Quando você limita quem pode criar um grupo, ele afeta todos os serviços que dependem de grupos para acesso, incluindo:

- Outlook
- SharePoint
- Yammer
- Microsoft Teams
- Microsoft Stream
- Planner
- Power BI (clássico)
- Projeto para a Web/mapa

Você pode restringir a criação de grupos do Microsoft 365 aos membros de um determinado grupo de segurança. Para configurar isso, use o Windows PowerShell. Este artigo orienta você pelas etapas necessárias.

As etapas neste artigo não impedem que os membros de determinadas funções criem grupos. Os administradores globais do Office 365 podem criar grupos por meio de qualquer meio, como o centro de administração do Microsoft 365, o Planner, o Teams, o Exchange e o SharePoint Online. Outras funções podem criar grupos por meio limitado, listados abaixo.

- Administrador do Exchange: centro de administração do Exchange, Azure AD
- Suporte à camada 1 do parceiro: centro de administração do Microsoft 365, centro de administração do Exchange, Azure AD
- Suporte à camada 2 do parceiro: centro de administração do Microsoft 365, centro de administração do Exchange, Azure AD
- Gravadores de diretório: Azure AD
- Administrador do SharePoint: centro de administração do SharePoint, Azure AD
- Administrador do teams Service: centro de administração do Microsoft Teams, Azure AD
- Administrador de gerenciamento de usuários: centro de administração do Microsoft 365, Yammer, Azure AD

Se você for um membro de uma dessas funções, poderá criar grupos do Microsoft 365 para usuários restritos e atribuir o usuário como o proprietário do grupo.

## <a name="licensing-requirements"></a>Requisitos de licença

Para gerenciar quem cria grupos, as seguintes pessoas precisam de licenças do Azure AD Premium ou licenças do Azure AD Basic EDU atribuídas a eles:

- O administrador que configura essas definições de criação de grupos
- Os membros do grupo de segurança que têm permissão para criar grupos

> [!NOTE]
> Consulte [atribuir ou remover licenças no portal do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) para obter mais detalhes sobre como atribuir licenças do Azure.

As seguintes pessoas não precisam de licenças do Azure AD Premium ou do Azure AD Basic EDU atribuídas:

- Pessoas que são membros de grupos do Microsoft 365 e que não têm a capacidade de criar outros grupos.

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a>Etapa 1: criar um grupo de segurança para os usuários que precisam criar grupos do Microsoft 365

Somente um grupo de segurança em sua organização pode ser usado para controlar quem é capaz de criar grupos. Mas você pode aninhar outros grupos de segurança como membros deste grupo.

Os administradores nas funções listadas acima não precisam ser membros desse grupo: Eles retêm a capacidade de criar grupos.

> [!IMPORTANT]
> Certifique-se de usar um **grupo de segurança** para restringir quem pode criar grupos. Não há suporte para o uso de um grupo do Microsoft 365.

1. No centro de administração, vá para a [página grupos](https://admin.microsoft.com/adminportal/home#/groups).

2. Clique em **Adicionar um grupo**.

3. Escolha **segurança** como o tipo de grupo. Lembre-se do nome do grupo! Você precisará disso posteriormente.

4. Conclua a configuração do grupo de segurança, adicionando pessoas ou outros grupos de segurança que você deseja poder criar grupos na sua organização.

Para obter instruções detalhadas, consulte [criar, editar ou excluir um grupo de segurança no centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group).

## <a name="step-2-run-powershell-commands"></a>Etapa 2: Executar comandos do PowerShell

Você deve usar a versão de visualização do [PowerShell do Azure Active Directory para Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (nome do módulo **AzureADPreview**) para alterar a configuração de acesso de convidados em nível de Grupo:

- Caso ainda não tenha instalado uma versão do módulo Azure AD PowerShell antes, confira [instalando o módulo Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) e siga as instruções para instalar a versão de visualização pública.

- Se você tiver a versão de disponibilidade geral 2.0 do módulo do Azure AD PowerShell (AzureAD) instalada, desinstale-a executando `Uninstall-Module AzureAD` em sua sessão do PowerShell e instale a versão de visualização executando `Install-Module AzureADPreview`.

- Se você já tiver instalado a versão de visualização, execute `Install-Module AzureADPreview` para ter certeza de que esta é a versão mais recente deste módulo.

Copie o script abaixo para um editor de texto, como o bloco de notas, ou o [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).

Substitua *\<SecurityGroupName\>* pelo nome do grupo de segurança que você criou. Por exemplo:

`$GroupName = "Group Creators"`

Salve o arquivo como GroupCreators.ps1.

Na janela do PowerShell, navegue até o local onde você salvou o arquivo (digite "CD <FileLocation> ").

Execute o script digitando:

`.\GroupCreators.ps1`

e [entre com sua conta de administrador](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) quando solicitado.

```PowerShell
$GroupName = "<SecurityGroupName>"
$AllowGroupCreation = $False

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
  $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString $GroupName).objectid
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

A última linha do script exibirá as configurações atualizadas:

![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

Se no futuro você quiser alterar o grupo de segurança usado, poderá executar novamente o script com o nome do novo grupo de segurança.

Se você deseja desativar a restrição de criação de grupo e novamente permitir que todos os usuários criem grupos, defina $GroupName como "" e $AllowGroupCreation como "true" e execute novamente o script.

## <a name="step-3-verify-that-it-works"></a>Etapa 3: Verifique se funciona

As alterações podem levar trinta minutos ou mais para entrar em vigor. Você pode verificar as novas configurações fazendo o seguinte:

1. Entre no Microsoft 365 com uma conta de usuário de alguém que não tenha a capacidade de criar grupos. Ou seja, eles não são membros do grupo de segurança que você criou ou de um administrador.

2. Selecione o bloco do **Planner** .

3. No Planner, selecione **novo plano** no painel de navegação à esquerda para criar um plano.

4. Você deve obter uma mensagem informando que o plano e a criação de grupos estão desabilitados.

Tente o mesmo procedimento novamente com um membro do grupo de segurança.

> [!NOTE]
> Se os membros do grupo de segurança não puderem criar grupos, verifique se eles não estão sendo bloqueados por meio da [política de caixa de correio do OWA](https://go.microsoft.com/fwlink/?linkid=852135).

## <a name="related-topics"></a>Tópicos relacionados

[Passo a passo de planejamento de governança de colaboração](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Criar seu plano de governança de colaboração](collaboration-governance-first.md)

[Introdução ao Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[Configurar o gerenciamento de grupo de autoatendimento no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[Cmdlets do Azure Active Directory para definição de configurações de grupo](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
