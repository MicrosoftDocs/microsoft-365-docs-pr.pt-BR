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
description: O registro em log de auditoria de caixa de correio é ativado por padrão no Office 365 (também chamado de auditoria de caixa de correio padrão ou de caixa de correio ativada por padrão). Isso significa que determinadas ações executadas por proprietários, representantes e administradores de caixa de correio são automaticamente registradas em um log de auditoria de caixa de correio, onde você pode pesquisar atividades realizadas na caixa de correio.
ms.openlocfilehash: 1c1d9996ef72c686a6a543a30bcb34e265cc79cc
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42074708"
---
# <a name="manage-mailbox-auditing"></a>Gerenciar a auditoria de caixa de correio

A partir de janeiro de 2019, a Microsoft está ativando o log de auditoria de caixa de correio por padrão para todas as organizações do Office 365. Isso significa que determinadas ações executadas por proprietários, representantes e administradores de caixa de correio são automaticamente registradas, e os registros de auditoria de caixa de correio correspondentes estarão disponíveis quando você procurá-los no log de auditoria de caixa de correio. Antes de a auditoria da caixa de correio ser ativada por padrão, você precisava habilitá-la manualmente para cada caixa de correio de usuário em sua organização.

Estes são alguns benefícios da auditoria de caixa de correio ativada por padrão:

- A auditoria é automaticamente habilitada quando você cria uma nova caixa de correio. Você não precisa habilitá-lo manualmente para novos usuários.

- Você não precisa gerenciar as ações da caixa de correio que são auditadas. Um conjunto predefinido de ações de caixa de correio é auditado por padrão para cada tipo de logon (administrador, representante e proprietário).

- Quando a Microsoft lança uma nova ação de caixa de correio (especialmente ações que ajudam a proteger sua organização e a ajudar com investigações jurídicas), a ação é automaticamente adicionada à lista de ações de caixa de correio que são auditadas por padrão. Isso significa que você não precisa monitorar a adição de novas ações em caixas de correio.

- Você tem uma política de auditoria de caixa de correio consistente em sua organização (pois você está auditando as mesmas ações para todas as caixas de correio).

