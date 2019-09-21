---
title: Gerenciar grupos no EOP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
description: Você pode usar o Proteção do Exchange Online (EOP) para criar grupos habilitados para email para uma organização do Exchange. Você também pode usar o EOP para definir ou atualizar propriedades de grupo que especificam associação, endereços de email e outros aspectos de grupos.
ms.openlocfilehash: 06813daae3270df61b9aa5aaf67ef322e14a623b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073719"
---
# <a name="manage-groups-in-eop"></a>Gerenciar grupos no EOP

 Você pode usar o Proteção do Exchange Online (EOP) para criar grupos habilitados para email para uma organização do Exchange. Você também pode usar o EOP para definir ou atualizar propriedades de grupo que especificam associação, endereços de email e outros aspectos de grupos. Você pode criar grupos de distribuição e grupos de segurança, dependendo das suas necessidades. Esses grupos podem ser criados usando o Centro de administração do Exchange (EAC) ou pelo Windows PowerShell remoto.
  
## <a name="types-of-mail-enabled-groups"></a>Tipos de grupos habilitados para email

Você pode criar dois tipos de grupos para sua organização do Exchange:
  
- Os grupos de distribuição são conjuntos de usuários de email, como uma equipe ou outro grupo ad hoc, que precisa receber ou enviar emails sobre uma área de interesse comum. Os grupos de distribuição destinam-se exclusivamente à distribuição de mensagens de email. No EOP, um grupo de distribuição refere-se a qualquer grupo habilitado para email, esteja ou não em um contexto de segurança.

- Grupos de segurança são conjuntos de usuários de email que precisam de permissões de acesso para funções de administrador. Por exemplo, talvez você queira fornecer permissões de função de administrador a um grupo específico de usuários para que eles possam definir configurações antispam e antimalware.

    > [!NOTE]
    > Por padrão, todos os novos grupos de segurança habilitados para email exigem que todos os remetentes sejam autenticados. Isso evita que remetentes externos enviem mensagens para grupos de segurança habilitados para email.
  
## <a name="before-you-begin"></a>Antes de você começar

- Para executar este procedimento ou estes procedimentos, você precisa receber permissões. Para ver de que permissões você precisa, consulte o Entrada "Grupos de Distribuição e Grupos de Segurança" no tópico [Permissões de recurso no EOP](feature-permissions-in-eop.md).

- Para abrir o centro de administração do Exchange, confira [Exchange Admin Center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).

- Lembre-se de que durante a criação e o gerenciamento de grupos usando os cmdlets do PowerShell do Exchange Online Protection, você pode encontrar limitação.

- Os procedimentos do PowerShell neste tópico usam um método de processamento em lotes que resulta em um atraso de propagação de alguns minutos antes que os resultados dos comandos fiquem visíveis.

- Para saber como usar o Windows PowerShell para se conectar à proteção do Exchange Online, confira [conectar-se ao PowerShell do Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).

- Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste tópico, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Está com problemas? Peça ajuda no fórum do [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) . 
  
## <a name="create-a-group-in-the-eac"></a>Criar um grupo no EAC

1. No Eat, vá para **grupos**de **destinatários** \> .

2. Clique em **novo** ![ícone](../media/ITPro-EAC-AddIcon.gif)de adição e, em seguida, clique em **grupo de distribuição** ou grupo de **segurança**, dependendo de suas necessidades.

3. Na página **novo grupo de distribuição** ou **novo grupo de segurança** , defina as seguintes configurações:

   - **Nome para exibição**: digite um nome de exibição exclusivo para sua organização e significativo para os usuários do EOP. O nome para exibição é necessário.

   - **Alias**: digite um alias de grupo de até 64 caracteres que seja exclusivo para sua organização. Os usuários do EOP digitam o alias na linha Para: de uma mensagem de email; então ele é convertido para o nome para exibição do grupo. Se você alterar o alias, o endereço SMTP principal do grupo também será alterado e conterá o novo alias. O alias é obrigatório. 

   - **Descrição**: digite uma descrição do grupo para que as pessoas saibam a finalidade do grupo. 

   - **Proprietários**: por padrão, a pessoa que cria o grupo é o proprietário. Você pode adicionar um proprietário escolhendo **Adicionar** ![ícone](../media/ITPro-EAC-AddIcon.gif)de adição. Todos os grupos devem ter no mínimo um proprietário.

     > [!NOTE]
     > Os proprietários do grupo não precisam ser membros do grupo.
  
   - **Membros**: Use esta seção para adicionar membros do grupo e especificar se a aprovação é necessária para que as pessoas ingressem ou saiam do grupo. Para adicionar membros ao grupo, clique em **Adicionar** ![ícone](../media/ITPro-EAC-AddIcon.gif)de adição.

