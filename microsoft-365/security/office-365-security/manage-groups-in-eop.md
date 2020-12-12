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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Administradores no proteção autônoma do Exchange Online (EOP) as organizações podem aprender a criar, modificar e remover grupos de distribuição e grupos de segurança habilitados para email no centro de administração do Exchange (Eat) e no PowerShell autônomo do Exchange Online Protection (EOP).
ms.openlocfilehash: 5ff7c61d51ded039b06d1faa98ba6390939b3413
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658840"
---
# <a name="manage-groups-in-eop"></a>Gerenciar grupos no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, você pode criar, modificar e remover os seguintes tipos de grupos:

- **Grupos de distribuição**: uma coleção de usuários de email ou outros grupos de distribuição. Por exemplo, equipes ou outros grupos ad hoc que precisam receber ou enviar emails em uma área comum de interesse. Os grupos de distribuição são exclusivamente para distribuir mensagens de email e não são entidades de segurança (elas não podem ter permissões atribuídas a eles).

- **Grupos de segurança habilitados para email**: uma coleção de usuários de email e outros grupos de segurança que precisam de permissões de acesso para funções de administrador. Por exemplo, você pode querer conceder permissões de administrador de grupo específico de usuários para que eles possam definir configurações antispam e antimalware.

    > [!NOTE]
    >
    > - Por padrão, novos grupos de segurança habilitados para email rejeitam mensagens de remetentes externos (não autenticados).
    >
    > - Não adicione grupos de distribuição a grupos de segurança habilitados para email.

Você pode gerenciar grupos no centro de administração do Exchange (Eat) e no PowerShell do EOP autônomo.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Para abrir o centro de administração do Exchange, confira [centro de administração do Exchange em EOP autônomo](exchange-admin-center-in-exchange-online-protection-eop.md).

- Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Ao gerenciar grupos no EOP PowerShell autônomo, você pode encontrar limitação. Os procedimentos do PowerShell neste artigo usam um método de processamento em lotes que resulta em um atraso de propagação de alguns minutos antes que os resultados dos comandos fiquem visíveis.

- Você precisa receber permissões na proteção do Exchange Online antes de poder executar os procedimentos deste artigo. Especificamente, você precisará da função **grupos de distribuição** , que é atribuída aos grupos de funções **Gerenciamento da organização** e gerenciamento de **destinatários** por padrão. Para obter mais informações, consulte [permissões em EOP autônomos](feature-permissions-in-eop.md) e [use o Eat modificar a lista de membros nos grupos de função](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste artigo, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Está com problemas? Peça ajuda no fórum [Proteção do Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=285351).

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a>Usar o centro de administração do Exchange para gerenciar grupos de distribuição

### <a name="use-the-eac-to-create-groups"></a>Usar o Eat para criar grupos

1. No Eat, vá para grupos de **destinatários** \> .

2. Clique em **novo** ![ ícone novo ](../../media/ITPro-EAC-AddIcon.png) e selecione uma das seguintes opções:

   - **Grupo de distribuição**

   - **Grupo de segurança habilitado para email**

3. Na página novo grupo que é aberta, defina as configurações a seguir. As configurações marcadas com um <sup>\*</sup> são obrigatórias.

   - <sup>\*</sup>**Nome para exibição**: esse nome é exibido no catálogo de endereços da sua organização, na linha para: quando o email é enviado a esse grupo e na lista de **grupos** no Eat. O nome para exibição é necessário, deve ser exclusivo e ser intuitivo para o usuário, para que as pessoas reconheçam o que é.

   - <sup>\*</sup>**Alias**: Use esta caixa para digitar o nome do alias do grupo. O alias não pode exceder 64 caracteres e deve ser exclusivo. Quando um usuário digita o alias na linha para de uma mensagem de email, ele é resolvido como o nome de exibição do grupo.

   - <sup>\*</sup>**Endereço de email**: o endereço de email consiste no alias no lado esquerdo do símbolo de arroba (@) e em um domínio no lado direito. Por padrão, o valor de **alias** é usado para o valor do alias, mas você pode alterá-lo. Para o valor de domínio, clique no menu suspenso e selecione o domínio aceito em sua organização.

   - **Descrição**: esta descrição aparece no catálogo de endereços e no painel de detalhes no Eat.

   - <sup>\*</sup>**Proprietários**: um proprietário de grupo pode gerenciar A Associação de grupo. Por padrão, a pessoa que cria um grupo é o proprietário. Todos os grupos devem ter no mínimo um proprietário.

     Para adicionar proprietários, clique em **Adicionar** ![ ícone de adição ](../../media/ITPro-EAC-AddIcon.png) . Na caixa de diálogo exibida, localize e selecione um destinatário ou grupo e clique em **Adicionar->**. Repita essa etapa quantas vezes forem necessárias. Quando tiver concluído, clique em **OK**.

     Para remover um proprietário, selecione o proprietário e, em seguida, clique em **remover** ![ Remover ícone ](../../media/ITPro-EAC-RemoveIcon.gif) .

   - **Membros**: Adicionar e remover membros do grupo.

     Para adicionar membros, clique em **Adicionar** ![ ícone de adição ](../../media/ITPro-EAC-AddIcon.png) . Na caixa de diálogo exibida, localize e selecione um destinatário ou grupo e clique em **Adicionar->**. Repita essa etapa quantas vezes forem necessárias. Quando tiver concluído, clique em **OK**.

     Para remover um membro, selecione-o e clique em **remover** ![ ícone Remover ](../../media/ITPro-EAC-RemoveIcon.gif) .

4. Quando tiver terminado, clique em **salvar** para criar o grupo de distribuição.

### <a name="use-the-eac-to-modify-distribution-groups"></a>Usar o Eat para modificar grupos de distribuição

1. No Eat, vá para grupos de **destinatários** \> .

2. Na lista de grupos, selecione o grupo de distribuição ou grupo de segurança habilitado para email que você deseja modificar e clique em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-AddIcon.png) .

