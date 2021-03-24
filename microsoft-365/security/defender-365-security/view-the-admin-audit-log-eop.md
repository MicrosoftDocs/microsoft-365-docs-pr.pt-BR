---
title: Exibir o log de auditoria de administradores no EOP autônomo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Os administradores podem aprender a exibir e pesquisar o log de auditoria de administrador no EOP (Proteção autônoma do Exchange Online).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5ed1d1eb121c06e6f5727e8782ba1d8bc8d23a99
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053060"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a>Exibir o log de auditoria de administradores no EOP autônomo

**Aplica-se a**
- [Proteção autônoma do Exchange Online](exchange-online-protection-overview.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, você pode usar o Centro de administração do Exchange (EAC) ou o EOP PowerShell autônomo para pesquisar e exibir entradas no log de auditoria do administrador.

O log de auditoria do administrador registra ações específicas, com base em cmdlets autônomos do EOP PowerShell, feitos por administradores e usuários que foram atribuídos a privilégios administrativos. As entradas no log de auditoria do administrador fornecem informações sobre qual cmdlet foi executado, quais parâmetros foram usados, quem correu o cmdlet e quais objetos foram afetados.

> [!NOTE]
>
> - O log de auditoria de administrador está habilitado por padrão e você não pode desabilitá-lo.
>
> - O log de auditoria do administrador não registra ações baseadas em cmdlets que começam com os verbos **Get,** **Search** ou **Test**.
>
> - As entradas do log de auditoria são armazenadas por 90 dias. Quando uma entrada é mais antiga do que 90 dias, ela é excluída

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Para abrir o centro de administração do Exchange, consulte Centro de [administração do Exchange no EOP autônomo](exchange-admin-center-in-exchange-online-protection-eop.md).

- Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Você precisa ter permissões atribuídas no Exchange Online Protection antes de poder fazer os procedimentos neste artigo. Especificamente, você precisa da  função Logs de **Auditoria** ou Logs de Auditoria Somente Exibição, que são atribuídos aos grupos de função Gerenciamento da **Organização,** Gerenciamento de Conformidade e Administrador de Segurança por padrão.  Para obter mais informações, consulte [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Para obter informações sobre atalhos de teclado que podem se aplicar aos procedimentos neste artigo, consulte [Atalhos](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)de teclado para o centro de administração do Exchange no Exchange Online .

> [!TIP]
> Está com problemas? Peça ajuda no fórum [Proteção do Exchange Online](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE).

## <a name="use-the-eac-to-view-the-admin-audit-log"></a>Usar o EAC para exibir o log de auditoria do administrador

1. No EAC, vá para Auditoria de **gerenciamento** de conformidade e, em seguida, escolha Executar o relatório de \> log de auditoria do **administrador.**

2. Na página **Pesquisar alterações nos** grupos de função de administrador que é aberta, escolha uma data de início e data de término (o intervalo padrão é as últimas duas semanas) e escolha **Pesquisar**.   Todas as alterações de configuração feitas durante o período especificado são exibidas e podem ser classificadas com as seguintes informações:

   - **Data**: a data e a hora em que a alteração de configuração foi feita. A data e a hora são armazenadas no formato UTC (Tempo Universal Coordenado).

   - **Cmdlet**: O nome do cmdlet que foi usado para fazer a configuração mudar.

   - **Usuário**: o nome da conta de usuário do usuário que fez a alteração de configuração.

     Serão exibidas até 5.000 entradas em várias páginas. Especifique um intervalo de datas menor se precisar restringir os resultados. Se você selecionar um resultado de pesquisa individual, as informações a seguir serão exibidas no painel de detalhes:

   - **Objeto modificado**: o objeto que foi modificado pelo cmdlet.

   - **Parâmetros (Parameter:Value)**: os parâmetros de cmdlet que foram usados e qualquer valor especificado com o parâmetro.

3. Se quiser imprimir uma determinada entrada do log de auditoria, selecione o botão **Imprimir** no painel de detalhes.

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a>Usar o EOP PowerShell autônomo para exibir o log de auditoria do administrador

Você pode usar o EOP PowerShell autônomo para pesquisar entradas de log de auditoria que atendem aos critérios especificados. Use a seguinte sintaxe:

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

**Observações**:

- Você só pode usar o _parâmetro Parameters_ juntamente com o _parâmetro Cmdlets._

- O _parâmetro ObjectIds_ filtra os resultados pelo objeto modificado pelo cmdlet. Um valor válido depende de como o objeto é representado no log de auditoria. Por exemplo:

  - Nome
  - Nome diferenciado canônico (por exemplo, contoso.com/Users/Akia Al-Zuhairi)

  Você provavelmente precisará usar outros parâmetros de filtragem neste cmdlet para restringir os resultados e identificar os tipos de objetos nos quais você está interessado.

- O _parâmetro UserIds_ filtra os resultados pelo usuário que fez a alteração (que correu o cmdlet).

- Para os _parâmetros StartDate_ e _EndDate,_ se você especificar um valor de data/hora sem um fuso horário, o valor está em Tempo Universal Coordenado (UTC). Para especificar um valor de data/hora para este parâmetro, use uma das opções a seguir:

  - Especificar o valor de data/hora em UTC: por exemplo, "2016-05-06 14:30:00Z".

  - Especifique o valor de data/hora como uma fórmula que converte a data/hora em seu fuso horário local para UTC: por exemplo, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` . Para mais informações, consulte [Get-Date](/powershell/module/microsoft.powershell.utility/get-date).

- O cmdlet retorna um máximo de 1.000 entradas de log por padrão. Use o _parâmetro ResultSize_ para especificar até 250.000 entradas de log. Ou, use o valor `Unlimited` para retornar todas as entradas.

Esse exemplo realiza uma pesquisa em todas as entradas de log de auditoria com os seguintes critérios:

- **Data de início**: 4 de agosto de 2019
- **Data de término**: 3 de outubro de 2019
- **Cmdlets**: Update-RoleGroupMember

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog).

### <a name="view-details-of-audit-log-entries"></a>Exibir detalhes de entradas de log de auditoria

O cmdlet **Search-AdminAuditLog** retorna os campos descritos na seção Conteúdo do log de [auditoria](#audit-log-contents) posteriormente neste artigo. Dos campos retornados pelo cmdlet, dois campos, **CmdletParameters** e **ModifiedProperties**, contêm informações adicionais que não são retornadas por padrão.

Para exibir o conteúdo dos campos **CmdletParameters** e **ModifiedProperties**, siga as etapas na sequência.

1. Decida quais critérios deseja pesquisa, execute o cmdlet **Search-AdminAuditLog** e armazene os resultados em uma variável usando o seguinte comando.

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. Cada entrada de log de auditoria é armazenada como um elemento de matriz na variável `$Results` . Você pode selecionar um elemento de matriz especificando seu índice de elemento de matriz. Os índices de elemento de matriz começam em zero (0) para o primeiro elemento da matriz. Por exemplo, para recuperar o elemento da quinta matriz, que tem um índice de 4, use o comando a seguir.

    ```PowerShell
    $Results[4]
    ```

3. O comando anterior retorna a entrada de log armazenada no elemento de matriz 4. Para ver o conteúdo dos campos **CmdletParameters** e **ModifiedProperties** referentes a essa entrada de log, use os seguintes comandos.

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. Para exibir o conteúdo dos campos **CmdletParameters** ou **ModifiedParameters** em outra entrada de log, altere o índice do elemento de matriz.

## <a name="audit-log-contents"></a>Conteúdo do log de auditoria

Cada entrada de log de auditoria contém as informações descritas na tabela a seguir. O log de auditoria contém uma ou mais entradas de log de auditoria.

****

|Campo|Descrição|
|---|---|
|`RunspaceId`|Esse campo é usado internamente pelo EOP.|
|`ObjectModified`|Este campo contém o objeto modificado pelo cmdlet especificado no `CmdletName` campo.|
|`CmdletName`|Este campo contém o nome do cmdlet que foi executado pelo usuário no `Caller` campo.|
|`CmdletParameters`|Este campo contém os parâmetros que foram especificados quando o cmdlet no `CmdletName` campo foi executado. O valor especificado com o parâmetro, se houver, também é armazenado nesse campo, mas não é visível na saída-padrão.|
|`ModifiedProperties`|Este campo contém as propriedades que foram modificadas no objeto no `ObjectModified` campo. O valor antigo da propriedade e o novo valor que foi armazenado também é armazenado nesse campo, mas não é visível na saída-padrão.|
|`Caller`|Este campo contém a conta de usuário do usuário que correu o cmdlet no `CmdletName` campo.|
|`ExternalAccess`|Esse campo é usado internamente pelo EOP.|
|`Succeeded`|Este campo especifica se o cmdlet no `CmdletName` campo foi realizado com êxito. O valor é ou `True` `False` .|
|`Error`|Este campo contém a mensagem de erro gerada se o cmdlet no `CmdletName` campo não tiver êxito.|
|`RunDate`|Este campo contém a data e a hora em que o cmdlet no `CmdletName` campo foi executado. A data e a hora são armazenadas no formato UTC (Tempo Universal Coordenado).|
|`OriginatingServer`|Este campo indica o servidor no qual o cmdlet especificado no `CmdletName` campo foi executado.|
|`ClientIP`|Esse campo é usado internamente pelo EOP.|
|`SessionId`|Esse campo é usado internamente pelo EOP.|
|`AppId`|Esse campo é usado internamente pelo EOP.|
|`ClientAppId`|Esse campo é usado internamente pelo EOP.|
|`Identity`|Esse campo é usado internamente pelo EOP.|
|`IsValid`|Esse campo é usado internamente pelo EOP.|
|`ObjectState`|Esse campo é usado internamente pelo EOP.|
|