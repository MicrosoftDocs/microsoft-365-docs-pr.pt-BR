---
title: Executar um relatório de grupo de função de administrador no EOP autônomo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a executar um relatório de grupo de funções de administrador no Exchange Online Protection (EOP) autônomo. Esse relatório registra quando um administrador adiciona membros a ou remove membros de grupos de função de administrador.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d778e807a087a5e29b31645457d4a81bd05c5649
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288014"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a>Executar um relatório de grupo de função de administrador no EOP autônomo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
-  [Proteção do Exchange Online autônoma](exchange-online-protection-overview.md)

Em organizações autônomas do Proteção do Exchange Online (EOP) sem caixas de correio do Exchange Online, quando um administrador adiciona membros ou remove membros de grupos de funções administrativas, o serviço registra cada ocorrência. Para obter mais informações sobre grupos de função no EOP autônomo, consulte Permissões no [EOP autônomo.](feature-permissions-in-eop.md)

Quando você executar um relatório de grupo de função de administrador no Centro de administração do Exchange (EAC), as entradas são exibidas como resultados de pesquisa e incluem os grupos de função afetados, quem alterou a associação do grupo de função e quando e quais atualizações de associação foram feitas. Use esse relatório para monitorar as alterações nas permissões administrativas atribuídas aos usuários da sua organização.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Para abrir o Centro de administração do Exchange, confira o Centro de administração [do Exchange no EOP autônomo.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Você precisa ter permissões no Exchange Online Protection antes de poder fazer os procedimentos neste artigo. Especificamente, você precisa da  função **Logs** de Auditoria ou **Logs** de Auditoria Somente Exibição, que são atribuídas aos grupos de funções Gerenciamento da **Organização,** Gerenciamento de Conformidade e Administrador de Segurança por padrão. Para obter mais informações, [consulte Permissões no EOP](feature-permissions-in-eop.md) autônomo e use o EAC modificar a lista de [membros em grupos de função.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Para obter informações sobre atalhos de teclado que podem se aplicar aos procedimentos neste artigo, consulte [Atalhos](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)de teclado para o Centro de administração do Exchange no Exchange Online .

> [!TIP]
> Está com problemas? Peça ajuda no fórum [Proteção do Exchange Online](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE).

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>Usar o EAC para executar o relatório de grupo de funções de administrador

Execute o relatório do grupo de funções de administrador para encontrar as alterações nos grupos de função de gerenciamento dentro de um determinado período de tempo.

1. No EAC, vá para Auditoria de **gerenciamento** de conformidade e escolha Executar um relatório de grupo de funções \>  **de administrador.**

2. Na página **Pesquisar alterações nos grupos de função de administrador** que é aberta, de configure as seguintes configurações:

   - **Data de início** **e data de** término: insira um intervalo de datas. Por padrão, o relatório procura alterações feitas nos grupos de funções do administrador nas duas últimas semanas.

   - **Selecionar grupos de função:** Por padrão, todos os grupos de funções são pesquisados. Para filtrar os resultados por grupos de função específicos, clique **em Selecionar grupos de função.** Na caixa de diálogo exibida, selecione um grupo de funções e clique **em add ->**. Repita essa etapa quantas vezes for necessário e clique em **OK** quando terminar.

3. Quando terminar, clique em **Pesquisar.**

Se quaisquer alterações forem encontradas usando os critérios especificados, elas aparecerão no painel de resultados. Clique em um grupo de função nos resultados da pesquisa para ver as alterações no painel de detalhes.

## <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Se você executou com sucesso um relatório de grupo de funções do administrador, os grupos de funções que foram alterados dentro do intervalo de datas serão exibidos no painel de resultados da pesquisa. Se não houver resultados, nenhuma alteração nos grupos de funções será executada dentro do intervalo de datas especificado. Se julgar que deveria haver resultados, altere o intervalo de dados e execute novamente o relatório.

## <a name="monitor-changes-to-role-group-membership"></a>Monitorar alterações na associação de grupo de funções

Quando os membros são adicionados ou removidos de um grupo de funções, os resultados da pesquisa exibidos no painel de detalhes indicam que a associação de grupo de funções foi atualizada e lista os membros atuais. Os resultados não informam explicitamente qual usuário foi adicionado ou removido.

Para determinar se um usuário foi adicionado ou removido, você terá que comparar duas entradas separadas no relatório. Por exemplo, vamos observar as entradas de log a seguir do grupo de funções de **HelpDesk**:

> 27/1/2018 16:43 <br> Administrador <br> Membros atualizados: Administrator;annb,florencef;pilarp <br> 06/02/2018 10:09 <br> Administrador <br> Membros atualizados: Administrator;annb;florencef;pilarp;tonip <br> 19/02/2018 14:12 <br> Administrador <br> Membros atualizados: Administrator;annb;florencef;tonip

Nesse exemplo, a conta de usuário Administrador fez as seguintes alterações:

- Em 06/02/2018, ele adicionou o tonip do usuário.
- Em 19/02/2018, a usuária pilarp foi removida.

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a>Usar o PowerShell autônomo do Exchange Online para procurar entradas de log de auditoria

Você pode usar o PowerShell do Exchange Online para pesquisar entradas de log de auditoria que atendem aos critérios especificados. Para uma lista de critérios de pesquisa, consulte Critérios de pesquisa [Search-AdminAuditLog](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet). Este procedimento usa o cmdlet **Search-AdminAuditLog** e exibe os resultados da pesquisa no PowerShell do Exchange Online. Ele pode ser usado quando você precisa retornar um conjunto de resultados que exceda os limites definidos no cmdlet **New-AdminAuditLogSearch** ou nos Relatórios de Auditoria do EAC.

Para pesquisar no log de auditoria pelos critérios especificados, use a sintaxe a seguir.

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> O cmdlet **Search-AdminAuditLog** retorna um máximo de 1.000 entradas de log por padrão. Use o _parâmetro ResultSize_ para especificar até 250.000 entradas de log. Ou use o valor `Unlimited` para retornar todas as entradas.

Esse exemplo realiza uma pesquisa em todas as entradas de log de auditoria com os seguintes critérios:

- **Data de** início : 04/08/2018
- **Data de** término : 03/10/2018
- **IDs de usuário:** `davids` `chrisd` , `kima`
- **Cmdlets**: **Set-Mailbox**
- **Parâmetros**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

Este exemplo pesquisa alterações efetuadas em uma caixa de correio específica. Isso será útil se você estiver solucionando problemas ou precisar fornecer informações para uma investigação. Os seguintes critérios são usados:

- **Data de** início : 01/05/2018
- **Data de** término : 03/10/2018
- **ID do** objeto : contoso.com/Users/DavidS

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

Se suas pesquisas retornarem muitas entradas de log, recomendamos que você use o procedimento fornecido em Usar o **PowerShell** do Exchange Online para procurar entradas de log de auditoria e enviar resultados a um destinatário posteriormente neste artigo. O procedimento dessa seção envia um arquivo XML como anexo de email aos destinatários especificados, permitindo que você extraia com mais facilidade os dados em que está interessado.

Para informações detalhadas de sintaxes e de parâmetros, consulte [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).

### <a name="view-details-of-audit-log-entries"></a>Exibir detalhes de entradas de log de auditoria

O cmdlet **Search-AdminAuditLog** retorna os campos descritos no [conteúdo do log de auditoria.](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents) Desses campos retornados pelo cmdlet, dois campos, **CmdletParameters** e **ModifiedProperties**, contêm informações adicionais que não podem ser exibidas por padrão.

Para exibir o conteúdo dos campos **CmdletParameters** e **ModifiedProperties**, siga as etapas na sequência. Ou você pode usar o procedimento em Usar o **PowerShell** do Exchange Online para procurar entradas de log de auditoria e enviar resultados a um destinatário posteriormente neste artigo para criar um arquivo XML.

Esse procedimento usa os seguintes conceitos:

- [about_Arrays](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [about_Variables](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

1. Decida quais critérios deseja pesquisa, execute o cmdlet **Search-AdminAuditLog** e armazene os resultados em uma variável usando o seguinte comando.

   ```PowerShell
   $Results = Search-AdminAuditLog <search criteria>
   ```

2. Cada entrada de log de auditoria é armazenada como um elemento de matriz na `$Results` variável. Você pode selecionar um elemento de matriz especificando seu índice de elemento de matriz. Os índices de elemento de matriz começam em zero (0) para o primeiro elemento da matriz. Por exemplo, para recuperar o elemento da quinta matriz, que tem um índice de 4, use o comando a seguir.

   ```PowerShell
   $Results[4]
   ```

3. O comando anterior retorna a entrada de log armazenada no elemento de matriz 4. Para ver o conteúdo dos campos **CmdletParameters** e **ModifiedProperties** referentes a essa entrada de log, use os seguintes comandos.

   ```PowerShell
   $Results[4].CmdletParameters
   $Results[4].ModifiedProperties
   ```

4. Para exibir o conteúdo dos campos **CmdletParameters** ou **ModifiedParameters** em outra entrada de log, altere o índice do elemento de matriz.