3. Na página de propriedades do grupo de distribuição que é aberta, clique em uma das guias a seguir para exibir ou alterar propriedades.

   Quando concluir, clique em **Salvar**.

#### <a name="general"></a>Geral

Use essa guia para exibir ou alterar as informações básicas sobre o grupo.

- **Nome para exibição**: esse nome é exibido no catálogo de endereços, na linha para quando o email é enviado a esse grupo e na **lista de grupos**. O nome para exibição é necessário e deve ser amigável para que as pessoas o reconheçam. Ele também deve ser exclusivo em seu domínio.

  Se você implementou uma política de nomeação de grupo, o nome para exibição terá que estar em conformidade com o formato de nomeação definido pela política.

- **Alias**: esta é a parte do endereço de email que aparece à esquerda do símbolo de arroba (@). Se você alterar o alias, o endereço SMTP principal do grupo também será alterado e conterá o novo alias. Além disso, o endereço de email com o alias anterior será mantido como um endereço proxy para o grupo.

- **Endereço de email**: o endereço de email consiste no alias no lado esquerdo do símbolo de arroba (@) e em um domínio no lado direito. Por padrão, o valor de **alias** é usado para o valor do alias, mas você pode alterá-lo. Para o valor de domínio, clique no menu suspenso e selecione o domínio aceito em sua organização.

- **Descrição**: esta descrição aparece no catálogo de endereços e no painel de detalhes no Eat.

#### <a name="ownership"></a>Propriedade

Use esta guia para atribuir proprietários de grupo. Um proprietário de grupo pode gerenciar A Associação de grupo. Por padrão, a pessoa que cria um grupo é o proprietário. Todos os grupos devem ter no mínimo um proprietário.

Para adicionar proprietários, clique em **Adicionar** ![ ícone de adição ](../../media/ITPro-EAC-AddIcon.png) . Na caixa de diálogo exibida, localize e selecione um destinatário e clique em **Adicionar->**. Repita essa etapa quantas vezes forem necessárias. Quando tiver concluído, clique em **OK**.

Para remover um proprietário, selecione o proprietário e, em seguida, clique em **remover** ![ Remover ícone ](../../media/ITPro-EAC-RemoveIcon.gif) .

#### <a name="membership"></a>Associação

Use esta guia para adicionar ou remover membros do grupo. Os proprietários do grupo não precisam ser membros do grupo.

