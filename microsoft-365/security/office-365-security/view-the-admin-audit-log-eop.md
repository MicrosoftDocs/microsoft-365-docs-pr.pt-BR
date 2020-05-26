---
title: Exibir o log de auditoria de administradores no EOP autônomo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Os administradores podem aprender a exibir e pesquisar o log de auditoria do administrador no Exchange Online Protection (EOP) autônomo.
ms.openlocfilehash: b3f2f2601be1ce6e2120b60d23f617ae4e174e08
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351856"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a>Exibir o log de auditoria de administradores no EOP autônomo

Em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, você pode usar o centro de administração do Exchange (Eat) ou o PowerShell autônomo do EOP para pesquisar e exibir entradas no log de auditoria do administrador.

O log de auditoria de administrador registra ações específicas, com base nos cmdlets do PowerShell EOP autônomo, realizadas por administradores e usuários que receberam privilégios administrativos. As entradas no log de auditoria de administrador fornecem informações sobre qual cmdlet foi executado, quais parâmetros foram usados, quem executou o cmdlet e quais objetos foram afetados.

> [!NOTE]
> <ul><li>O log de auditoria de administrador é habilitado por padrão e não pode ser desabilitado.</li><li>O log de auditoria do administrador não registra ações com base nos cmdlets que começam com os verbos **Get**, **Search**ou **Test**.</li><li>As entradas do log de auditoria são armazenadas por 90 dias. Quando uma entrada é mais antiga que 90 dias, ela é excluída</li></ul>

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Para abrir o centro de administração do Exchange, confira [centro de administração do Exchange em EOP autônomo](exchange-admin-center-in-exchange-online-protection-eop.md).

- Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Você precisa receber permissões para executar esses procedimentos. Especificamente, você precisa da função logs de auditoria ou de logs de auditoria somente para exibição, que são atribuídos aos grupos de função ComplianceManagement, gerenciamento (administradores globais) e SecurityAdministrator por padrão. Para obter mais informações, consulte [permissões em EOP autônomos](feature-permissions-in-eop.md) e [use o Eat modificar a lista de membros nos grupos de função](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste tópico, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Está com problemas? Peça ajuda no fórum do [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="use-the-eac-to-view-the-admin-audit-log"></a>Use o Eat para exibir o log de auditoria de administrador

1. No Eat, vá para auditoria de **Gerenciamento de conformidade** \> **Auditing**e, em seguida, escolha **executar o relatório de log de auditoria do administrador**.

2. Na página **Pesquisar alterações nos grupos de funções de administrador** que é aberta, escolha uma **data de início** e uma **data de término** (o intervalo padrão é as duas últimas semanas) e, em seguida, escolha **Pesquisar**. Todas as alterações de configuração feitas durante o período especificado são exibidas e podem ser classificadas com as seguintes informações:

   - **Date**: a data e hora em que a alteração de configuração foi feita. A data e a hora são armazenadas no formato UTC (Tempo Universal Coordenado).

   - **Cmdlet**: o nome do cmdlet que foi usado para fazer a alteração da configuração.

   - **User**: o nome da conta de usuário do usuário que fez a alteração na configuração.

     Serão exibidas até 5.000 entradas em várias páginas. Especifique um intervalo de datas menor se precisar restringir os resultados. Se você selecionar um resultado de pesquisa individual, as informações a seguir serão exibidas no painel de detalhes:

   - **Objeto modificado**: o objeto que foi modificado pelo cmdlet.

   - **Parâmetros (parâmetro: value)**: os parâmetros de cmdlet que foram usados e qualquer valor especificado com o parâmetro.

3. Se quiser imprimir uma determinada entrada do log de auditoria, selecione o botão **Imprimir** no painel de detalhes.

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a>Usar o EOP PowerShell autônomo para exibir o log de auditoria de administrador

Você pode usar o PowerShell autônomo do EOP para pesquisar entradas de log de auditoria que atendam aos critérios especificados. Use a seguinte sintaxe:

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

**Observações**:

- Você só pode usar o parâmetro _Parameters_ juntamente com o parâmetro _cmdlets_ .

- O parâmetro _ObjectIDs_ filtra os resultados pelo objeto que foi modificado pelo cmdlet. Um valor válido depende de como o objeto é representado no log de auditoria. Por exemplo:

  - Nome
  - Nome distinto canônico (por exemplo, contoso.com/Users/Akia Al-Zuhairi)

  Provavelmente você precisará usar outros parâmetros de filtragem nesse cmdlet para restringir os resultados e identificar os tipos de objetos nos quais você está interessado.

- O parâmetro _userids_ filtra os resultados pelo usuário que fez a alteração (quem executou o cmdlet).

- Para os parâmetros _StartDate_ e _EndDate_ , se você especificar um valor de data/hora sem um fuso horário, o valor estará no tempo universal coordenado (UTC). Para especificar um valor de data/hora para este parâmetro, use uma das opções a seguir:

  - Especificar o valor de data/hora em UTC: por exemplo, "2016-05-06 14:30:00Z".

  - Especifique o valor de data/hora como uma fórmula que converte a data/hora em seu fuso horário local em UTC: por exemplo, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` . Para mais informações, consulte [Get-Date](https://go.microsoft.com/fwlink/p/?LinkID=113313).

- Por padrão, o cmdlet retorna um máximo de 1.000 entradas de log. Use o parâmetro _resultize_ para especificar até 250.000 entradas de log. Ou use o valor `Unlimited` para retornar todas as entradas.

Esse exemplo realiza uma pesquisa em todas as entradas de log de auditoria com os seguintes critérios:

- **Data de início**: 4 de agosto de 2019
- **Data de término**: 3 de outubro de 2019
- **Cmdlets**: Update-RoleGroupMember

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).

### <a name="view-details-of-audit-log-entries"></a>Exibir detalhes de entradas de log de auditoria

O cmdlet **Search-AdminAuditLog** retorna os campos descritos na seção [conteúdo do log de auditoria](#audit-log-contents) mais adiante neste tópico. Dos campos retornados pelo cmdlet, dois campos, **CmdletParameters** e **modificados**, contêm informações adicionais que não são retornadas por padrão.

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

|||
|---|---|
|**Field**|**Descrição**|
|`RunspaceId`|Este campo é usado internamente pelo EOP.|
|`ObjectModified`|Este campo contém o objeto que foi modificado pelo cmdlet especificado no `CmdletName` campo.|
|`CmdletName`|Este campo contém o nome do cmdlet que foi executado pelo usuário no `Caller` campo.|
|`CmdletParameters`|Este campo contém os parâmetros que foram especificados quando o cmdlet no `CmdletName` campo foi executado. O valor especificado com o parâmetro, se houver, também é armazenado nesse campo, mas não é visível na saída-padrão.|
|`ModifiedProperties`|Este campo contém as propriedades que foram modificadas no objeto no `ObjectModified` campo. O valor antigo da propriedade e o novo valor que foi armazenado também é armazenado nesse campo, mas não é visível na saída-padrão.|
|`Caller`|Este campo contém a conta de usuário do usuário que executou o cmdlet no `CmdletName` campo.|
|`ExternalAccess`|Este campo é usado internamente pelo EOP.|
|`Succeeded`|Este campo especifica se o cmdlet no `CmdletName` campo foi executado com êxito. O valor é `True` ou `False` .|
|`Error`|Este campo contém a mensagem de erro gerada se o cmdlet no `CmdletName` campo não tiver sido concluído com êxito.|
|`RunDate`|Este campo contém a data e hora em que o cmdlet no `CmdletName` campo foi executado. A data e a hora são armazenadas no formato UTC (Tempo Universal Coordenado).|
|`OriginatingServer`|Este campo indica o servidor no qual o cmdlet especificado no `CmdletName` campo foi executado.|
|`ClientIP`|Este campo é usado internamente pelo EOP.|
|`SessionId`|Este campo é usado internamente pelo EOP.|
|`AppId`|Este campo é usado internamente pelo EOP.|
|`ClientAppId`|Este campo é usado internamente pelo EOP.|
|`Identity`|Este campo é usado internamente pelo EOP.|
|`IsValid`|Este campo é usado internamente pelo EOP.|
|`ObjectState`|Este campo é usado internamente pelo EOP.|
|
