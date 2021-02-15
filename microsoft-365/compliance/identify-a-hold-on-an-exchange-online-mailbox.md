---
title: Como identificar o tipo de retenção de uma caixa de correio do Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
ms.custom:
- seo-marvel-apr2020
description: Saiba como identificar os diferentes tipos de espera que podem ser colocados em uma caixa de correio do Exchange Online no Microsoft 365.
ms.openlocfilehash: c0f5d11066169181b524632c7a1340c54f0061f0
ms.sourcegitcommit: 33afa334328cc4e3f2474abd611c1411adabd39f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48370331"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>Como identificar o tipo de retenção de uma caixa de correio do Exchange Online

Este artigo explica como identificar retém colocadas em caixas de correio do Exchange Online no Microsoft 365.

O Microsoft 365 oferece várias maneiras que sua organização pode impedir que o conteúdo da caixa de correio seja excluído permanentemente. Isso permite que sua organização retenha o conteúdo para atender aos regulamentos de conformidade ou durante processos legais e outros tipos de investigações. Aqui está uma lista dos recursos de retenção (também chamados de *retenções)* no Office 365:

- **[Litígio :](create-a-litigation-hold.md)** Retém que são aplicadas a caixas de correio de usuário no Exchange Online.

- **[EDiscovery hold](create-ediscovery-holds.md):** Retém que estão associadas a um caso de Descoberta e Principal no centro de conformidade e segurança. As rescuções de Descoberta Eletrônico podem ser aplicadas às caixas de correio do usuário e à caixa de correio correspondente para Grupos do Microsoft 365 e Microsoft Teams.

