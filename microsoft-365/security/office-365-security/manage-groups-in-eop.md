---
title: Gerenciar grupos no EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Os administradores em organizações autônomas do Exchange Online Protection (EOP) podem aprender a criar, modificar e remover grupos de distribuição e grupos de segurança habilitados para email no Centro de administração do Exchange (EAC) e no PowerShell do Exchange Online Protection (EOP) autônomo.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b9d83f2fb59ee8f8d2d3035045ed438d5ba45851
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599564"
---
# <a name="manage-groups-in-eop"></a>Gerenciar grupos no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
-  [Proteção autônoma do Exchange Online](exchange-online-protection-overview.md)

Em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, você pode criar, modificar e remover os seguintes tipos de grupos:

- **Grupos de distribuição**: uma coleção de usuários de email ou outros grupos de distribuição. Por exemplo, equipes ou outros grupos ad hoc que precisam receber ou enviar emails em uma área comum de interesse. Os grupos de distribuição são exclusivamente para distribuir mensagens de email e não são entidades de segurança (eles não podem ter permissões atribuídas a eles).

- **Grupos de segurança habilitados para email**: uma coleção de usuários de email e outros grupos de segurança que precisam de permissões de acesso para funções de administrador. Por exemplo, talvez você queira dar permissões de administrador a um grupo específico de usuários para que eles possam configurar configurações anti-spam e anti-malware.

    > [!NOTE]
    >
    > - Por padrão, novos grupos de segurança habilitados para email rejeitam mensagens de envios externos (não autenticados).
    >
    > - Não adicione grupos de distribuição a grupos de segurança habilitados para email.

Você pode gerenciar grupos no Centro de administração do Exchange (EAC) e no EOP PowerShell autônomo.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Para abrir o centro de administração do Exchange, consulte Centro de [administração do Exchange no EOP autônomo](exchange-admin-center-in-exchange-online-protection-eop.md).

- Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Ao gerenciar grupos no EOP PowerShell autônomo, você pode encontrar a throttling. Os procedimentos do PowerShell neste artigo usam um método de processamento em lote que resulta em um atraso de propagação de alguns minutos antes que os resultados dos comandos sejam visíveis.

