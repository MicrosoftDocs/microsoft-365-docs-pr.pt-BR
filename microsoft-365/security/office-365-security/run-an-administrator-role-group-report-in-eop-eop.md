---
title: Executar um relatório de grupo de função de administrador no EOP autônomo
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
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a executar um relatório de grupo de funções de administrador no proteção do Exchange Online (EOP) autônomo. Este relatório registra quando um administrador adiciona ou remove membros de grupos de funções de administrador, EOP registra cada ocorrência.
ms.openlocfilehash: 0c504460657a153aad7d3dd065c81007a68ba916
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2020
ms.locfileid: "44587359"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a>Executar um relatório de grupo de função de administrador no EOP autônomo

Em organizações autônomas de proteção do Exchange Online (EOP) sem caixas de correio do Exchange Online, quando um administrador adiciona ou remove membros dos grupos de função administrativa, o serviço registra cada ocorrência. Para obter mais informações sobre grupos de função em EOP autônomos, consulte [permissões no EOP autônomo](feature-permissions-in-eop.md).

Quando você executa um relatório de grupo de funções de administrador no centro de administração do Exchange (Eat), as entradas são exibidas como resultados de pesquisa e incluem os grupos de função afetados, quem alterou a associação do grupo de função e quando e quais foram feitas as atualizações de associação. Use esse relatório para monitorar as alterações nas permissões administrativas atribuídas aos usuários da sua organização.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Para abrir o centro de administração do Exchange, confira [centro de administração do Exchange em EOP autônomo](exchange-admin-center-in-exchange-online-protection-eop.md).