> [!NOTE]
>• O importante a ser lembrado sobre o lançamento da auditoria de caixa de correio por padrão é: não é necessário fazer nada para gerenciar a auditoria de caixa de correio. No entanto, para saber mais, personalizar a auditoria de caixa de correio nas configurações padrão ou desativá-la completamente, este tópico pode ajudá-lo. <br><br>• Por padrão, somente eventos de auditoria de caixa de correio para usuários do E5 estão disponíveis em pesquisas de log de auditoria no centro de conformidade & segurança ou por meio da API de atividade de gerenciamento do Office 365. Para obter mais informações, consulte a seção [mais informações](#more-information) neste tópico.

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a>Verificar se a auditoria de caixa de correio está ativada por padrão

Para verificar se a auditoria de caixa de correio ativa por padrão está ativada para sua organização, execute o seguinte comando no [PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell):

```PowerShell
Get-OrganizationConfig | Format-List AuditDisabled
```

O valor **false** indica que a auditoria da caixa de correio ativa por padrão é habilitada para a organização. Esse valor de organização ativado por padrão substitui a configuração de auditoria de caixa de correio em caixas de correio específicas. Por exemplo, se a auditoria de caixa de correio estiver desabilitada para uma caixa de correio (a propriedade *AuditEnabled* for **false** na caixa de correio), as ações de caixa de correio padrão ainda serão auditadas para a caixa de correio, pois a auditoria de caixa de correio ativa por padrão para a organização.

Para manter a auditoria de caixa de correio desabilitada para caixas de correio específicas, configure o bypass de auditoria de caixa de correio para o proprietário da caixa de correio e outros usuários com acesso delegado à caixa de correio. Para obter mais informações, consulte a seção [ignorar o log de auditoria de caixa de correio](#bypass-mailbox-audit-logging) neste tópico.

> [!NOTE]
> Quando a auditoria de caixa de correio ativa por padrão é ativada para a organização, a propriedade *AuditEnabled* para caixas de correio afetadas não será alterada de **false** para **true**. Em outras palavras, a auditoria de caixa de correio ativada por padrão ignora a propriedade *AuditEnabled* nas caixas de correio.

## <a name="supported-mailbox-types"></a>Tipos de caixa de correio suportados

A tabela a seguir mostra os tipos de caixa de correio com suporte no momento pela auditoria de caixa de correio ativada por padrão:

|**Tipo de caixa de correio**|**Com suporte**|**Sem suporte**|
|:---------|:---------:|:---------:|
|Caixas de correio de usuário|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|Caixas de correio compartilhadas|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|Caixas de correio de grupo do Office 365|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|Caixas de correio de recurso||![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Caixas de correio de pastas públicas||![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|

## <a name="logon-types-and-mailbox-actions"></a>Tipos de logon e ações de caixa de correio

Os tipos de logon classificam o usuário que fazia as ações auditadas na caixa de correio. A lista a seguir descreve os tipos de logon usados no log de auditoria de caixa de correio:

- **Proprietário**: o proprietário da caixa de correio (a conta associada à caixa de correio).

- **Delegate**:

  - Um usuário que foi atribuído à permissão SendAs, SendOnBehalf ou FullAccess a outra caixa de correio.

  - Um administrador que recebeu a permissão FullAccess para a caixa de correio de um usuário.

- **Administrador**:

  - A caixa de correio é pesquisada com uma das seguintes ferramentas de descoberta eletrônica da Microsoft:

    - Pesquisa de conteúdo no centro de conformidade.

    - Descoberta eletrônica ou descoberta eletrônica avançada no centro de conformidade.

    - Descoberta eletrônica in-loco no Exchange Online.

  - A caixa de correio é acessada usando o editor MAPI do Microsoft Exchange Server.

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a>Ações de caixa de correio para caixas de correio de usuário e caixas de correio compartilhadas

A tabela a seguir descreve as ações de caixa de correio disponíveis no log de auditoria de caixa de correio para caixas de correio de usuário e caixas de correio compartilhadas.

- Uma marca de seleção ( ![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)) indica que a ação de caixa de correio pode ser registrada para o tipo de logon (nem todas as ações estão disponíveis para todos os tipos de logon).

- Um asterisco ( <sup>\*</sup> ) após a marca de seleção indica que a ação de caixa de correio é registrada por padrão para o tipo de logon.

- Lembre-se de que um administrador com permissão de acesso completo para uma caixa de correio é considerado um representante.

|**Ação de caixa de correio**|**Descrição**|**Admin**|**Delegar**|**Owner**|
|:---------|:---------|:---------:|:---------:|:---------:|
|**AddFolderPermissions**|**Observação**: embora esse valor seja aceito como uma ação de caixa de correio, ele já está incluído na ação **UpdateFolderPermissions** e não é auditado separadamente. Em outras palavras, não use esse valor.||||
|**ApplyRecord**|Um item é rotulado como um registro.|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**Copy**|Uma mensagem foi copiada a outra pasta.|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|**Create**|Um item foi criado na pasta calendário, contatos, anotações ou tarefas na caixa de correio (por exemplo, uma nova solicitação de reunião é criada). Observe que a criação, o envio ou o recebimento de uma mensagem não é auditado. Criar pastas de caixa de correio também não é uma ação auditada.|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**Padrão**||![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**FolderBind**|Uma pasta da caixa de correio foi acessada. Esta ação também é registrada quando o administrador ou representante abrem a caixa de correio.<br/><br/> **Observação**: os registros de auditoria das ações de associação de pasta executadas pelos representantes são consolidados. Um registro de auditoria é gerado para o acesso a pastas individuais no período de 24 horas.|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|**HardDelete**|Uma mensagem foi removida da pasta de Itens Recuperáveis.|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**MailItemsAccessed**|Os dados de email são acessados por protocolos e clientes de email. Esse valor só está disponível para usuários de assinatura de complemento de conformidade E5 ou e5. Para obter detalhes, consulte [eventos de auditoria de alto valor](https://docs.microsoft.com/microsoft-365/compliance/advanced-audit#high-value-audit-events)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**MailboxLogin**|O usuário entrou em sua caixa de correio. |||![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**MessageBind**|Uma mensagem foi exibida no painel de visualização ou foi aberta por um administrador. **Observação**: embora esse valor seja aceito como uma ação de caixa de correio, essas ações não são registradas.|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|**ModifyFolderPermissions**|**Observação**: embora esse valor seja aceito como uma ação de caixa de correio, ele já está incluído na ação **UpdateFolderPermissions** e não é auditado separadamente. Em outras palavras, não use esse valor.||||
|**Move**|Uma mensagem foi movida para outra pasta.|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**MoveToDeletedItems**|Uma mensagem foi excluída e movida para a pasta Itens Excluídos.|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**RecordDelete**|Um item rotulado como um registro foi excluído por software (movido para a pasta itens recuperáveis). Os itens rotulados como registros não podem ser excluídos permanentemente (removidos da pasta itens recuperáveis).|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**RemoveFolderPermissions**|**Observação**: embora esse valor seja aceito como uma ação de caixa de correio, ele já está incluído na ação **UpdateFolderPermissions** e não é auditado separadamente. Em outras palavras, não use esse valor.||||
|**SendAs**|Uma mensagem foi enviada usando a permissão SendAs. Isto significa que outro usuário enviou a mensagem apesar de ter vindo do proprietário da caixa de correio.|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SendOnBehalf**|Uma mensagem foi enviada usando a permissão SendOnBehalf. Isto significa que outro usuário enviou a mensagem em nome do proprietário da caixa de correio. A mensagem indica ao destinatário em nome de quem a mensagem foi enviada e quem na verdade enviou a mensagem.|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SoftDelete**|Uma mensagem foi excluída permanentemente da pasta Itens Excluídos. Os itens excluídos temporariamente são movidos para a pasta Itens Recuperáveis.|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**Update**|Uma mensagem ou suas propriedades foram alteradas.|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**UpdateCalendarDelegation**|Uma delegação de calendário foi atribuída a uma caixa de correio. A delegação de calendário concede a outra pessoa na mesma organização permissões para gerenciar o calendário do proprietário da caixa de correio.|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**UpdateComplianceTag**|Um rótulo de retenção diferente é aplicado a um item de email (um item pode ter apenas um rótulo de retenção atribuído a ele).|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**UpdateFolderPermissions**|Uma permissão da pasta foi alterada. As permissões de pasta controlam quais usuários da sua organização podem acessar as pastas em uma caixa de correio e as mensagens localizadas nessas pastas.|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**UpdateInboxRules**|Uma regra de caixa de entrada foi adicionada, removida ou alterada. As regras de caixa de entrada são usadas para processar mensagens na caixa de entrada do usuário com base nas condições especificadas e realizar ações quando as condições de uma regra são atendidas, como mover uma mensagem para uma pasta especificada ou excluir uma mensagem.|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|

> [!IMPORTANT]
> Se você personalizou as ações da caixa de correio para auditar qualquer tipo de logon *antes* de a auditoria da caixa de correio ativada por padrão na organização, as configurações personalizadas são preservadas na caixa de correio e não são sobrescritas pelas ações de caixa de correio padrão, conforme descrito nesta seção. Para reverter as ações de caixa de correio de auditoria para seus valores padrão (que você pode fazer a qualquer momento), consulte a seção [restaurar as ações de caixa de correio padrão](#restore-the-default-mailbox-actions) mais adiante neste tópico.

### <a name="mailbox-actions-for-office-365-group-mailboxes"></a>Ações de caixa de correio para caixas de correio de grupo do Office 365

A auditoria de caixa de correio ativada por padrão traz o log de auditoria de caixa de correio para as caixas de correio de grupo do Office 365, mas não é possível personalizar o que está sendo registrado (não é possível adicionar ou remover ações de caixa de correio registradas para qualquer tipo de logon

A tabela a seguir descreve as ações de caixa de correio registradas por padrão em caixas de correio de grupo do Office 365 para cada tipo de logon.

Lembre-se de que um administrador com permissão de acesso completo para uma caixa de correio de grupo do Office 365 é considerado um representante.

|**Ação de caixa de correio**|**Descrição**|**Admin**|**Delegar**|**Owner**|
|:---------|:---------|:---------:|:---------:|:---------:|
|**Create**|Criação de um item de calendário. Observe que a criação, o envio ou o recebimento de uma mensagem não é auditado.|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**HardDelete**|Uma mensagem foi removida da pasta de Itens Recuperáveis.|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**MoveToDeletedItems**|Uma mensagem foi excluída e movida para a pasta Itens Excluídos.|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**SendAs**|Uma mensagem foi enviada usando a permissão SendAs.|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SendOnBehalf**|Uma mensagem foi enviada usando a permissão SendOnBehalf. |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SoftDelete**|Uma mensagem foi excluída permanentemente da pasta Itens Excluídos. Os itens excluídos temporariamente são movidos para a pasta Itens Recuperáveis.|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**Update**|Uma mensagem ou suas propriedades foram alteradas.|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a>Verifique se as ações de caixa de correio padrão estão sendo registradas para cada tipo de logon

A auditoria de caixa de correio ativada por padrões adiciona uma nova propriedade *Defaultauditset* a todas as caixas de correio. O valor dessa propriedade indica se as ações de caixa de correio padrão (gerenciadas pela Microsoft) estão sendo auditadas na caixa de correio.

Para exibir o valor em caixas de correio de usuário ou caixas de correio \<compartilhadas, substitua mailboxidentity pela\> pelo nome, alias, endereço de email ou nome de usuário principal (username) da caixa de correio e execute o seguinte comando no PowerShell do Exchange Online:

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

Para exibir o valor nas caixas de correio de grupo do Office \<365\> , substitua mailboxidentity pela pelo nome, alias ou endereço de email da caixa de correio compartilhada e execute o seguinte comando no PowerShell do Exchange Online:

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

O valor `Admin, Delegate, Owner` indica:

- As ações de caixa de correio padrão para todos os três tipos de logon estão sendo auditadas. Observe que esse é o único valor que você verá nas caixas de correio de grupo do Office 365.

- Um administrador *não* alterou as ações de caixa de correio auditadas para qualquer tipo de logon na caixa de correio de um usuário ou em uma caixa de correio compartilhada. Observação Este é o estado padrão após a auditoria da caixa de correio ativada por padrão na sua organização.

Se um administrador já tiver alterado as ações de caixa de correio que são auditadas para um tipo de logon (usando os parâmetros *AuditAdmin*, *AuditDelegate*ou *AuditOwner* no cmdlet **Set-Mailbox** ), o valor da propriedade será diferente.

Por exemplo, o valor `Owner` da propriedade *defaultauditset* em uma caixa de correio de usuário ou caixa de correio compartilhada indica:

- As ações de caixa de correio padrão para o proprietário da caixa de correio estão sendo auditadas.

- As ações de caixa de correio auditadas para os `Delegate` tipos de logon e `Admin` foram alteradas das ações padrão.

Um valor em branco para a propriedade *Defaultauditset* indica que as ações da caixa de correio para todos os três tipos de logon foram alteradas na caixa de correio do usuário ou em uma caixa de correio compartilhada.

Para obter mais informações, consulte a seção [alterar ou restaurar ações de caixa de correio registradas por padrão](#change-or-restore-mailbox-actions-logged-by-default) neste tópico

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a>Exibir as ações de caixa de correio que estão sendo registradas nas caixas de correio

Para ver as ações de caixa de correio que estão sendo registradas no momento em caixas de correio de \<usuários\> ou caixas de correio compartilhadas, substitua mailboxidentity pela pelo nome, alias, endereço de email ou nome UPN da caixa de correio e execute um ou mais dos seguintes comandos no PowerShell do Exchange Online.

> [!NOTE]
> Embora seja possível adicionar a `-GroupMailbox` opção aos seguintes comandos **Get-Mailbox** para caixas de correio de grupo do Office 365, não acredite nos valores retornados. As ações de caixa de correio padrão e estática que são auditadas para caixas de correio de grupo do Office 365 são descritas na seção [ações de caixa de correio para caixas de correio de grupo do office 365](#mailbox-actions-for-office-365-group-mailboxes) anteriormente neste tópico.

#### <a name="owner-actions"></a>Ações do proprietário

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a>Ações de representante

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a>Ações de administrador

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a>Alterar ou restaurar ações de caixa de correio registradas por padrão

Como explicado anteriormente, um dos principais benefícios de ter a auditoria de caixa de correio ativada por padrão é: não é necessário gerenciar as ações de caixas de correio que são auditadas. A Microsoft faz isso para você e adicionaremos automaticamente novas ações de caixa de correio para serem auditadas por padrão à medida que elas forem liberadas.

No entanto, sua organização pode ser necessária para auditar um conjunto diferente de ações de caixa de correio para caixas de correio de usuário e caixas de correio compartilhadas. Os procedimentos desta seção mostram como alterar as ações de caixa de correio que são auditadas para cada tipo de logon e como reverter para as ações padrão gerenciadas pela Microsoft.

> [!IMPORTANT]
> Se você usar os procedimentos a seguir para personalizar as ações de caixa de correio registradas nas caixas de correio do usuário ou caixas de correio compartilhadas, qualquer nova ação de caixa de correio padrão liberada pela Microsoft não será auditada automaticamente nessas caixas de correio. Você precisará adicionar manualmente qualquer ação de caixa de correio nova à sua lista personalizada de ações.

### <a name="change-the-mailbox-actions-to-audit"></a>Alterar as ações da caixa de correio para auditoria

Você pode usar os parâmetros *AuditAdmin*, *AuditDelegate*ou *AuditOwner* no cmdlet **Set-Mailbox** para alterar as ações de caixa de correio que são auditadas para caixas de correio de usuário e caixas de correio compartilhadas (ações auditadas para caixas de correio de grupo do Office 365 não podem ser personalizadas).

Você pode usar dois métodos diferentes para especificar as ações da caixa de correio:

- *Substitua* (substitua) as ações de caixa de correio existentes usando esta `action1,action2,...actionN`sintaxe:.

- *Adicionar ou remover* ações de caixa de correio sem afetar outros valores existentes usando esta `@{Add="action1","action2",..."actionN"}` sintaxe `@{Remove="action1","action2",..."actionN"}`: ou.

Este exemplo altera as ações da caixa de correio de administrador da caixa de correio chamada "Gabriela Laureano" substituindo as ações padrão por SoftDelete e HardDelete.

```PowerShell
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

Este exemplo adiciona a ação de proprietário MailboxLogin à caixa de correio laura@contoso.onmicrosoft.com.

```PowerShell
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

Este exemplo remove a ação de representante MoveToDeletedItems para a caixa de correio de discussão em equipe.

```PowerShell
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

Independentemente do método usado, a personalização das ações de caixa de correio auditadas nas caixas de correio do usuário ou nas caixas de correio compartilhadas tem os seguintes resultados:

- Para o tipo de logon que você personalizou, as ações de caixa de correio auditadas não são mais gerenciadas pela Microsoft.

- O tipo de logon que você personalizou não é mais exibido no valor da propriedade *Defaultauditset* da caixa de correio, como [descrito anteriormente](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type).

### <a name="restore-the-default-mailbox-actions"></a>Restaurar as ações de caixa de correio padrão

Se você personalizou as ações de caixa de correio que são auditadas em uma caixa de correio de usuário ou em uma caixa de correio compartilhada, é possível restaurar as ações de caixa de correio padrão para um ou todos os tipos de logon usando esta sintaxe:

```PowerShell
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

Você pode especificar vários valores *Defaultauditset* separados por vírgulas

**Observação**: os seguintes procedimentos não se aplicam às caixas de correio de grupo do Office 365 (eles estão limitados às ações padrão, conforme descrito [aqui](#mailbox-actions-for-office-365-group-mailboxes)).

Este exemplo restaura as ações de caixa de correio auditadas padrão para todos os tipos de logon na caixa de correio mark@contoso.onmicrosoft.com.

```PowerShell
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

Este exemplo restaura as ações de caixa de correio auditadas padrão para o tipo de logon de administrador na caixa de correio chris@contoso.onmicrosoft.com, mas deixa as ações de caixa de correio auditadas para o representante e os tipos de logon proprietário.

```PowerShell
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

Restaurar as ações de caixa de correio auditadas por padrão para um tipo de logon tem os seguintes resultados:

- A lista atual de ações de caixa de correio é substituída pelas ações de caixa de correio padrão para o tipo de logon.

- Quaisquer novas ações de caixa de correio lançadas pela Microsoft são automaticamente adicionadas à lista de ações auditadas para o tipo de logon.

- O valor da propriedade *Defaultauditset* da caixa de correio é atualizado para incluir o tipo de logon restaurado.

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a>Desativar a auditoria de caixa de correio por padrão para sua organização

Você pode desativar a auditoria de caixa de correio por padrão para toda a organização executando o seguinte comando no PowerShell do Exchange Online:

```PowerShell
Set-OrganizationConfig -AuditDisabled $true
```

Por padrão, a desativação da auditoria de caixa de correio tem os seguintes resultados:

- A auditoria de caixa de correio está desabilitada para sua organização.

- A partir do momento em que você desabilitou a auditoria de caixa de correio ativada por padrão, nenhuma ação de caixa de correio é auditada, mesmo se a auditoria estiver habilitada em uma caixa de correio (a propriedade *AuditEnabled* na caixa de correio é **verdadeira**).

- A auditoria de caixa de correio não está habilitada para novas caixas de correio e a definição da propriedade *AuditEnabled* em uma caixa de correio nova ou existente como **true** será ignorada.

- Todas as configurações de associação de bypass de auditoria de caixa de correio (configuradas usando o cmdlet **Set-MailboxAuditBypassAssociation** ) são ignoradas.

- Os registros de auditoria de caixa de correio existentes são mantidos até que o limite de idade do log de auditoria do registro expire.

### <a name="turn-on-mailbox-auditing-on-by-default"></a>Habilitar a auditoria de caixa de correio por padrão

Para ativar novamente a auditoria de caixa de correio em sua organização, execute o seguinte comando no PowerShell do Exchange Online:

```PowerShell
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a>Ignorar log de auditoria de caixa de correio

No momento, não é possível desabilitar a auditoria de caixa de correio para caixas de correio específicas quando a auditoria de caixa de correio ativa por padrão em sua organização. Por exemplo, a definição da propriedade de caixa de correio *AuditEnabled* como **false** será ignorada.

No entanto, você ainda pode usar o cmdlet **Set-MailboxAuditBypassAssociation** no PowerShell do Exchange Online para impedir que *todas* as ações de caixa de correio dos usuários especificados sejam registradas, independentemente de onde ocorram as ações. Por exemplo:

- As ações do proprietário da caixa de correio executadas pelos usuários ignorados não são registradas.

- As ações de representante executadas pelos usuários ignorados em caixas de correio de outros usuários (incluindo caixas de correio compartilhadas) não são registradas.

- Ações de administrador executadas pelos usuários ignorados não são registradas.

Para ignorar o log de auditoria de caixa de correio para \<um\> usuário específico, substitua mailboxidentity pela pelo nome, endereço de email, alias ou nome de usuário principal (username) do usuário e execute o seguinte comando:

```PowerShell
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

Para verificar se a auditoria foi ignorada para o usuário especificado, execute o seguinte comando:

```PowerShell
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

O valor **true** indica que o log de auditoria de caixa de correio é ignorado para o usuário.

## <a name="more-information"></a>Mais informações

- Embora o registro em log de auditoria de caixa de correio ativado por padrão esteja habilitado para todas as organizações, somente os usuários com licenças E5 retornarão eventos de log de auditoria de caixa de correio nas [pesquisas de log de auditoria no centro de conformidade & segurança](search-the-audit-log-in-security-and-compliance.md) ou por meio da [API de atividade de gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) **por**

  Para recuperar entradas de log de auditoria de caixa de correio para usuários sem licenças e5, você pode:

  - Use pesquisas de log de auditoria no centro de conformidade & segurança ou por meio da API de atividade de gerenciamento do Office 365 **depois** de habilitar manualmente a auditoria de caixa de correio nas caixas de correio individuais.

  - Use os seguintes cmdlets no PowerShell do Exchange Online:

    - [Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog) para pesquisar o log de auditoria de caixa de correio para usuários específicos.

    - [New-MailboxAuditLogSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/new-mailboxauditlogsearch) para pesquisar o log de auditoria de caixa de correio para usuários específicos e para que os resultados sejam enviados por email para destinatários especificados.

  - Use o centro de administração do Exchange (Eat) no Exchange Online para executar as seguintes ações:

    - [Exportar logs de auditoria de caixas de correio](https://docs.microsoft.com/Exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs)

    - [Executar um relatório de acesso não proprietário da caixa de correio](https://docs.microsoft.com/Exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report)

- Por padrão, os registros de log de auditoria de caixa de correio são mantidos por 90 dias antes de serem excluídos. Você pode alterar o limite de idade para registros de log de auditoria usando o parâmetro *AuditLogAgeLimit* no cmdlet **Set-Mailbox** no PowerShell do Exchange Online. No entanto, aumentar esse valor não permite que você pesquise eventos com mais de 90 dias no log de auditoria do Office 365.

  Se você aumentar o limite de idade, será necessário usar o cmdlet [Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog) no PowerShell do Exchange Online para pesquisar o log de auditoria de caixa de correio do usuário em registros com mais de 90 dias.

- Se você tiver alterado a propriedade *AuditLogAgeLimit* para uma caixa de correio antes de a auditoria da caixa de correio ativada por padrão para a organização, o limite de idade do log de auditoria existente da caixa de correio não será alterado. Em outras palavras, a auditoria de caixa de correio ativada por padrão não afeta o limite de idade atual para registros de auditoria de caixa de correio.

- Para alterar o valor *AuditLogAgeLimit* em uma caixa de correio de grupo do Office 365, você `-GroupMailbox` precisa incluir a opção no comando **Set-Mailbox** .

- Os registros de log de auditoria de caixa de correio são armazenados em uma subpasta ( *auditorias*nomeadas) na pasta itens recuperáveis na caixa de correio de cada usuário. Considere os seguintes aspectos em relação aos registros de auditoria de caixa de correio e à pasta itens recuperáveis:

  - Os registros de auditoria de caixa de correio são considerados na cota de armazenamento da pasta itens recuperáveis, que é 30GB por padrão (a cota de aviso é de 20 GB). A cota de armazenamento é aumentada automaticamente para 100 GB (com uma cota de aviso de 90 GB) quando:

    - Uma retenção é colocada em uma caixa de correio.

    - A caixa de correio é atribuída a uma política de retenção no centro de conformidade.

  - Os registros de auditoria de caixa de correio também são considerados no [limite de pastas da pasta itens recuperáveis](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits). No máximo 3 milhões itens (registros de auditoria) podem ser armazenados na subpasta Auditorias.

    > [!NOTE]
    > É improvável que a auditoria de caixa de correio por padrão afete a cota de armazenamento ou o limite de pasta da pasta itens recuperáveis.

    - Você pode executar o seguinte comando no PowerShell do Exchange Online para exibir o tamanho e o número de itens na subpasta auditorias da pasta itens recuperáveis:

      ```PowerShell
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - Você não pode acessar diretamente um registro de log de auditoria na pasta itens recuperáveis; em vez disso, você usa o cmdlet **Search-MailboxAuditLog** ou pesquisa o log de auditoria do Office 365 para localizar e exibir registros de auditoria de caixa de correio.

- Se uma caixa de correio for colocada em espera ou atribuída a uma política de retenção no centro de conformidade, os registros de log de auditoria ainda serão mantidos pela duração definida pela propriedade *AuditLogAgeLimit* da caixa de correio (90 dias por padrão). Para manter os registros de log de auditoria mais longos para caixas de correio em espera, você precisa aumentar o valor de *AuditLogAgeLimit* da caixa de correio.