- Você precisa ter permissões atribuídas no Exchange Online Protection antes de poder fazer os procedimentos neste artigo. Especificamente, você precisa da função **Grupos de** Distribuição,  que é atribuída aos grupos de função **Gerenciamento** da Organização e Gerenciamento de Destinatários por padrão. Para obter mais informações, consulte [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Para obter informações sobre atalhos de teclado que podem se aplicar aos procedimentos neste artigo, consulte [Atalhos](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)de teclado para o centro de administração do Exchange no Exchange Online .

> [!TIP]
> Está com problemas? Peça ajuda no fórum [Proteção do Exchange Online](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE).

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a>Usar o centro de administração do Exchange para gerenciar grupos de distribuição

### <a name="use-the-eac-to-create-groups"></a>Usar o EAC para criar grupos

1. No EAC, vá para **Grupos de** \> **Destinatários.**

2. Clique **em Novo** ícone Novo e selecione uma das seguintes ![ ](../../media/ITPro-EAC-AddIcon.png) opções:

   - **Grupo de distribuição**

   - **Grupo de segurança habilitado para email**

3. Na nova página de grupo que é aberta, configure as configurações a seguir. As configurações marcadas com <sup>\*</sup> um são necessárias.

   - <sup>\*</sup>**Nome para** exibição : esse nome aparece no livro de endereços da sua organização, na linha Para: quando o email é enviado para esse grupo e na lista **Grupos** no EAC. O nome de exibição é necessário, deve ser exclusivo e deve ser amigável para que as pessoas reconheçam o que é.

   - <sup>\*</sup>**Alias:** use essa caixa para digitar o nome do alias do grupo. O alias não pode exceder 64 caracteres e deve ser exclusivo. Quando um usuário digita o alias na linha Para de uma mensagem de email, ele é resolvido para o nome de exibição do grupo.

   - <sup>\*</sup>**Endereço de** email : o endereço de email consiste no alias no lado esquerdo do símbolo at (@) e um domínio no lado direito. Por padrão, o valor de **Alias** é usado para o valor de alias, mas você pode alterá-lo. Para o valor de domínio, clique no drop-down e selecione e aceite o domínio em sua organização.

   - **Descrição**: essa descrição aparece no livro de endereços e no painel Detalhes no EAC.

   - <sup>\*</sup>**Proprietários**: um proprietário de grupo pode gerenciar a associação ao grupo. Por padrão, a pessoa que cria um grupo é o proprietário. Todos os grupos devem ter no mínimo um proprietário.

     Para adicionar proprietários, clique **em Adicionar** ![ ícone ](../../media/ITPro-EAC-AddIcon.png) . Na caixa de diálogo exibida, encontre e selecione um destinatário ou grupo e clique **em adicionar ->**. Repita essa etapa quantas vezes forem necessárias. Quando terminar, clique em **OK**.

     Para remover um proprietário, selecione o proprietário e clique em **Remover** ![ ícone remover ](../../media/ITPro-EAC-RemoveIcon.gif) .

   - **Membros**: Adicionar e remover membros do grupo.

     Para adicionar membros, clique em **Adicionar** ![ ícone ](../../media/ITPro-EAC-AddIcon.png) . Na caixa de diálogo exibida, encontre e selecione um destinatário ou grupo e clique **em adicionar ->**. Repita essa etapa quantas vezes forem necessárias. Quando terminar, clique em **OK**.

     Para remover um membro, selecione o membro e clique em **Remover** ![ ícone ](../../media/ITPro-EAC-RemoveIcon.gif) Remover.

4. Quando terminar, clique em **Salvar** para criar o grupo de distribuição.

### <a name="use-the-eac-to-modify-distribution-groups"></a>Usar o EAC para modificar grupos de distribuição

1. No EAC, vá para **Grupos de** \> **Destinatários.**

2. Na lista de grupos, selecione o grupo de distribuição ou o grupo de segurança habilitado para email que você deseja modificar e clique em **Editar** ![ ícone editar ](../../media/ITPro-EAC-AddIcon.png) .

3. Na página propriedades do grupo de distribuição que é aberta, clique em uma das seguintes guias para exibir ou alterar propriedades.

   Quando concluir, clique em **Salvar**.

#### <a name="general"></a>Geral

Use esta guia para exibir ou alterar informações básicas sobre o grupo.

- **Nome para** exibição: esse nome aparece no livro de endereços, na linha Para quando o email é enviado para esse grupo e na lista **Grupos.** O nome para exibição é necessário e deve ser amigável para que as pessoas o reconheçam. Ele também deve ser exclusivo em seu domínio.

  Se você implementou uma política de nomeação de grupo, o nome para exibição terá que estar em conformidade com o formato de nomeação definido pela política.

- **Alias**: esta é a parte do endereço de email que aparece à esquerda do símbolo at (@). Se você alterar o alias, o endereço SMTP principal do grupo também será alterado e conterá o novo alias. Além disso, o endereço de email com o alias anterior será mantido como um endereço proxy para o grupo.

- **Endereço de** email : o endereço de email consiste no alias no lado esquerdo do símbolo at (@) e um domínio no lado direito. Por padrão, o valor de **Alias** é usado para o valor de alias, mas você pode alterá-lo. Para o valor de domínio, clique no drop-down e selecione e aceite o domínio em sua organização.

- **Descrição**: essa descrição aparece no livro de endereços e no painel Detalhes no EAC.

#### <a name="ownership"></a>Propriedade

Use esta guia para atribuir proprietários de grupo. Um proprietário de grupo pode gerenciar a associação ao grupo. Por padrão, a pessoa que cria um grupo é o proprietário. Todos os grupos devem ter no mínimo um proprietário.

Para adicionar proprietários, clique **em Adicionar** ![ ícone ](../../media/ITPro-EAC-AddIcon.png) . Na caixa de diálogo exibida, encontre e selecione um destinatário e clique **em adicionar ->**. Repita essa etapa quantas vezes forem necessárias. Quando terminar, clique em **OK**.

Para remover um proprietário, selecione o proprietário e clique em **Remover** ![ ícone remover ](../../media/ITPro-EAC-RemoveIcon.gif) .

#### <a name="membership"></a>Associação

Use essa guia para adicionar ou remover membros do grupo. Os proprietários do grupo não precisam ser membros do grupo.

Para adicionar membros, clique em **Adicionar** ![ ícone ](../../media/ITPro-EAC-AddIcon.png) . Na caixa de diálogo exibida, encontre e selecione um destinatário ou grupo e clique **em adicionar ->**. Repita essa etapa quantas vezes forem necessárias. Quando terminar, clique em **OK**.

Para remover um membro, selecione o membro e clique em **Remover** ![ ícone ](../../media/ITPro-EAC-RemoveIcon.gif) Remover.

### <a name="use-the-eac-to-remove-groups"></a>Usar o EAC para remover grupos

1. No EAC, vá para **Grupos de** \> **Destinatários.**

2. Na lista de grupos, selecione o grupo de distribuição que você deseja remover e clique em **Remover** ![ ícone ](../../media/ITPro-EAC-RemoveIcon.gif) .

## <a name="use-powershell-to-manage-groups"></a>Usar o PowerShell para gerenciar grupos

### <a name="use-standalone-eop-powershell-to-view-groups"></a>Usar o EOP PowerShell autônomo para exibir grupos

Para retornar uma lista resumida de todos os grupos de distribuição e grupos de segurança habilitados para email no EOP PowerShell autônomo, execute o seguinte comando:

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

Para retornar a lista de membros do grupo, substitua pelo nome, alias ou endereço de email do grupo e \<GroupIdentity\> execute o seguinte comando:

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-Recipient](/powershell/module/exchange/get-recipient) e [Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember).

