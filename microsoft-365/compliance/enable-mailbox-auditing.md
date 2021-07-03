---
title: Gerenciar a auditoria de caixa de correio
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
ms.custom: seo-marvel-apr2020
description: O log de auditoria de caixa de correio está ligado por padrão Microsoft 365 (também chamado de auditoria de caixa de correio padrão ou auditoria de caixa de correio por padrão). Isso significa que determinadas ações executadas por proprietários, representantes e administradores de caixa de correio são registradas automaticamente em um log de auditoria de caixa de correio, onde você pode pesquisar atividades realizadas na caixa de correio.
ms.openlocfilehash: f74cb23a029d4710a19aeb18999169f6adc636a4
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287024"
---
# <a name="manage-mailbox-auditing"></a>Gerenciar a auditoria de caixa de correio

A partir de janeiro de 2019, a Microsoft está aprindo o log de auditoria de caixa de correio por padrão para todas as organizações. Isso significa que determinadas ações executadas por proprietários, representantes e administradores de caixa de correio são registradas automaticamente e os registros de auditoria de caixa de correio correspondentes estarão disponíveis quando você pesquisar por eles no log de auditoria de caixa de correio. Antes de a auditoria de caixa de correio ser ativada por padrão, você precisava habilita-la manualmente para cada caixa de correio de usuário em sua organização.

Aqui estão alguns benefícios da auditoria de caixa de correio por padrão:

- A auditoria é habilitada automaticamente quando você cria uma nova caixa de correio. Você não precisa habilita-lo manualmente para novos usuários.
- Você não precisa gerenciar as ações de caixa de correio auditadas. Um conjunto predefinido de ações de caixa de correio é auditado por padrão para cada tipo de logon (Administrador, Representante e Proprietário).
- Quando a Microsoft lança uma nova ação de caixa de correio, a ação pode ser adicionada automaticamente à lista de ações de caixa de correio auditadas por padrão (sujeita ao usuário que tem a licença apropriada). Isso significa que você não precisa monitorar adicionar novas ações em caixas de correio.
- Você tem uma política de auditoria de caixa de correio consistente em toda a sua organização (porque está auditando as mesmas ações para todas as caixas de correio).