- **[In-Place Hold](https://docs.microsoft.com/Exchange/security-and-compliance/create-or-remove-in-place-holds):** Retém que são aplicadas às caixas de correio do usuário usando a ferramenta In-Place eDiscovery & Hold no Centro de administração do Exchange no Exchange Online.

- **[Políticas de retenção do Microsoft 365:](retention.md)** Pode ser configurado para reter (ou reter e excluir) conteúdo em caixas de correio de usuário no Exchange Online e na caixa de correio correspondente para Grupos do Microsoft 365 e Microsoft Teams. Você também pode criar uma política de retenção para reter conversas do Skype for Business, que são armazenadas em caixas de correio do usuário.

  Há dois tipos de políticas de retenção do Microsoft 365 que podem ser atribuídos a caixas de correio.

    - **Políticas de retenção de local específicas:** Estas são as políticas atribuídas aos locais de conteúdo de usuários específicos. Use o cmdlet **Get-Mailbox** no PowerShell do Exchange Online para obter informações sobre políticas de retenção atribuídas a caixas de correio específicas. Para obter mais informações sobre esse tipo de política de retenção, consulte a seção Uma política com inclusões ou exclusões [específicas](create-retention-policies.md#a-policy-with-specific-inclusions-or-exclusions) da documentação da política de retenção.

    - **Políticas de retenção para toda a organização:** Estas são as políticas atribuídas a todos os locais de conteúdo em sua organização. Use o cmdlet **Get-OrganizationConfig** no PowerShell do Exchange Online para obter informações sobre políticas de retenção em toda a organização. Para obter mais informações sobre esse tipo de política de retenção, consulte a seção A que se aplica a locais [inteiros](create-retention-policies.md#a-policy-that-applies-to-entire-locations) na documentação da política de retenção.

- **Rótulos de retenção do [Microsoft 365:](retention.md)** se um usuário aplicar um rótulo de retenção do Microsoft 365 (um que está configurado para reter conteúdo ou reter e excluir conteúdo) a qualquer pasta ou item em sua caixa de correio, uma retenção será colocada na caixa de correio como se a caixa de correio tivesse sido colocada em Retenção de Litígio ou atribuída a uma política de retenção do Microsoft 365.  Para obter mais informações, consulte a seção Identificando caixas de correio em espera porque um rótulo de retenção foi aplicado a uma seção de pasta ou [item](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) neste artigo.

Para gerenciar caixas de correio em espera, talvez seja necessário identificar o tipo de retenção que é colocado em uma caixa de correio para que você possa executar tarefas como alterar a duração da retenção, remover temporaria ou permanentemente a retenção ou excluir uma caixa de correio de uma política de retenção do Microsoft 365. Nesses casos, a primeira etapa é identificar o tipo de espera colocada na caixa de correio. E como várias retém (e diferentes tipos de retém) podem ser colocadas em uma única caixa de correio, você precisa identificar todas as retém colocadas em uma caixa de correio se quiser remover ou alterar uma espera.

## <a name="step-1-obtain-the-guid-for-holds-placed-on-a-mailbox"></a>Etapa 1: Obter o GUID para retém colocados em uma caixa de correio

Você pode executar os dois cmdlets a seguir no PowerShell do Exchange Online para obter o GUID dos retém colocados em uma caixa de correio. Depois de obter um GUID, use-o para identificar a espera específica na Etapa 2. Uma Espera de Litígio não é identificada por um GUID. As Retém de Litígio estão habilitadas ou desabilitadas para uma caixa de correio.

- **Get-Mailbox:** Use este cmdlet para determinar se a Retenção de Litígio está habilitada para uma caixa de correio e obter os GUIDs para retenções de Descoberta Eletrônica, In-Place Isenções e políticas de retenção do Microsoft 365 especificamente atribuídas a uma caixa de correio. A saída desse cmdlet também indicará se uma caixa de correio foi explicitamente excluída de uma política de retenção em toda a organização.

- **Get-OrganizationConfig:** Use este cmdlet para obter os GUIDs das políticas de retenção em toda a organização.

Para se conectar ao Windows PowerShell do Exchange Online, confira [Conectar ao Windows PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

### <a name="get-mailbox"></a>Get-Mailbox

Execute o seguinte comando para obter informações sobre as retenções e as políticas de retenção do Microsoft 365 aplicadas a uma caixa de correio.

```powershell
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> Se houver muitos valores na propriedade InPlaceHolds e nem todos eles são exibidos, você pode executar o comando para exibir cada GUID em `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` uma linha separada.

A tabela a seguir descreve como identificar diferentes tipos de reter com base nos valores na propriedade *InPlaceHolds* quando você executar o cmdlet **Get-Mailbox.**


|Tipo de espera  |Valor de exemplo  |Como identificar a espera  |
|---------|---------|---------|
|Retenção de litígio     |    `True`     |     A responsabilidade de litígio é habilitada para uma caixa de correio quando a propriedade *LitigationHoldEnabled* está definida como `True` .    |
|EDiscovery hold     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   A *propriedade InPlaceHolds* contém o GUID de qualquer espera associada a um caso de Descoberta eDiscovery no centro de conformidade e segurança. Você pode dizer que se trata de uma isenção de Descoberta Descoberta porque o GUID começa com o `UniH` prefixo (que indica uma Isenção Unificada).      |
|Bloqueio In-loco     |     `c0ba3ce811b6432a8751430937152491` <br/> ou <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     A *propriedade InPlaceHolds* contém o GUID do In-Place que é colocado na caixa de correio. Você pode dizer que esse é um In-Place, pois o GUID não começa com um prefixo ou começa com o `cld` prefixo.     |
|Política de retenção do Microsoft 365 aplicada especificamente à caixa de correio     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> ou <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     A propriedade InPlaceHolds contém GUIDs de qualquer política de retenção de local específica aplicada à caixa de correio. Você pode identificar políticas de retenção porque o GUID começa com `mbx` o `skp` prefixo ou o guid. O `skp` prefixo indica que a política de retenção é aplicada às conversas do Skype for Business na caixa de correio do usuário.    |
|Excluído de uma política de retenção do Microsoft 365 em toda a organização     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     Se uma caixa de correio for excluída de uma política de retenção do Microsoft 365 em toda a organização, o GUID da política de retenção da caixa de correio da caixa de correio excluída será exibido na propriedade InPlaceHolds e será identificado pelo `-mbx` prefixo.    |

### <a name="get-organizationconfig"></a>Get-OrganizationConfig
Se a propriedade *InPlaceHolds* estiver vazia quando você executar o cmdlet **Get-Mailbox,** ainda poderá haver uma ou mais políticas de retenção do Microsoft 365 em toda a organização aplicadas à caixa de correio. Execute o seguinte comando no PowerShell do Exchange Online para obter uma lista de GUIDs para políticas de retenção do Microsoft 365 em toda a organização.

```powershell
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> Se houver muitos valores na propriedade InPlaceHolds e nem todos eles são exibidos, você pode executar o comando para exibir cada GUID em `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` uma linha separada.

A tabela a seguir descreve os diferentes tipos de reter em toda a organização e como identificar cada tipo com base nos GUIDs contidos na propriedade *InPlaceHolds* quando você executar o cmdlet **Get-OrganizationConfig.**


|Tipo de espera  |Valor de exemplo  |Descrição  |
|---------|---------|---------|
|Políticas de retenção do Microsoft 365 aplicadas a caixas de correio do Exchange, pastas públicas do Exchange e chats do Teams    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   As políticas de retenção em toda a organização aplicadas a caixas de correio do Exchange, pastas públicas do Exchange e chats 1xN no Microsoft Teams são identificadas por GUIDs que começam com o `mbx` prefixo. Observação: os chats 1xN são armazenados na caixa de correio dos participantes individuais do chat.      |
|Política de retenção do Microsoft 365 aplicada às mensagens de canal dos Grupos do Microsoft 365 e do Teams     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    As políticas de retenção em toda a organização aplicadas a grupos e mensagens de canal do Microsoft 365 no Microsoft Teams são identificadas por GUIDs que começam com o `grp` prefixo. As mensagens do canal de anotações são armazenadas na caixa de correio do grupo associada a um Microsoft Team.     |

Para saber mais sobre as políticas de retenção aplicadas ao Microsoft Teams, confira Saiba mais sobre as políticas [de retenção do Microsoft Teams.](retention-policies-teams.md)

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>Noções básicas sobre o formato do valor InPlaceHolds para políticas de retenção

Além do prefixo (mbx, skp ou grp) que identifica um item na propriedade InPlaceHolds como uma política de retenção do Microsoft 365, o valor também contém um sufixo que identifica o tipo de ação de retenção configurada para a política. Por exemplo, o sufixo de ação é realçado em negrito nos exemplos a seguir:

   `skp127d7cf1076947929bf136b7a2a8c36f`**:1**

   `mbx7cfb30345d454ac0a989ab3041051209`**:2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**:3**

A tabela a seguir define as três ações de retenção possíveis:

|Valor  |Descrição  |
|---------|---------|
|**1**     | Indica que a política de retenção está configurada para excluir itens. A política não retém itens.        |
|**2**    |    Indica que a política de retenção está configurada para retenções de itens. A política não exclui itens após o período de retenção expirar.     |
|**3**     |   Indica que a política de retenção está configurada para retenções de itens e, em seguida, excluí-los após o período de retenção expirar.      |

Para obter mais informações sobre ações de retenção, consulte [a seção Retenção de conteúdo para um período específico de](create-retention-policies.md#retaining-content-for-a-specific-period-of-time) tempo.
   
## <a name="step-2-use-the-guid-to-identify-the-hold"></a>Etapa 2: Usar o GUID para identificar a espera

Depois de obter o GUID de uma iseção que é aplicada a uma caixa de correio, a próxima etapa é usar esse GUID para identificar a iseção. As seções a seguir mostram como identificar o nome da espera (e outras informações) usando o GUID de espera.

### <a name="ediscovery-holds"></a>Bloqueios de Descoberta Eletrônica

Execute os seguintes comandos & no PowerShell do Centro de Conformidade e Segurança para identificar uma espera de Descoberta Eletrônico aplicada à caixa de correio. Use o GUID (sem incluir o prefixo UniH) para a isenção de Descoberta e que você identificou na Etapa 1. O primeiro comando cria uma variável que contém informações sobre a espera. Essa variável é usada nos outros comandos. O segundo comando exibe o nome da ocorrência de Descoberta e à que a isenção está associada. O terceiro comando exibe o nome da espera e uma lista das caixas de correio às que a espera se aplica.

```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold | FL Name,ExchangeLocation
```

Para se conectar ao PowerShell do Centro de Conformidade & segurança, confira Conectar-se ao PowerShell do Centro de [Conformidade & Segurança.](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)

### <a name="in-place-holds"></a>Bloqueio In-loco

Execute o seguinte comando no PowerShell do Exchange Online para identificar a In-Place de correio aplicada à caixa de correio. Use o GUID para a In-Place que você identificou na Etapa 1. O comando exibe o nome da espera e uma lista das caixas de correio às que a espera se aplica.

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```

Se o GUID do In-Place De espera iniciar com o prefixo, certifique-se de incluir o `cld` prefixo ao executar o comando anterior.

> [!IMPORTANT]
> À medida que continuamos investindo em maneiras diferentes de preservar o conteúdo da caixa de correio, anunciamos a ressarção de In-Place retém no Centro de administração do Exchange (EAC). A partir de 1º de julho de 2020, você não poderá criar novos In-Place retém no Exchange Online. Mas você ainda poderá gerenciar In-Place Retém no EAC ou usando o cmdlet **Set-MailboxSearch** no PowerShell do Exchange Online. No entanto, a partir de 1º de outubro de 2020, você não poderá gerenciar o In-Place Retém. Você só os removerá no EAC ou usando o cmdlet **Remove-MailboxSearch.** Para obter mais informações sobre a baixa In-Place, consulte a Baixa das ferramentas de [Descoberta eDiscovery herdado.](legacy-ediscovery-retirement.md)

### <a name="microsoft-365-retention-policies"></a>Políticas de retenção do Microsoft 365

Execute & o seguinte comando no PowerShell do Centro de Conformidade e Segurança para identificar a política de retenção do Microsoft 365 (local específico ou em toda a organização) aplicada à caixa de correio. Use o GUID (sem incluir o prefixo mbx, skp ou grp ou o sufixo de ação) identificado na Etapa 1.

```powershell
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a>Identificar caixas de correio em espera porque um rótulo de retenção foi aplicado a uma pasta ou item

Sempre que um usuário aplica um rótulo de retenção configurado para reter conteúdo ou reter e, em seguida, excluir conteúdo para qualquer pasta ou item em sua caixa de correio, a propriedade de caixa de correio *ComplianceTagHoldApplied* é definida como **True**. Quando isso acontece, a caixa de correio é considerada em espera, como se tivesse sido colocada em Retenção de Litígio ou atribuída a uma política de retenção do Microsoft 365. Quando a *propriedade ComplianceTagHoldApplied* estiver definida como **True,** as seguintes coisas podem ocorrer:

- Se a caixa de correio ou a conta de usuário do usuário for excluída, ela se tornará [uma caixa de correio inativa.](inactive-mailboxes-in-office-365.md)
- Não é possível desabilitar a caixa de correio (a caixa de correio principal ou a caixa de correio de arquivo morto, se ela estiver habilitada).
- Os itens na caixa de correio podem ser mantidos por mais tempo do que o esperado. Isso porque a caixa de correio está em espera e, portanto, nenhum item é excluído permanentemente (excluído).

Para exibir o valor da *propriedade ComplianceTagHoldApplied,* execute o seguinte comando no PowerShell do Exchange Online:

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

Para obter mais informações sobre rótulos de retenção, consulte [rótulos de retenção.](retention.md#retention-labels)

## <a name="managing-mailboxes-on-delay-hold"></a>Gerenciando caixas de correio em espera de atraso

Depois que qualquer tipo de espera é removido de uma caixa de correio, um *atraso é* aplicado. Isso significa que a remoção real da espera é adiada por 30 dias para impedir que os dados são excluídos permanentemente (excluídos) da caixa de correio. Isso oferece aos administradores a oportunidade de pesquisar ou recuperar itens de caixa de correio que serão removidos após a remoção de uma espera. Um atraso é colocado em uma caixa de correio na próxima vez que o Assistente de Pasta Gerenciada processa a caixa de correio e detecta que uma espera foi removida. Especificamente, um atraso é aplicado a uma caixa de correio quando o Assistente de Pasta Gerenciada define uma das seguintes propriedades de caixa de correio como **True:**

- **DelayHoldApplied:** Essa propriedade se aplica ao conteúdo relacionado ao email (gerado por pessoas que usam o Outlook e o Outlook na Web) armazenado na caixa de correio de um usuário.

- **DelayReleaseHoldApplied:** Essa propriedade se aplica ao conteúdo baseado em nuvem (gerado por aplicativos que não são do Outlook, como Microsoft Teams, Microsoft Forms e Microsoft Yammer) armazenado na caixa de correio de um usuário. Os dados de nuvem gerados por um aplicativo da Microsoft normalmente são armazenados em uma pasta oculta na caixa de correio de um usuário.
 
 Quando uma espera de atraso é colocada na caixa de correio (quando uma das propriedades anteriores é definida como **True**), a caixa de correio ainda é considerada em espera por uma duração de espera ilimitada, como se a caixa de correio estivesse em Litígio. Após 30 dias, a espera de atraso expirará, e o Microsoft 365 tentará remover automaticamente a espera de atraso (definindo a propriedade DelayHoldApplied ou DelayReleaseHoldApplied como **False**) para que a espera seja removida. Depois que uma dessas propriedades for definida como **False**, os itens correspondentes marcados para remoção serão limpos na próxima vez que a caixa de correio for processada pelo Assistente de Pasta Gerenciada.

Para exibir os valores das propriedades DelayHoldApplied e DelayReleaseHoldApplied de uma caixa de correio, execute o seguinte comando no PowerShell do Exchange Online.

```powershell
Get-Mailbox <username> | FL *HoldApplied*
```

Para remover a espera de atraso antes que ela expire, você pode executar um (ou ambos) os seguintes comandos no PowerShell do Exchange Online, dependendo da propriedade que você deseja alterar: 
 
```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

Ou
 
```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

Você deve ter a função de Reter Legal no Exchange Online para usar os parâmetros *RemoveDelayHoldApplied* ou *RemoveDelayReleaseHoldApplied.* 

Para remover a espera de atraso em uma caixa de correio inativa, execute um dos seguintes comandos no PowerShell do Exchange Online:

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

Ou

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayReleaseHoldApplied
```

> [!TIP]
> A melhor maneira de especificar uma caixa de correio inativa no comando anterior é usar seu nome diferenciado ou valor GUID do Exchange. Usar um desses valores ajuda a evitar a especificação acidental da caixa de correio errada. 

Para obter mais informações sobre como usar esses parâmetros para gerenciar retém de atraso, consulte [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).

Lembre-se do seguinte ao gerenciar uma caixa de correio em espera de atraso:

- Se a propriedade DelayHoldApplied ou DelayReleaseHoldApplied for definida como **True** e uma caixa de correio (ou a conta de usuário correspondente) for excluída, a caixa de correio se tornará uma caixa de correio inativa. Isso acontece porque uma caixa de correio será considerada em espera se uma das propriedades for definida como **True** e a exclusão de uma caixa de correio em espera resulta em uma caixa de correio inativa. Para excluir uma caixa de correio e não torná-la uma caixa de correio inativa, você precisa definir as duas propriedades como **False**.

- Conforme indicado anteriormente, uma caixa de correio será considerada em espera por uma duração de espera ilimitada se a propriedade DelayHoldApplied ou DelayReleaseHoldApplied estiver definida como **True**. No entanto, isso não significa que *todo o* conteúdo na caixa de correio seja preservado. Depende do valor definido para cada propriedade. Por exemplo, digamos que ambas as propriedades estão definidas como **True** porque retém são removidas da caixa de correio. Em seguida, remova apenas a espera de atraso aplicada a dados de nuvem que não são do Outlook (usando o *parâmetro RemoveDelayReleaseHoldApplied).* Na próxima vez que o Assistente de Pasta Gerenciada processa a caixa de correio, os itens que não são do Outlook marcados para remoção são limpos. Todos os itens do Outlook marcados para remoção não serão limpos porque a propriedade DelayHoldApplied ainda está definida como **True**. O oposto também seria verdadeiro: se DelayHoldApplied for definido como **False** e DelayReleaseHoldApplied for definido como **True,** somente os itens do Outlook marcados para remoção serão limpos.

## <a name="next-steps"></a>Próximas etapas

Depois de identificar as retenções aplicadas a uma caixa de correio, você pode executar tarefas como alterar a duração da retenção, remover temporaria ou permanentemente a retenção ou excluir uma caixa de correio inativa de uma política de retenção do Microsoft 365. Para obter mais informações sobre a execução de tarefas relacionadas a remissões, consulte um dos seguintes tópicos:

- Execute o comando [Set-RetentionCompliancePolicy -Identity \<Policy Name> -AddExchangeLocationEx & ception \<user mailbox> ](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) no PowerShell do Centro de Conformidade e Segurança para excluir uma caixa de correio de uma política de retenção do Microsoft 365 em toda a organização. Este comando só pode ser usado para políticas de retenção onde o valor da *propriedade ExchangeLocation* é igual `All` a .

- Execute o [comando Set-Mailbox \<hold GUID without prefix or suffix> -ExcludeFromOrgHolds](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) no PowerShell do Exchange Online para excluir uma caixa de correio inativa de uma política de retenção do Microsoft 365 em toda a organização.

- [Alterar a duração de retenção de uma caixa de correio inativa](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Excluir uma caixa de correio inativa](delete-an-inactive-mailbox.md)

- [Excluir itens na pasta de Itens recuperáveis de caixas de correio baseadas em nuvem em retenção](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