### <a name="use-standalone-eop-powershell-to-create-groups"></a>Usar o EOP PowerShell autônomo para criar grupos

Para criar grupos de distribuição ou grupos de segurança habilitados para email no EOP PowerShell autônomo, use a seguinte sintaxe:

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

**Observações**:

- O _parâmetro Name_ é necessário, tem um comprimento máximo de 64 caracteres e deve ser exclusivo. Se você não usa o parâmetro _DisplayName_, o valor do parâmetro _Name_ é usado para o nome de exibição.

- Se você não usar o parâmetro _Alias,_ o parâmetro _Name_ será usado para o valor de alias. Os espaços são removidos e os caracteres sem suporte são convertidos em pontos de interrogação (?).

- Se você não usar o _parâmetro PrimarySmtpAddress,_ o valor de alias será usado no _parâmetro PrimarySmtpAddress._

- Se você não usar o parâmetro _Type,_ o valor padrão será Distribution.

Este exemplo cria um grupo de distribuição chamado Administradores de IT com as propriedades especificadas.

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-EOPDistributionGroup](/powershell/module/exchange/New-EOPDistributionGroup).

### <a name="use-standalone-eop-powershell-to-modify-groups"></a>Usar o EOP PowerShell autônomo para modificar grupos

Para modificar grupos no EOP PowerShell autônomo, use a seguinte sintaxe:

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

Este exemplo usa alterações no endereço SMTP principal (também chamado de endereço de resposta) do grupo funcionários de Seattle para sea.employees@contoso.com.

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

Este exemplo substitui os membros atuais do grupo equipe de segurança por Kitty Petersen e Tyson Fawcett.

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

Este exemplo adiciona um novo usuário chamado Tyson Fawcett ao grupo chamado Equipe de Segurança, preservando os membros atuais do grupo.

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-EOPDistributionGroup](/powershell/module/exchange/set-eopdistributiongroup) e [Update-EOPDistributionGroupMember](/powershell/module/exchange/update-eopdistributiongroupmember).

### <a name="remove-a-group-using-remote-windows-powershell"></a>Remover um grupo usando Windows PowerShell

Este exemplo usa remove o grupo de distribuição chamado Administradores de IT.

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-EOPDistributionGroup](/powershell/module/exchange/remove-eopdistributiongroup).

## <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se você criou, modificou ou removeu com êxito um grupo de distribuição ou um grupo de segurança habilitado para email, faça uma das seguintes etapas:

- No EAC, vá para **Grupos de** \> **Destinatários.** Verifique se o grupo está listado (ou não listado) e verifique o valor **Tipo de** Grupo. Selecione o grupo e exibir as informações no painel Detalhes ou clique em **Editar** ![ ícone editar para exibir as ](../../media/ITPro-EAC-AddIcon.png) configurações.

- No EOP PowerShell autônomo, execute o seguinte comando para verificar se o grupo está listado (ou não está listado):

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- Substitua pelo nome, alias ou endereço de email do grupo e execute o seguinte comando \<GroupIdentity\> para verificar as configurações:

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- Para exibir os membros do grupo, substitua pelo nome, alias ou endereço de email do grupo e \<GroupIdentity\> execute o seguinte comando:

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```