- Você precisa receber permissões para executar esses procedimentos. Especificamente, você precisa da função logs de auditoria ou de logs de auditoria somente para exibição, que são atribuídos aos grupos de função ComplianceManagement, gerenciamento (administradores globais) e SecurityAdministrator por padrão. Para obter mais informações, consulte [permissões em EOP autônomos](feature-permissions-in-eop.md) e [use o Eat modificar a lista de membros nos grupos de função](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste tópico, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Está com problemas? Peça ajuda no fórum do [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>Usar o EAC para executar o relatório de grupo de funções de administrador

Execute o relatório do grupo de funções de administrador para localizar as alterações nos grupos de função de gerenciamento em sua organização dentro de um determinado período.

1. No Eat, vá para auditoria de **Gerenciamento de conformidade** \> **Auditing**e, em seguida, escolha **executar um relatório de grupo de função de administrador**.

2. Na página **Pesquisar alterações nos grupos de funções de administrador** que é aberta, defina as seguintes configurações:

   - **Data de início** e **data de término**: Insira um intervalo de datas. Por padrão, o relatório procura alterações feitas nos grupos de funções do administrador nas duas últimas semanas.

   - **Selecionar grupos de função**: por padrão, todos os grupos de função são pesquisados. Para filtrar os resultados por grupos de função específicos, clique em **Selecionar grupos de função**. Na caixa de diálogo exibida, selecione um grupo de função e clique em **Adicionar->**. Repita essa etapa quantas vezes for necessário e clique em **OK** quando terminar.

3. Quando tiver concluído, clique em **Pesquisar**.

Se quaisquer alterações forem encontradas usando os critérios especificados, elas aparecerão no painel de resultados. Clique em um grupo de função nos resultados da pesquisa para ver as alterações no painel de detalhes.

## <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Se você executou com sucesso um relatório de grupo de funções do administrador, os grupos de funções que foram alterados dentro do intervalo de datas serão exibidos no painel de resultados da pesquisa. Se não houver resultados, nenhuma alteração nos grupos de funções será executada dentro do intervalo de datas especificado. Se julgar que deveria haver resultados, altere o intervalo de dados e execute novamente o relatório.

## <a name="monitor-changes-to-role-group-membership"></a>Monitorar alterações na associação de grupo de funções

Quando os membros são adicionados ou removidos de um grupo de funções, os resultados da pesquisa exibidos no painel de detalhes indicam que a associação de grupo de funções foi atualizada e lista os membros atuais. Os resultados não informam explicitamente qual usuário foi adicionado ou removido.

Para determinar se um usuário foi adicionado ou removido, você terá que comparar duas entradas separadas no relatório. Por exemplo, vamos observar as entradas de log a seguir do grupo de funções de **HelpDesk**:

> 1/27/2018 4:43 PM <br> Administrador <br> Membros atualizados: Administrator;annb,florencef;pilarp <br> 2/06/2018 10:09 AM <br> Administrador <br> Membros atualizados: Administrator;annb;florencef;pilarp;tonip <br> 2/19/2018 2:12 PM <br> Administrador <br> Membros atualizados: Administrator;annb;florencef;tonip

Nesse exemplo, a conta de usuário Administrador fez as seguintes alterações:

- No 2/06/2018, eles adicionaram o usuário tonip.

- No 2/19/2018, eles removeram o usuário pilarp.

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a>Usar o PowerShell autônomo do Exchange Online para pesquisar entradas de log de auditoria

Você pode usar o PowerShell do Exchange Online para pesquisar entradas de log de auditoria que atendam aos critérios especificados. Para obter uma lista de critérios de pesquisa, consulte [Search-AdminAuditLog search criteria](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet). Este procedimento usa o cmdlet **Search-AdminAuditLog** e exibe os resultados da pesquisa no PowerShell do Exchange Online. Ele pode ser usado quando você precisa retornar um conjunto de resultados que exceda os limites definidos no cmdlet **New-AdminAuditLogSearch** ou nos Relatórios de Auditoria do EAC.

Para pesquisar no log de auditoria pelos critérios especificados, use a sintaxe a seguir.

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> O cmdlet **Search-AdminAuditLog** retorna um máximo de 1.000 entradas de log por padrão. Use o parâmetro _resultize_ para especificar até 250.000 entradas de log. Ou use o valor `Unlimited` para retornar todas as entradas.

Esse exemplo realiza uma pesquisa em todas as entradas de log de auditoria com os seguintes critérios:

- **Data de início**: 08/04/2018

- **Data de término**: 10/03/2018

- **IDs de usuário**: Davids, Carla, Kima

- **Cmdlets**: **Set-Mailbox**

- **Parâmetros**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

Este exemplo pesquisa alterações efetuadas em uma caixa de correio específica. Isso será útil se você estiver solucionando problemas ou precisar fornecer informações para uma investigação. Os seguintes critérios são usados:

- **Data de início**: 05/01/2018

- **Data de término**: 10/03/2018

- **ID do objeto**: contoso.com/users/DavidS

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

Se as pesquisas retornarem muitas entradas de log, recomendamos que você use o procedimento fornecido em **usar o PowerShell do Exchange Online para pesquisar entradas de log de auditoria e enviar resultados para um destinatário** mais adiante neste tópico. O procedimento dessa seção envia um arquivo XML como anexo de email aos destinatários especificados, permitindo que você extraia com mais facilidade os dados em que está interessado.

Para informações detalhadas de sintaxes e de parâmetros, consulte [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).

### <a name="view-details-of-audit-log-entries"></a>Exibir detalhes de entradas de log de auditoria

O cmdlet **Search-AdminAuditLog** retorna os campos descritos no [conteúdo do log de auditoria](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents). Desses campos retornados pelo cmdlet, dois campos, **CmdletParameters** e **ModifiedProperties**, contêm informações adicionais que não podem ser exibidas por padrão.

Para exibir o conteúdo dos campos **CmdletParameters** e **ModifiedProperties**, siga as etapas na sequência. Ou você pode usar o procedimento em **usar o Exchange Online PowerShell para pesquisar entradas de log de auditoria e enviar resultados para um destinatário** posteriormente neste tópico para criar um arquivo XML.

Esse procedimento usa os seguintes conceitos:

- [about_Arrays](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [about_Variables](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

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