Para adicionar membros, clique em **Adicionar** ![ ícone de adição ](../../media/ITPro-EAC-AddIcon.png) . Na caixa de diálogo exibida, localize e selecione um destinatário ou grupo e clique em **Adicionar->**. Repita essa etapa quantas vezes forem necessárias. Quando tiver concluído, clique em **OK**.

Para remover um membro, selecione-o e clique em **remover** ![ ícone Remover ](../../media/ITPro-EAC-RemoveIcon.gif) .

### <a name="use-the-eac-to-remove-groups"></a>Usar o Eat para remover grupos

1. No Eat, vá para grupos de **destinatários** \> .

2. Na lista de grupos, selecione o grupo de distribuição que você deseja remover e clique em **remover** ![ ícone de remoção ](../../media/ITPro-EAC-RemoveIcon.gif) .

## <a name="use-powershell-to-manage-groups"></a>Usar o PowerShell para gerenciar grupos

### <a name="use-standalone-eop-powershell-to-view-groups"></a>Usar o EOP PowerShell autônomo para exibir grupos

Para retornar uma lista resumida de todos os grupos de distribuição e grupos de segurança habilitados para email no PowerShell autônomo do EOP, execute o seguinte comando:

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

Para retornar a lista de membros do grupo, substitua-o \<GroupIdentity\> pelo nome, alias ou endereço de email do grupo e execute o seguinte comando:

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) e [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).

### <a name="use-standalone-eop-powershell-to-create-groups"></a>Usar o EOP PowerShell autônomo para criar grupos

Para criar grupos de distribuição ou grupos de segurança habilitados para email no PowerShell autônomo do EOP, use a seguinte sintaxe:

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

**Observações**:

- O parâmetro _Name_ é obrigatório, tem um comprimento máximo de 64 caracteres e deve ser exclusivo. Se você não usa o parâmetro _DisplayName_, o valor do parâmetro _Name_ é usado para o nome de exibição.

- Se você não usar o parâmetro _alias_ , o parâmetro _Name_ será usado para o valor do alias. Os espaços são removidos e os caracteres não suportados são convertidos em pontos de interrogação (?).

- Se você não usar o parâmetro _PrimarySmtpAddress_ , o valor do alias será usado no parâmetro _PrimarySmtpAddress_ .

- Se você não usar o parâmetro _Type_ , o valor padrão será Distribution.

Este exemplo cria um grupo de distribuição chamado administradores de ti com as propriedades especificadas.

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).

### <a name="use-standalone-eop-powershell-to-modify-groups"></a>Usar o EOP PowerShell autônomo para modificar grupos

Para modificar grupos no EOP PowerShell autônomo, use a seguinte sintaxe:

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

Este exemplo usa as alterações do endereço SMTP principal (também chamado de endereço de resposta) do grupo de Seattle Employees para sea.employees@contoso.com.

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

Este exemplo substitui os membros atuais do grupo equipe de segurança por Kitty Petersen e Tyson Fawcett.

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

Este exemplo adiciona um novo usuário chamado Tyson Fawcett ao grupo chamado equipe de segurança enquanto preserva os membros atuais do grupo.

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) e [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).

### <a name="remove-a-group-using-remote-windows-powershell"></a>Remover um grupo usando o Windows PowerShell remoto

Este exemplo usa remove o grupo de distribuição chamado administradores de ti.

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).

## <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se você criou, modificou ou removeu com êxito um grupo de distribuição ou um grupo de segurança habilitado para email, execute uma das seguintes etapas:

- No Eat, vá para grupos de **destinatários** \> . Verifique se o grupo está listado (ou não listado) e verifique o valor do **tipo de grupo** . Selecione o grupo e visualize as informações no painel de detalhes ou clique em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-AddIcon.png) para exibir as configurações.

- Em EOP autônomo do PowerShell, execute o seguinte comando para verificar se o grupo está listado (ou não está listado):

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- Substitua \<GroupIdentity\> pelo nome, alias ou endereço de email do grupo e execute o seguinte comando para verificar as configurações:

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- Para exibir os membros do grupo, substitua o \<GroupIdentity\> nome, o alias ou o endereço de email do grupo e execute o seguinte comando:

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
