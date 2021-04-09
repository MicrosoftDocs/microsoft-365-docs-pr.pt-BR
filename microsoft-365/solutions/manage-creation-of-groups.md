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
ms.openlocfilehash: 092ff821911ef0af2b7867e1b870b68b1b6355b3
ms.sourcegitcommit: dcc6bfd228ca9070975ce9eb14574e084f9ed92c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656980"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a>Gerenciar quem pode criar grupos do Microsoft 365

Por padrão, todos os usuários podem criar grupos do Microsoft 365. Essa é a abordagem recomendada porque permite que os usuários comecem a colaborar sem exigir assistência de TI.

Se sua empresa exigir que você restrinja quem pode criar grupos, você pode restringir a criação do Grupo do Microsoft 365 aos membros de um grupo ou grupo de segurança específico do Microsoft 365.

Se você estiver preocupado com os usuários que criam equipes ou grupos que não estão em conformidade com seus padrões de negócios, considere exigir que os usuários concluam um curso de treinamento e, em seguida, adicione-os ao grupo de usuários permitidos.

Quando você limita quem pode criar um grupo, ele afeta todos os serviços que dependem de grupos para acesso, incluindo:

- Outlook
- SharePoint
- Yammer
- Microsoft Teams
- Microsoft Stream
- Planner
- Power BI (clássico)
- Project for the Web /Roadmap

As etapas deste artigo não impedirão que membros de determinadas funções de criação de Grupos. Os administradores globais do Office 365 podem criar Grupos por meio do centro de administração do Microsoft 365, planner, Exchange e SharePoint Online. Outras funções podem criar Grupos por meios limitados, listados abaixo.

- Administrador do Exchange: Centro de administração do Exchange, Azure AD
- Suporte a Nível de Parceiro 1: Centro de administração do Microsoft 365, Centro de Administração do Exchange, Azure AD
- Suporte a Nível de Parceiro 2: Centro de administração do Microsoft 365, Centro de Administração do Exchange, Azure AD
- Redatores de diretório: Azure AD
- Administrador do SharePoint: Centro de administração do SharePoint, Azure AD
- Administrador de Serviços do Teams: Centro de administração do Teams, Azure AD
- Administrador do Usuário: Centro de administração do Microsoft 365, Azure AD

Se você for membro de uma dessas funções, poderá criar Grupos do Microsoft 365 para usuários restritos e atribuir o usuário como o proprietário do grupo.

## <a name="licensing-requirements"></a>Requisitos de licença

Para gerenciar quem cria grupos, as seguintes pessoas precisam de licenças do Azure AD Premium ou licenças do Azure AD Basic EDU atribuídas a eles:

- O administrador que configura essas configurações de criação de grupo
- Os membros do grupo que têm permissão para criar grupos

> [!NOTE]
> Confira Atribuir ou remover licenças no portal do [Azure Active Directory](/azure/active-directory/fundamentals/license-users-groups) para obter mais detalhes sobre como atribuir licenças do Azure.

As pessoas a seguir não precisam de licenças do Azure AD Premium ou do Azure AD Basic EDU atribuídas a elas:

- Pessoas que são membros de grupos do Microsoft 365 e que não têm a capacidade de criar outros grupos.

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a>Etapa 1: Criar um grupo para usuários que precisam criar grupos do Microsoft 365

Somente um grupo em sua organização pode ser usado para controlar quem é capaz de criar Grupos. Porém, você pode aninhar outros grupos como membros desse grupo.

Os administradores nas funções listadas acima não precisam ser membros desse grupo: eles retêm a capacidade de criar grupos.

1. No centro de administração, vá para a [página Grupos.](https://admin.microsoft.com/adminportal/home#/groups)

2. Clique em **Adicionar um Grupo**.

3. Escolha o tipo de grupo que você deseja. Lembre-se do nome do grupo! Você precisará disso posteriormente.

4. Termine de configurar o grupo, adicionando pessoas ou outros grupos que você deseja criar grupos em sua organização.

Para obter instruções detalhadas, consulte [Create, edit, or delete a security group in the Microsoft 365 admin center](../admin/email/create-edit-or-delete-a-security-group.md).

## <a name="step-2-run-powershell-commands"></a>Etapa 2: Executar comandos do PowerShell

Você deve usar a versão de visualização do [Azure Active Directory PowerShell para Graph (AzureAD) (nome](/powershell/azure/active-directory/install-adv2) do módulo **AzureADPreview**) para alterar a configuração de acesso de convidado no nível de grupo:

- Caso ainda não tenha instalado uma versão do módulo Azure AD PowerShell antes, confira [instalando o módulo Azure AD](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) e siga as instruções para instalar a versão de visualização pública.

- Se você tiver a versão de disponibilidade geral 2.0 do módulo do Azure AD PowerShell (AzureAD) instalada, desinstale-a executando `Uninstall-Module AzureAD` em sua sessão do PowerShell e instale a versão de visualização executando `Install-Module AzureADPreview`.

- Se você já tiver instalado a versão de visualização, execute `Install-Module AzureADPreview` para ter certeza de que esta é a versão mais recente deste módulo.

Copie o script abaixo para um editor de texto, como o Bloco de Notas ou o [Windows PowerShell ISE](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).

Substitua *\<GroupName\>* pelo nome do grupo que você criou. Por exemplo:

`$GroupName = "Group Creators"`

Salve o arquivo como GroupCreators.ps1.

Na janela do PowerShell, navegue até o local onde você salvou o arquivo (digite "CD <FileLocation> ").

Execute o script digitando:

`.\GroupCreators.ps1`

e [entre com sua conta de administrador quando](../enterprise/connect-to-microsoft-365-powershell.md#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) solicitado.

```PowerShell
$GroupName = "<GroupName>"
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

![Captura de tela da saída de script do PowerShell.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

Se no futuro você quiser alterar qual grupo é usado, você pode reprisar o script com o nome do novo grupo.

Se você quiser desativar a restrição de criação de grupo e permitir novamente que todos os usuários criem grupos, de definir $GroupName como "" e $AllowGroupCreation como "True" e repetir o script.

## <a name="step-3-verify-that-it-works"></a>Etapa 3: Verifique se funciona

As alterações podem levar trinta minutos ou mais para vigorar. Você pode verificar as novas configurações fazendo o seguinte:

1. Entre no Microsoft 365 com uma conta de usuário de alguém que NÃO deve ter a capacidade de criar grupos. Ou seja, eles não são um membro do grupo que você criou ou um administrador.

2. Selecione o **azulejo do Planner.**

3. No Planner, selecione **Novo Plano** na navegação à esquerda para criar um plano.

4. Você deve receber uma mensagem de que o plano e a criação de grupo estão desabilitados.

Tente o mesmo procedimento novamente com um membro do grupo.

> [!NOTE]
> Se os membros do grupo não são capazes de criar grupos, verifique se eles não estão sendo bloqueados por meio da política de caixa de [correio do OWA](/powershell/module/exchange/set-owamailboxpolicy).

## <a name="related-topics"></a>Tópicos relacionados

[Planejamento de governança de colaboração passo a passo](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Criar seu plano de governança de colaboração](collaboration-governance-first.md)

[Introdução ao Office 365 PowerShell](../enterprise/getting-started-with-microsoft-365-powershell.md)

[Configurar o gerenciamento de grupo de autoatenduro no Azure Active Directory](/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-ExecutionPolicy](/powershell/module/microsoft.powershell.security/set-executionpolicy)

[Cmdlets Azure Active Directory para definição de configurações de grupo](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