> [!NOTE]
>
> - O importante a ser lembrado sobre a liberação da auditoria de caixa de correio por padrão é: você não precisa fazer nada para gerenciar a auditoria de caixa de correio. No entanto, para saber mais, personalize a auditoria de caixa de correio a partir das configurações padrão ou a desligue completamente, este artigo pode ajudá-lo.
> - Por padrão, somente os eventos de auditoria de caixa de correio para usuários do E5 estão disponíveis em pesquisas de log de auditoria no Centro de Conformidade & Segurança ou por meio da API de Atividade de Gerenciamento Office 365. Para obter mais informações, consulte [a seção Mais informações](#more-information) neste artigo.

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a>Verificar se a auditoria de caixa de correio está ativada por padrão

Para verificar se a auditoria de caixa de correio por padrão está 100% 100% 100%, execute o seguinte comando no [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):

```PowerShell
Get-OrganizationConfig | Format-List AuditDisabled
```

O valor **False** indica que a auditoria de caixa de correio ativada por padrão está habilitada para a organização. Isso por padrão substitui a configuração de auditoria de caixa de correio em caixas de correio específicas. Por exemplo, se a auditoria de caixa de correio estiver desabilitada para uma caixa de correio (a propriedade *AuditEnabled* é **False** na caixa de correio), as ações de caixa de correio padrão ainda serão auditadas para a caixa de correio, pois a auditoria de caixa de correio ativada por padrão está habilitada para a organização.

Para manter a auditoria de caixa de correio desabilitada para caixas de correio específicas, configure o bypass de auditoria de caixa de correio para o proprietário da caixa de correio e outros usuários que tenham sido delegados acesso à caixa de correio. Para obter mais informações, consulte a seção [Bypass mailbox audit logging](#bypass-mailbox-audit-logging) neste artigo.

> [!NOTE]
> Quando a auditoria de caixa de correio por padrão estiver ativa para a organização, a propriedade *AuditEnabled* para caixas de correio afetadas não será alterada de **False** para **True**. Em outras palavras, a auditoria de caixa de correio por padrão ignora a *propriedade AuditEnabled* em caixas de correio.

## <a name="supported-mailbox-types"></a>Tipos de caixa de correio com suporte

A tabela a seguir mostra os tipos de caixa de correio atualmente suportados pela auditoria de caixa de correio por padrão:

<br>

****

|Tipo de caixa de correio|Com suporte|
|---|:---:|
|Caixas de correio de usuário|![Marca de seleção](../media/checkmark.png)|
|Caixas de correio compartilhadas|![Marca de seleção](../media/checkmark.png)|
|Microsoft 365 Caixas de correio de grupo|![Marca de seleção](../media/checkmark.png)|
|Caixas de correio de recurso||
|Caixas de correio de pastas públicas||
|

## <a name="logon-types-and-mailbox-actions"></a>Tipos de logon e ações de caixa de correio

Os tipos de logon classificam o usuário que fez as ações auditadas na caixa de correio. A lista a seguir descreve os tipos de logon usados no log de auditoria de caixa de correio:

- **Proprietário**: o proprietário da caixa de correio (a conta associada à caixa de correio).
- **Delegar**:
  - Um usuário que tenha sido atribuído a permissão SendAs, SendOnBehalf ou FullAccess para outra caixa de correio.
  - Um administrador que foi atribuído a permissão FullAccess à caixa de correio de um usuário.
- **Admin**:
  - A caixa de correio é pesquisada com uma das seguintes ferramentas de Descoberta Eletrônico da Microsoft:
    - Pesquisa de conteúdo no Centro de Conformidade.
    - EDiscovery ou Advanced eDiscovery no Centro de Conformidade.
    - In-Place Descoberta eDiscovery no Exchange Online.
  - A caixa de correio é acessada usando o editor Microsoft Exchange Server MAPI.

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a>Ações de caixa de correio para caixas de correio de usuário e caixas de correio compartilhadas

A tabela a seguir descreve as ações de caixa de correio que estão disponíveis no log de auditoria de caixa de correio para caixas de correio de usuário e caixas de correio compartilhadas.

- Uma marca de seleção (![Marca de seleção](../media/checkmark.png)) indica que a ação da caixa de correio pode ser registrada no tipo de logon (nem todas as ações estão disponíveis para todos os tipos de logon).
- Um asterisco ( ) depois que a marca de seleção indica que a ação de caixa de correio é registrada por <sup>\*</sup> padrão para o tipo de logon.
- Lembre-se de que um administrador com permissão de Acesso Total a uma caixa de correio é considerado um representante.

<br>

****

|Ação de caixa de correio|Descrição|Administrador|Delegar|Proprietário|
|---|---|:---:|:---:|:---:|
|**AddFolderPermissions**|Embora esse valor seja aceito como uma ação de caixa de correio, ele já está incluído na ação **UpdateFolderPermissions** e não é auditado separadamente. Em outras palavras, não use esse valor.||||
|**ApplyRecord**|Um item é rotulado como um registro.|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|
|**Copy**|Uma mensagem foi copiada a outra pasta.|![Marca de seleção](../media/checkmark.png)|||
|**Create**|Um item foi criado na pasta Calendário, Contatos, Anotações ou Tarefas na caixa de correio (por exemplo, uma nova solicitação de reunião é criada). Criar, enviar ou receber uma mensagem não é auditada. Criar pastas de caixa de correio também não é uma ação auditada.|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)|
|**FolderBind**|Uma pasta da caixa de correio foi acessada. Esta ação também é registrada quando o administrador ou representante abrem a caixa de correio.<br/><br/> **Observação**: Os registros de auditoria para ações de vinculação de pastas executadas por representantes são consolidados. Um registro de auditoria é gerado para acesso de pasta individual em um período de 24 horas.|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)||
|**HardDelete**|Uma mensagem foi removida da pasta de Itens Recuperáveis.|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|
|**MailboxLogin**|O usuário entrou em sua caixa de correio.|||![Marca de seleção](../media/checkmark.png)|
|**MailItemsAccessed**|**Observação**: esse valor está disponível somente para usuários de assinatura de complemento de Conformidade E5 ou E5. Para obter mais informações, [consulte Set up Advanced Audit in Microsoft 365](set-up-advanced-audit.md). <p> Os dados de email são acessados por protocolos de email e clientes.|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|
|**MessageBind**|**Observação:** esse valor está disponível somente para usuários do E3 (usuários sem assinaturas de complemento de Conformidade E5 ou E5). <p> Uma mensagem foi exibida no painel de visualização ou aberta por um administrador.|![Marca de seleção](../media/checkmark.png)|||
|**ModifyFolderPermissions**|Embora esse valor seja aceito como uma ação de caixa de correio, ele já está incluído na ação **UpdateFolderPermissions** e não é auditado separadamente. Em outras palavras, não use esse valor.||||
|**Move**|Uma mensagem foi movida para outra pasta.|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|
|**MoveToDeletedItems**|Uma mensagem foi excluída e movida para a pasta Itens Excluídos.|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|
|**RecordDelete**|Um item rotulado como registro foi excluído de forma suave (movido para a pasta Itens Recuperáveis). Os itens rotulados como registros não podem ser excluídos permanentemente (excluídos da pasta Itens Recuperáveis).|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|
|**RemoveFolderPermissions**|Embora esse valor seja aceito como uma ação de caixa de correio, ele já está incluído na ação **UpdateFolderPermissions** e não é auditado separadamente. Em outras palavras, não use esse valor.||||
|**SearchQueryInitiated**|**Observação**: esse valor está disponível somente para usuários de assinatura de complemento de Conformidade E5 ou E5. Para obter mais informações, [consulte Set up Advanced Audit in Microsoft 365](set-up-advanced-audit.md). <p> Uma pessoa usa Outlook (Windows, Mac, iOS, Android ou Outlook na Web) ou o aplicativo email para Windows 10 para pesquisar itens em uma caixa de correio.|||![Marca de seleção](../media/checkmark.png)|
|**Send**|**Observação**: esse valor está disponível somente para usuários de assinatura de complemento de Conformidade E5 ou E5. Para obter mais informações, [consulte Set up Advanced Audit in Microsoft 365](set-up-advanced-audit.md). <p> O usuário envia uma mensagem de email, responde a uma mensagem de email ou encaminha uma mensagem de email.|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>||![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|
|**SendAs**|Uma mensagem foi enviada usando a permissão SendAs. Isto significa que outro usuário enviou a mensagem apesar de ter vindo do proprietário da caixa de correio.|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>||
|**SendOnBehalf**|Uma mensagem foi enviada usando a permissão SendOnBehalf. Isto significa que outro usuário enviou a mensagem em nome do proprietário da caixa de correio. A mensagem indica ao destinatário em nome de quem a mensagem foi enviada e quem na verdade enviou a mensagem.|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>||
|**SoftDelete**|Uma mensagem foi excluída permanentemente da pasta Itens Excluídos. Os itens excluídos temporariamente são movidos para a pasta Itens Recuperáveis.|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|
|**Atualizar**|Uma mensagem ou qualquer uma de suas propriedades foi alterada.|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|
|**UpdateCalendarDelegation**|Uma delegação de calendário foi atribuída a uma caixa de correio. A delegação de calendário concede a outra pessoa na mesma organização permissões para gerenciar o calendário do proprietário da caixa de correio.|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>||![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|
|**UpdateComplianceTag**|Um rótulo de retenção diferente é aplicado a um item de email (um item só pode ter um rótulo de retenção atribuído a ele).|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|![Marca de seleção](../media/checkmark.png)|
|**UpdateFolderPermissions**|Uma permissão da pasta foi alterada. As permissões de pasta controlam quais usuários da sua organização podem acessar as pastas em uma caixa de correio e as mensagens localizadas nessas pastas.|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|
|**UpdateInboxRules**|Uma regra de caixa de entrada foi adicionada, removida ou alterada. As regras de caixa de entrada são usadas para processar mensagens na Caixa de Entrada do usuário com base nas condições especificadas e tomar ações quando as condições de uma regra são atendidas, como mover uma mensagem para uma pasta especificada ou excluir uma mensagem.|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|
|

> [!IMPORTANT]
> Se você personalizou as ações de caixa  de correio para auditar qualquer tipo de logon antes que a auditoria de caixa de correio por padrão estivesse habilitada em sua organização, as configurações personalizadas serão preservadas na caixa de correio e não serão substituídas pelas ações de caixa de correio padrão, conforme descrito nesta seção. Para reverter as ações de caixa de correio de auditoria para seus valores padrão (o que você pode fazer a qualquer momento), consulte a seção [Restaurar](#restore-the-default-mailbox-actions) as ações de caixa de correio padrão mais adiante neste artigo.

### <a name="mailbox-actions-for-microsoft-365-group-mailboxes"></a>Ações de caixa de correio para Microsoft 365 de grupo

A auditoria de caixa de correio por padrão faz com que o log de auditoria de caixa de correio Microsoft 365 caixas de correio do Grupo, mas você não pode personalizar o que está sendo registrado (não é possível adicionar ou remover ações de caixa de correio que estão registradas para qualquer tipo de logon).

A tabela a seguir descreve as ações de caixa de correio que são registradas por padrão Microsoft 365 caixas de correio de grupo para cada tipo de logon.

Lembre-se de que um administrador com permissão de Acesso Total para uma Microsoft 365 de grupo é considerado um representante.

<br>

****

|Ação de caixa de correio|Descrição|Administrador|Delegar|Proprietário|
|---|---|:---:|:---:|:---:|
|**Create**|Criação de um Item de calendário. Criar, enviar ou receber uma mensagem não é auditada.|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>||
|**HardDelete**|Uma mensagem foi removida da pasta de Itens Recuperáveis.|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|
|**MoveToDeletedItems**|Uma mensagem foi excluída e movida para a pasta Itens Excluídos.|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|
|**SendAs**|Uma mensagem foi enviada usando a permissão SendAs.|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>||
|**SendOnBehalf**|Uma mensagem foi enviada usando a permissão SendOnBehalf.|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>||
|**SoftDelete**|Uma mensagem foi excluída permanentemente da pasta Itens Excluídos. Os itens excluídos temporariamente são movidos para a pasta Itens Recuperáveis.|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|
|**Atualizar**|Uma mensagem ou qualquer de sua propriedade foi alterada.|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|![Marca de seleção](../media/checkmark.png)<sup>\*</sup>|
|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a>Verifique se as ações de caixa de correio padrão estão sendo registradas para cada tipo de logon

A auditoria de caixa de correio por padrão adiciona uma nova *propriedade DefaultAuditSet* a todas as caixas de correio. O valor dessa propriedade indica se as ações de caixa de correio padrão (gerenciadas pela Microsoft) estão sendo auditadas na caixa de correio.

Para exibir o valor em caixas de correio de usuário ou caixas de correio compartilhadas, substitua pelo nome, alias, endereço de email ou nome principal do usuário (nome de usuário) da caixa de correio e execute o seguinte comando no \<MailboxIdentity\> Exchange Online PowerShell:

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

Para exibir o valor em Microsoft 365 de grupo, substitua pelo nome, alias ou endereço de email da caixa de correio compartilhada e execute o seguinte comando no \<MailboxIdentity\> Exchange Online PowerShell:

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

O valor `Admin, Delegate, Owner` indica:

- As ações de caixa de correio padrão para todos os três tipos de logon estão sendo auditadas. Esse é o único valor que você verá nas caixas de correio Microsoft 365 Group.
- Um administrador *não alterou* as ações de caixa de correio auditadas para qualquer tipo de logon em uma caixa de correio de usuário ou uma caixa de correio compartilhada. Observe que esse é o estado padrão depois que a auditoria de caixa de correio por padrão é inicialmente 1ada em sua organização.

Se um administrador tiver alterado as ações de caixa de correio auditadas para um tipo de logon (usando os parâmetros *AuditAdmin,* *AuditDelegate* ou *AuditOwner* no cmdlet **Set-Mailbox),** o valor da propriedade será diferente.

Por exemplo, o valor `Owner` da *propriedade DefaultAuditSet* em uma caixa de correio de usuário ou caixa de correio compartilhada indica:

- As ações de caixa de correio padrão para o proprietário da caixa de correio estão sendo auditadas.
- As ações de caixa de correio auditadas para os tipos de logon e foram `Delegate` `Admin` alteradas das ações padrão.

Um valor em branco para a *propriedade DefaultAuditSet* indica que as ações de caixa de correio para todos os três tipos de logon foram alteradas na caixa de correio do usuário ou em uma caixa de correio compartilhada.

Para obter mais informações, consulte a seção Alterar ou restaurar ações de caixa de correio [registradas](#change-or-restore-mailbox-actions-logged-by-default) por padrão neste artigo

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a>Exibir as ações de caixa de correio que estão sendo registradas em caixas de correio

Para ver as ações de caixa de correio que estão sendo registradas em caixas de correio de usuário ou caixas de correio compartilhadas, substitua pelo nome, alias, endereço de email ou nome principal do usuário (nome de usuário) da caixa de correio e execute um ou mais dos seguintes comandos no \<MailboxIdentity\> Exchange Online PowerShell.

> [!NOTE]
> Embora você possa adicionar a opção aos seguintes comandos Get-Mailbox para Microsoft 365 caixas de correio de grupo, não acredite nos valores `-GroupMailbox` retornados.  As ações padrão e [estáticas](#mailbox-actions-for-microsoft-365-group-mailboxes) de caixa de correio que são auditadas para Microsoft 365 caixas de correio de grupo são descritas na seção Ações de Caixa de Correio para caixas de correio Microsoft 365 Group anteriormente neste artigo.

#### <a name="owner-actions"></a>Ações do proprietário

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a>Ações delegar

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a>Ações de administrador

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a>Alterar ou restaurar ações de caixa de correio registradas por padrão

Como explicado anteriormente, um dos principais benefícios de ter a auditoria de caixa de correio por padrão é: você não precisa gerenciar as ações de caixas de correio que são auditadas. A Microsoft faz isso para você e adicionaremos automaticamente novas ações de caixa de correio a serem auditadas por padrão à medida que elas são lançadas.

No entanto, sua organização pode ser necessária para auditar um conjunto diferente de ações de caixa de correio para caixas de correio de usuário e caixas de correio compartilhadas. Os procedimentos nesta seção mostram como alterar as ações de caixa de correio auditadas para cada tipo de logon e como reverter para as ações padrão gerenciadas pela Microsoft.

> [!IMPORTANT]
> Se você usar os procedimentos a seguir para personalizar as ações de caixa de correio que estão registradas em caixas de correio de usuário ou caixas de correio compartilhadas, quaisquer novas ações de caixa de correio padrão lançadas pela Microsoft não serão auditadas automaticamente nessas caixas de correio. Você precisará adicionar manualmente qualquer nova ação de caixa de correio à sua lista personalizada de ações.

### <a name="change-the-mailbox-actions-to-audit"></a>Alterar as ações de caixa de correio para auditoria

Você pode usar os parâmetros *AuditAdmin,* *AuditDelegate* ou *AuditOwner* no cmdlet **Set-Mailbox** para alterar as ações de caixa de correio auditadas para caixas de correio de usuário e caixas de correio compartilhadas (ações auditadas para caixas de correio de grupo Microsoft 365 não podem ser personalizadas).

Você pode usar dois métodos diferentes para especificar as ações de caixa de correio:

- *Substitua* (substitua) as ações de caixa de correio existentes usando esta sintaxe: `action1,action2,...actionN` .
- *Adicione ou remova ações* de caixa de correio sem afetar outros valores existentes usando esta sintaxe: `@{Add="action1","action2",..."actionN"}` ou `@{Remove="action1","action2",..."actionN"}` .

Este exemplo altera as ações de caixa de correio de administrador para a caixa de correio chamada "Gabriela Laureano" ao sobrescrever as ações padrão com SoftDelete e HardDelete.

```PowerShell
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

Este exemplo adiciona a ação proprietário MailboxLogin à caixa de correio laura@contoso.onmicrosoft.com.

```PowerShell
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

Este exemplo remove a ação delegada MoveToDeletedItems para a caixa de correio discussão de equipe.

```PowerShell
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

Independentemente do método usado, personalizar as ações de caixa de correio auditadas em caixas de correio de usuário ou caixas de correio compartilhadas tem os seguintes resultados:

- Para o tipo de logon personalizado, as ações de caixa de correio auditadas não são mais gerenciadas pela Microsoft.
- O tipo de logon personalizado não é mais exibido no valor da propriedade *DefaultAuditSet* para a caixa de correio conforme [descrito anteriormente](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type).

### <a name="restore-the-default-mailbox-actions"></a>Restaurar as ações de caixa de correio padrão

> [!NOTE]
> Os procedimentos a seguir não se aplicam Microsoft 365 caixas de correio de grupo (elas estão limitadas às ações padrão conforme descrito [aqui](#mailbox-actions-for-microsoft-365-group-mailboxes)).

Se você personalização das ações de caixa de correio auditadas em uma caixa de correio de usuário ou em uma caixa de correio compartilhada, poderá restaurar as ações de caixa de correio padrão para um ou todos os tipos de logon usando esta sintaxe:

```PowerShell
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

Você pode especificar vários *valores DefaultAuditSet* separados por vírgulas

Este exemplo restaura as ações de caixa de correio auditadas padrão para todos os tipos de logon na caixa de correio mark@contoso.onmicrosoft.com.

```PowerShell
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

Este exemplo restaura as ações de caixa de correio auditadas padrão para o tipo de logon administrador na caixa de correio chris@contoso.onmicrosoft.com, mas deixa as ações de caixa de correio auditadas personalizadas para os tipos de logon Delegar e Proprietário.

```PowerShell
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

Restaurar as ações de caixa de correio auditadas padrão para um tipo de logon tem os seguintes resultados:

- A lista atual de ações de caixa de correio é substituída pelas ações de caixa de correio padrão para o tipo de logon.
- Todas as novas ações de caixa de correio lançadas pela Microsoft são adicionadas automaticamente à lista de ações auditadas para o tipo de logon.
- O *valor da propriedade DefaultAuditSet* para a caixa de correio é atualizado para incluir o tipo de logon restaurado.

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a>Desativar a auditoria de caixa de correio por padrão para sua organização

Você pode desativar a auditoria de caixa de correio por padrão para toda a sua organização executando o seguinte comando no Exchange Online PowerShell:

```PowerShell
Set-OrganizationConfig -AuditDisabled $true
```

Desligar a auditoria de caixa de correio por padrão tem os seguintes resultados:

- A auditoria de caixa de correio está desabilitada para sua organização.
- Desde o momento em que você desabilitou a auditoria de caixa de correio por padrão, nenhuma ação de caixa de correio é auditada, mesmo que a auditoria seja habilitada em uma caixa de correio (a propriedade *AuditEnabled* na caixa de correio é **True**).
- A auditoria de caixa de correio não está habilitada para novas caixas de correio e a definição da propriedade *AuditEnabled* em uma caixa de correio nova ou existente como **True** será ignorada.
- Todas as configurações de associação de bypass de auditoria de caixa de correio (configuradas usando o cmdlet **Set-MailboxAuditBypassAssociation)** são ignoradas.
- Os registros de auditoria de caixa de correio existentes são mantidos até que o limite de idade do log de auditoria para o registro expire.

### <a name="turn-on-mailbox-auditing-on-by-default"></a>Ativar a auditoria de caixa de correio por padrão

Para ativar novamente a auditoria de caixa de correio para sua organização, execute o seguinte comando Exchange Online PowerShell:

```PowerShell
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a>Ignorar log de auditoria de caixa de correio

Atualmente, não é possível desabilitar a auditoria de caixas de correio para específicas caixas de correio quando a auditoria de caixas de correio estiver ativada por padrão na organização. Por exemplo, a definição da propriedade de caixa de *correio AuditEnabled* **como False** é ignorada.

No entanto, você ainda pode usar o cmdlet **Set-MailboxAuditBypassAssociation** no Exchange Online PowerShell para impedir que todas as ações de caixa de correio dos usuários especificados sejam registradas, independentemente de onde as ações ocorrem.  Por exemplo:

- As ações do proprietário da caixa de correio executadas pelos usuários ignorados não são registradas.
- As ações de representante executadas pelos usuários ignorados em caixas de correio de outros usuários (incluindo caixas de correio compartilhadas) não são registradas.
- As ações de administrador executadas pelos usuários ignorados não são registradas.

Para ignorar o log de auditoria de caixa de correio de um usuário específico, substitua pelo nome, endereço de email, alias ou nome principal do usuário (nome de usuário) do usuário e execute \<MailboxIdentity\> o seguinte comando:

```PowerShell
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

Para verificar se a auditoria é ignorada para o usuário especificado, execute o seguinte comando:

```PowerShell
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

O valor **True** indica que o log de auditoria de caixa de correio é ignorado para o usuário.

## <a name="more-information"></a>Mais informações

- Embora [o](search-the-audit-log-in-security-and-compliance.md) log de auditoria de caixa de correio ativado por padrão seja habilitado para todas as organizações, somente os usuários com licenças do E5 retornarão eventos de log de auditoria de caixa de correio em pesquisas de log de auditoria no Centro de Conformidade & Segurança ou por meio da API de Atividade de Gerenciamento [do Office 365](/office/office-365-management-api/office-365-management-activity-api-reference) por padrão . 

  Para recuperar entradas de log de auditoria de caixa de correio para usuários sem licenças E5, você pode:

  - Habilitar manualmente a auditoria de caixa de correio em caixas de correio individuais (execute o comando, `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true` ). Depois de fazer isso, você pode usar pesquisas de log de auditoria no Centro de Conformidade & Segurança ou por meio da API de Atividade de Gerenciamento Office 365 Gerenciamento.

    > [!NOTE]
    > Se a auditoria de caixa de correio já estiver habilitada na caixa de correio, mas suas pesquisas não retornarem resultados, altere o valor do parâmetro _AuditEnabled_ para e volte `$false` para `$true` .

  - Use os seguintes cmdlets no Exchange Online PowerShell:
    - [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) para pesquisar o log de auditoria de caixa de correio para usuários específicos.
    - [New-MailboxAuditLogSearch](/powershell/module/exchange/new-mailboxauditlogsearch) para pesquisar o log de auditoria de caixa de correio para usuários específicos e para ter os resultados enviados por email para destinatários especificados.

  - Use o Exchange de administração (EAC) no Exchange Online para fazer as seguintes ações:
    - [Exportar logs de auditoria de caixas de correio](/Exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs)
    - [Executar relatório de acesso à caixa de correio de um não proprietário](/Exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report)

- Por padrão, os registros de log de auditoria de caixa de correio são mantidos por 90 dias antes de ser excluídos. Você pode alterar o limite de idade para registros de log de auditoria usando o parâmetro *AuditLogAgeLimit* no cmdlet **Set-Mailbox** no Exchange Online PowerShell. No entanto, aumentar esse valor não permite que você pesquise eventos com mais de 90 dias no log de auditoria.

  Se você aumentar o limite de idade, precisará usar o cmdlet [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) no Exchange Online PowerShell para pesquisar o log de auditoria de caixa de correio do usuário em busca de registros com mais de 90 dias.

- Se você alterou a propriedade *AuditLogAgeLimit* para uma caixa de correio antes de a auditoria de caixa de correio estar 100% 2016 2016 2016, o limite de idade do log de auditoria existente da caixa de correio não será alterado. Em outras palavras, a auditoria de caixa de correio por padrão não afeta o limite de idade atual para registros de auditoria de caixa de correio.

- Para alterar o *valor AuditLogAgeLimit* em uma caixa de correio Microsoft 365 Group, você precisa incluir a opção no `-GroupMailbox` comando **Set-Mailbox.**

- Os registros de log de auditoria de caixa de correio são armazenados em uma subpasta (denominada *Auditorias*) na pasta Itens Recuperáveis na caixa de correio de cada usuário. Lembre-se das seguintes coisas sobre os registros de auditoria de caixa de correio e a pasta Itens Recuperáveis:

  - Os registros de auditoria de caixa de correio contam com a cota de armazenamento da pasta Itens Recuperáveis, que é de 30 GB por padrão (a cota de aviso é de 20 GB). A cota de armazenamento é aumentada automaticamente para 100 GB (com uma cota de aviso de 90 GB) quando:
    - Uma espera é colocada em uma caixa de correio.
    - A caixa de correio é atribuída a uma política de retenção no Centro de Conformidade.

  - Os registros de auditoria de caixa de correio também contam com o limite [de pasta para a pasta Itens Recuperáveis.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits) No máximo 3 milhões de itens (registros de auditoria) podem ser armazenados na subpasta Auditorias.

    > [!NOTE]
    > É improvável que a auditoria de caixa de correio por padrão impacte a cota de armazenamento ou o limite de pasta para a pasta Itens Recuperáveis.

    - Você pode executar o seguinte comando no Exchange Online PowerShell para exibir o tamanho e o número de itens na subpasta Auditorias na pasta Itens Recuperáveis:

      ```PowerShell
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - Você não pode acessar diretamente um registro de log de auditoria na pasta Itens Recuperáveis; em vez disso, use o cmdlet **Search-MailboxAuditLog** ou pesquise o log de auditoria para encontrar e exibir registros de auditoria de caixa de correio.

- Se uma caixa de correio for colocada em retenção ou atribuída a uma política de retenção no Centro de Conformidade, os registros de log de auditoria ainda serão mantidos pela duração definida pela propriedade *AuditLogAgeLimit* da caixa de correio (90 dias por padrão). Para manter os registros de log de auditoria por mais tempo para caixas de correio em espera, você precisa aumentar o valor *AuditLogAgeLimit* da caixa de correio.

- Em um ambiente de várias regiões, não há suporte para a auditoria de caixas de correio de várias regiões. Por exemplo, se um usuário receber permissões para acessar uma caixa de correio compartilhada em um local geográfico diferente, as ações de caixa de correio executadas por esse usuário não serão registradas no log de auditoria da caixa de correio da caixa de correio compartilhada.
