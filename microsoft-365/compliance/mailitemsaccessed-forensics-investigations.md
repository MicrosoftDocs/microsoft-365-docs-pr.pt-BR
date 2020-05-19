---
title: Usar a Auditoria Avançada para investigar contas comprometidas
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use a ação de auditoria da caixa de correio MailItemsAccessed para executar investigações de perícia das contas de usuários comprometidas.
ms.openlocfilehash: 20c57f1d11af8fded15cc2fdf280414f7172ffd7
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262574"
---
# <a name="use-advanced-audit-to-investigate-compromised-accounts"></a>Usar a Auditoria Avançada para investigar contas comprometidas

Uma conta de usuário comprometida (também chamada de *tomada de controle da conta*) é um tipo de ataque quando um invasor obtém acesso a uma conta de usuário e opera como o usuário. Esses tipos de ataques, às vezes, causam mais danos do que o invasor planejou. Ao investigar contas de email comprometidas, você deve supor que mais dados de email foram comprometidos do que foi indicado ao rastrear a presença real do invasor. Dependendo do tipo de dados nas mensagens de email, você deve supor que as informações confidenciais foram comprometidas ou pagar multas regulatórias, a menos que seja possível provar que as informações confidenciais não tenham sido expostas. Por exemplo, as organizações regulamentadas pelo HIPAA terão de pagar multas significativas se houver evidências de que as informações de saúde do paciente (PHI) tenham sido expostas. Nesses casos, os invasores provavelmente não têm interesse nas PHI, mas as organizações ainda devem relatar violações de dados, a menos que possam provar o contrário.

Para ajudá-lo a investigar contas de email comprometidas, agora vamos auditar os acessos de dados de email por protocolos e clientes de email com a ação de auditoria da caixa de correio *MailItemsAccessed*. Essa nova ação de auditoria ajudará os investigadores a entender melhor as violações de dados de email e o ajudarão a identificar o escopo de comprometimentos em itens de email específicos que possam ter sido comprometidos. O objetivo de usar essa nova ação de auditoria é a defensibilidade de perícia para ajudar a afirmar que um trecho específico de dados de email não foi comprometido. Se um invasor obtiver acesso a um email específico, o Exchange Online auditará o evento mesmo que não haja indicação de que o item de email foi realmente lido.

## <a name="the-mailitemsaccessed-mailbox-auditing-action"></a>A ação de auditoria da caixa de correio MailItemsAccessed