4. Clique em **OK** para retornar à página original.

5. Quando você tiver terminado, clique em **Salvar** para criar o grupo. O novo grupo deve aparecer na lista de grupos.

## <a name="edit-or-remove-a-group-in-the-eac"></a>Editar ou remover um grupo no EAC

1. Na EAC, navegue até **Destinatários** \> **Grupos**.

2. Execute uma das seguintes etapas:

   - Para editar um grupo: na lista de grupos, clique no grupo que você deseja exibir ou alterar e, em seguida, clique em **Editar** ![ícone](../media/ITPro-EAC-EditIcon.gif)de edição. Você pode atualizar as configurações gerais, adicionar ou remover proprietários de grupo e adicionar ou remover membros do grupo, conforme necessário.

   - Para remover um grupo: selecione o grupo e clique em **remover** ![ícone](../media/ITPro-EAC-RemoveIcon.gif)de remoção.

3. Ao terminar de fazer as alterações, clique em **Salvar**.

## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a>Criar, editar ou remover um grupo usando o Windows PowerShell remoto

Esta seção fornece informações sobre como criar grupos e alterar suas propriedades no PowerShell do Exchange Online Protection. Também mostra como remover um grupo existente.
  
### <a name="create-a-group-using-remote-windows-powershell"></a>Criar um grupo usando o Windows PowerShell remoto
  
Este exemplo usa o cmdlet [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) para criar um grupo de distribuição com um alias itadmin e o nome IT Administrators (Administradores de TI). Também adiciona usuários como membros do grupo.
  
```Powershell
New-EOPDistributionGroup -Type Distribution -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy Member1
```

**Observação**: para criar um grupo de segurança em vez de um grupo de distribuição, `Security` use o valor para o parâmetro *Type* .
  
Para verificar se você criou o grupo Administradores de ti com êxito, execute o seguinte comando para exibir informações sobre o novo grupo:
  
```Powershell
Get-Recipient "IT Administrators" | Format-List
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient).

Para obter uma lista de membros no grupo, execute o seguinte comando:
  
```Powershell
Get-DistributionGroupMember "IT Administrators"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).

Para obter uma lista completa de todos os seus grupos, execute o seguinte comando:
  
```Powershell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | Format-Table | more
```

### <a name="change-the-properties-of-a-group-using-remote-windows-powershell"></a>Alterar as propriedades de um grupo usando o Windows PowerShell remoto
  
Uma vantagem de usar o PowerShell em vez da Eat é a capacidade de alterar as propriedades de vários grupos.
  
Aqui estão alguns exemplos de como usar o PowerShell do Exchange Online Protection para alterar as propriedades do grupo.
  
Este exemplo usa as alterações do endereço SMTP principal (também chamado de endereço de resposta) do grupo de Seattle Employees para sea.employees@contoso.com.
  
```Powershell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup).

Para verificar se você alterou com êxito as propriedades do grupo, execute o seguinte comando para verificar o novo valor:
  
```Powershell
Get-Recipient "Seattle Employees" | Format-List "PrimarySmtpAddress"
```

Este exemplo atualiza todos os membros do grupo de Seattle Employees. Use uma vírgula para separar todos os membros.
  
```Powershell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Update-EOPDistributionGroupMember](https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).

Para obter a lista de todos os membros no grupo de Seattle Employees, execute o seguinte comando: 
  
```Powershell
Get-DistributionGroupMember "Seattle Employees"
```

### <a name="remove-a-group-using-remote-windows-powershell"></a>Remover um grupo usando o Windows PowerShell remoto
  
Este exemplo usa remove o grupo de distribuição chamado administradores de ti.
  
```Powershell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).

Para verificar se o grupo foi removido, execute o seguinte comando e confirme se o grupo (neste caso, "administradores de ti") foi excluído.
  
```Powershell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"
```