A nova ação MailItemsAccessed faz parte da nova funcionalidade [Auditoria Avançada](advanced-audit.md). Faz parte da [auditoria de caixa de email do Exchange](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing#mailbox-auditing-actions) e é habilitada por padrão para os usuários que recebem uma licença do Office 365 ou Microsoft 365 E5 ou para organizações com uma assinatura complementar da Conformidade do Microsoft 365 E5.

A ação de auditoria da caixa de correio MailItemsAccessed abrange todos os protocolos de email: POP, IMAP, MAPI, EWS, Exchange ActiveSync e REST. Ela também aborda os dois tipos de acesso a email: *sincronização* e *vinculação*.

### <a name="auditing-sync-access"></a>Auditoria do acesso de sincronização

As operações de sincronização só são registradas quando uma caixa de correio é acessada por uma versão de área de trabalho do cliente do Outlook para Windows ou Mac. Durante a operação de sincronização, esses clientes geralmente baixam um grande conjunto de itens de email da nuvem para um computador local. O volume de auditoria para operações de sincronização é enorme. Então, em vez de gerar um registro de auditoria para item de email que é sincronizado, basta gerar um evento de auditoria para a pasta de email com os itens que foram sincronizados. Isso supõe que *todos* os itens de email na pasta sincronizada foram comprometidos. O tipo de acesso é registrado no campo OperationsProperties do registro de auditoria. 

Confira a etapa 2 na seção [Usar os registros de auditoria MailItemsAccessed para investigações de perícia](#use-mailitemsaccessed-audit-records-for-forensic-investigations) para obter um exemplo de como exibir o tipo de acesso de sincronização em um registro de auditoria.

### <a name="auditing-bind-access"></a>Auditoria do acesso de vinculação

Uma operação de vinculação é um acesso individual a uma mensagem de email. Para o acesso de vinculação, o internet-message-id das mensagens individuais será gravado no registro de auditoria. A ação de auditoria MailItemsAccessed registra as operações de vinculação e, em seguida, agrega-as em um único registro de auditoria. Todas as operações de vinculação que ocorrem em um intervalo de 2 minutos são agregadas em um único registro de auditoria no campo Pastas dentro da propriedade AuditData. Cada mensagem que foi acessada é identificada pelo internet-message-id. O número de operações de vinculação agregadas no registro é exibido no campo OperationCount na propriedade AuditData.

Confira a etapa 4 na seção [Usar os registros de auditoria MailItemsAccessed para investigações forenses](#use-mailitemsaccessed-audit-records-for-forensic-investigations) para obter um exemplo de como exibir o tipo de acesso de vinculação em um registro de auditoria.

### <a name="throttling-of-mailitemsaccessed-audit-records"></a>Limitação de registros de auditoria MailItemsAccessed

Se mais de 1.000 registros de auditoria MailItemsAccessed forem gerados em menos de 24 horas, o Exchange Online deixará de gerar registros de auditoria para a atividade MailItemsAccessed. Quando uma caixa de correio é limitada, a atividade MailItemsAccessed não será registrada por 24 horas após a limitação da caixa de correio. Se isso ocorrer, há uma possibilidade de que a caixa de correio tenha sido comprometida durante esse período. A gravação da atividade MailItemsAccessed será retomada após um período de 24 horas.  

Aqui estão alguns pontos para lembrar sobre a limitação:

- Menos de 1% de todas as caixas de correio no Exchange Online são limitadas.

- Quando uma caixa de correio é limitada, apenas os registros de auditoria para a atividade MailItemsAccessed não são auditados. Outras ações de auditoria da caixa de correio não são afetadas.

- As caixas de correio são limitadas apenas para operações de vinculação. Os registros de auditoria para operações de sincronização não são limitados.

- Se uma caixa de correio for limitada, você poderá supor que havia uma atividade MailItemsAccessed que não foi gravada no logs de auditoria.

Confira a etapa 1 na seção [Usar registros de auditoria MailItemsAccessed para investigações de perícia](#use-mailitemsaccessed-audit-records-for-forensic-investigations) para obter um exemplo de como exibir a propriedade IsThrottled em um registro de auditoria.

## <a name="use-mailitemsaccessed-audit-records-for-forensic-investigations"></a>Use os registros de auditoria MailItemsAccessed para investigações de perícia

A auditoria de caixa de correio gera registros de auditoria para acesso a mensagens de email para que você tenha certeza de que as mensagens de email não foram comprometidas. Por esse motivo, em situações em que não sabemos que alguns dados foram acessados, supomos que foram acessados gravando todas as atividades de acesso ao email.

Geralmente usa-se os registros de auditoria MailItemsAccessed para fins de perícia após uma violação de dados ser resolvida e o invasor ser removido. Para iniciar a investigação, identifique o conjunto de caixas de correio que foram comprometidas e determine o período de tempo em que o invasor teve acesso às caixas de correio em sua organização. Em seguida, você pode usar os cmdlets **Search-UnifiedAuditLog** ou **Search-MailboxAuditLog** no [PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) para pesquisar registros de auditoria que correspondem à violação de dados. 

Você pode executar um dos seguintes comandos para pesquisar registros de auditoria MailItemsAccessed:

**Log de auditoria unificada**

```powershell
Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000
```

**Log de auditoria de caixa de correio**

```powershell
Search-MailboxAuditLog -Identity <user> -StartDate 01/06/2020 -EndDate 01/20/2020 -Operations MailItemsAccessed -ResultSize 1000 -ShowDetails
```

> [!TIP]
> Uma grande diferença entre esses dois cmdlets é que você pode usar o cmdlet **Search-UnifiedAuditLog** para pesquisar em registros de auditoria atividades realizadas por um ou mais usuários. Isso ocorre porque *UserIds* é um parâmetro de vários valores. O cmdlet **Search-MailboxAuditLog** pesquisa o log de auditoria da caixa de correio para um único usuário.

Estas são as etapas para usar os registros de auditoria MailItemsAccessed para investigar uma invasão a um usuário comprometido. Cada etapa mostra a sintaxe de comando para os cmdlets **Search-UnifiedAuditLog** ou **Search-MailboxAuditLog**.

1. Verifique se a caixa de correio foi limitada. Caso tenha sido, isso significa que alguns registros de auditoria da caixa de correio não foram registrados. Caso nenhum registro de auditoria tenha o “IsThrottled é “Verdadeiro”, você deve supor que, por um período de 24 horas depois desse registro ser gerado, nenhum acesso à caixa de correio foi auditado e que todos os dados de email foram comprometidos.

   Para procurar registros MailItemsAccessed em que a caixa de correio foi limitada, execute o seguinte comando:

   **Log de auditoria unificada**
 
   ```powershell
   Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000 | Where {$_.AuditData -like '*"IsThrottled","Value":"True"*'} | FL
   ```

   **Log de auditoria de caixa de correio**

   ```powershell
   Search-MailboxAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -Identity <user> -Operations MailItemsAccessed -ResultSize 10000 -ShowDetails | Where {$_.OperationProperties -like "*IsThrottled:True*"} | FL
   ```

2. Verifique se há atividades de sincronização. Se um invasor usa um cliente de email para baixar mensagens em uma caixa de correio, ele pode desconectar o computador da Internet e acessar as mensagens localmente sem interagir com o servidor. Isso significa que a auditoria de caixa de correio não conseguiria auditar essas atividades.

   Para procurar registros MailItemsAccessed em que os itens de email foram acessados por uma operação de sincronização, execute o seguinte comando:

   **Log de auditoria unificada**

   ```powershell
   Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 02/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000 | Where {$_.AuditData -like '*"MailAccessType","Value":"Sync"*'} | FL
   ```

   **Log de auditoria de caixa de correio**

   ```powershell
   Search-MailboxAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -Identity <user> -Operations MailItemsAccessed -ResultSize 10000 -ShowDetails | Where {$_.OperationProperties -like "*MailAccessType:Sync*"} | FL
   ```

3. Verifique as atividades de sincronização para determinar se alguma delas ocorreu no mesmo contexto que aquele usado pelo invasor para acessar a caixa de correio. O contexto é identificado e diferenciado pelo endereço IP do computador cliente usado para acessar a caixa de correio e o protocolo de email. Para obter mais informações, confira a seção [Identificar os contextos de acesso de diferentes registros de auditoria](#identifying-the-access-contexts-of-different-audit-records).

   Use as propriedades listadas abaixo para investigar. Essas propriedades estão localizadas na propriedade AuditData ou OperationProperties. Se qualquer uma das sincronizações ocorrer no mesmo contexto da atividade do invasor, suponha que o invasor sincronizou todos os itens de email com seu cliente, o que significa que a caixa de correio inteira provavelmente foi comprometida.

   |Propriedade         | Descrição |
   |:---------------- | :----------|
   |ClientInfoString | Descreve protocolo, cliente (inclui versão)|
   |ClientIPAddress  | Endereço IP do computador cliente.|
   |SessionId        | O Session ID ajuda a diferenciar as ações do invasor versus as atividades diárias do usuário na mesma conta (no caso de uma conta comprometida)|
   |UserId           | UPN do usuário que está lendo a mensagem.|
   |||

4. Verifique as atividades de vinculação. Depois de realizar as etapas 2 e 3, você pode ter certeza de que todo o acesso a mensagens de email por meio do invasor será capturado nos registros de auditoria MailItemsAccessed que têm uma propriedade MailAccessType com um valor de “Vinculação”.

   Para procurar registros MailItemsAccessed em que os itens de email foram acessados por uma operação de vinculação, execute o seguinte comando.

   **Log de auditoria unificada**

   ```powershell
   Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000 | Where {$_.AuditData -like '*"MailAccessType","Value":"Bind"*'} | FL
   ```
 
   **Log de auditoria de caixa de correio**
   
   ```powershell
   Search-MailboxAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -Identity <user> -Operations MailItemsAccessed -ResultSize 10000 -ShowDetails | Where {$_.OperationProperties -like "*MailAccessType:Bind*"} | FL
   ```

   As mensagens de email que foram acessadas são identificadas pelo internet message Id. Você também pode verificar se algum registro de auditoria tem o mesmo contexto que o de outras atividades de invasor. Para obter mais informações, confira a seção [Identificar os contextos de acesso de diferentes registros de auditoria](#identifying-the-access-contexts-of-different-audit-records).
 
   Você pode usar os dados de auditoria para operações de vinculação de duas maneiras diferentes:

     - Acesse ou reúna todas as mensagens de email que o invasor acessou usando o internet-message-id para encontrá-las e, em seguida, verifique se alguma dessas mensagens contém informações confidenciais.

     - Use o internet-message-id para procurar registros de auditoria relacionados a um conjunto de mensagens de email potencialmente confidenciais. Isso será útil se você estiver preocupado somente com uma pequena quantidade de mensagens.

## <a name="filtering-of-duplicate-audit-records"></a>Filtragem de registros de auditoria duplicados

Os registros de auditoria duplicados para as mesma operações de vinculação que ocorrem dentro de uma hora entre si são filtrados para remover o ruído de auditoria. As operações de sincronização também são filtradas em intervalos de uma hora. A exceção para esse processo de eliminação de duplicação ocorre se, para o mesmo internet-message-id, qualquer uma das propriedades descritas na tabela a seguir for diferente. Se uma dessas propriedades for diferente em uma operação duplicada, um novo registro de auditoria será gerado. Esse processo é descrito em mais detalhes na próxima seção.

| Propriedade| Descrição|
|:--------|:---------|
|ClientIPAddress | O endereço IP do computador cliente.|
|ClientInfoString| O protocolo cliente, o cliente usado para acessar a caixa de correio.| 
|ParentFolder    | O caminho completo da pasta do item de email que foi acessado. |
|Logon_type      | O tipo de logon do usuário que realizou a ação. Os tipos de logon (e seu valor de enumeração correspondente) são Proprietário (0), Administrador (1), ou Delegado (2).|
|MailAccessType  | Se o acesso é uma operação de vinculação ou de sincronização.|
|MailboxUPN      | O UPN da caixa de correio na qual a mensagem que está sendo lida está localizada.|
|Usuário            | O UPN do usuário lendo a mensagem.|
|SessionId       | O Session Id ajuda a diferenciar as ações do invasor e as atividades diárias do usuário na mesma caixa de correio (no caso de uma conta comprometida). Para saber mais sobre sessões, confira [Contextualizar a atividade do invasor dentro de sessões do Exchange Online](https://techcommunity.microsoft.com/t5/exchange-team-blog/contextualizing-attacker-activity-within-sessions-in-exchange/ba-p/608801).|
||||

## <a name="identifying-the-access-contexts-of-different-audit-records"></a>Identificar os contextos de acesso de registros de auditoria diferentes

É comum que um invasor possa acessar uma caixa de correio ao mesmo tempo que o proprietário da caixa de correio está acessando. Para diferenciar o acesso do invasor do acesso do proprietário da caixa de correio, há propriedades de registro de auditoria que definem o contexto do acesso. Como explicado anteriormente, quando os valores dessas propriedades forem diferentes, mesmo quando a atividade ocorrer dentro do intervalo de agregação, os registros de auditoria separados serão gerados. No exemplo a seguir, há três registros de auditoria diferentes. Cada um é diferenciado pelas propriedades Session Id e ClientIPAddress. As mensagens que foram acessadas também são identificadas.

|Registro de auditoria 1  |Registro de auditoria 2  |Registro de auditoria 3|
|---------|---------|---------|
|ClientIPAddress**1**<br/>SessionId**2**|ClientIPAddress**2**<br/>SessionId**2**|ClientIPAddress**1**<br/>SessionId**3**|
|InternetMessageId**A**<br/>InternetMessageId**D**<br/>InternetMessageId**E**<br/>InternetMessageId**F**<br/>|InternetMessageId**A**<br/>InternetMessageId**C**|InternetMessageId**B** |
||||

Se alguma das propriedades listadas na tabela na [seção anterior](#filtering-of-duplicate-audit-records) forem diferentes, um registro de auditoria separado será gerado para controlar o novo contexto. Os acessos serão classificados nos registros de auditoria separados, dependendo do contexto em que a atividade ocorreu.

Por exemplo, em registros de auditoria mostrados na captura de tela a seguir, embora estejamos acessando o email do EWSEditor e OWA simultaneamente, a atividade de acesso é agrupada em registros de auditoria diferentes, dependendo do contexto no qual o acesso ocorreu. Neste caso, o contexto é definido pelo valores diferentes para a propriedade ClientInfoString.

![Registros de auditoria diferentes com base em contexto](../media/MailItemsAccessed4.png)
