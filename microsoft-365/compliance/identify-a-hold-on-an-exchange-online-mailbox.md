---
title: Como identificar o tipo de retenção de uma caixa de correio do Exchange Online
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
description: Saiba como identificar os diferentes tipos de retenção que podem ser colocados em uma caixa de correio do Office 365. Esses tipos de isenções incluem retenção de litígio, bloqueios de descoberta eletrônica e políticas de retenção do Office 365. Você também pode determinar se um usuário foi excluído de uma política de retenção em toda a organização
ms.openlocfilehash: dcdb79aa1c1cae83602a42e6c99136a2f85226a1
ms.sourcegitcommit: 03a83ff76c8162b850c4c552759c49f2a4750574
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2020
ms.locfileid: "41558008"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>Como identificar o tipo de retenção de uma caixa de correio do Exchange Online

Este artigo explica como identificar as isenções colocadas nas caixas de correio do Exchange Online no Office 365.

O Office 365 oferece várias maneiras em que sua organização pode impedir que o conteúdo da caixa de correio seja excluído permanentemente. Isso permite que sua organização retenha conteúdo para atender às normas de conformidade ou durante outros tipos de investigações. Veja a seguir uma lista dos recursos de retenção (também chamados de *isenções*) no Office 365:

- ** [Retenção de litígio](create-a-litigation-hold.md):** As isenções são aplicadas às caixas de correio do usuário no Exchange Online.

- ** [bloqueio de descoberta eletrônica](ediscovery-cases.md#step-4-place-content-locations-on-hold):** Suspensões associadas a uma ocorrência de descoberta eletrônica no centro de conformidade e segurança. as suspensões de descoberta eletrônica podem ser aplicadas às caixas de correio do usuário e à caixa de correio correspondente dos grupos do Office 365 e do Microsoft Teams.

- ** [Bloqueio in-loco](https://docs.microsoft.com/Exchange/security-and-compliance/create-or-remove-in-place-holds):** As isenções são aplicadas às caixas de correio do usuário usando a ferramenta de bloqueio de & de descoberta eletrônica in-loco no centro de administração do Exchange no Exchange Online.

- ** [Políticas de retenção do Office 365](retention-policies.md):** O pode ser configurado para reter (ou reter e excluir) o conteúdo nas caixas de correio do usuário no Exchange Online e na caixa de correio correspondente dos grupos do Office 365 e do Microsoft Teams. Você também pode criar uma política de retenção para reter as conversas do Skype for Business, que são armazenadas nas caixas de correio do usuário.

  Há dois tipos de políticas de retenção do Office 365 que podem ser atribuídos às caixas de correio.

    - **Políticas de retenção de local específico:** Essas são as políticas atribuídas aos locais de conteúdo de usuários específicos. Você usa o cmdlet **Get-Mailbox** no PowerShell do Exchange Online para obter informações sobre políticas de retenção atribuídas a caixas de correio específicas.

    - **Políticas de retenção em toda a organização:** Essas são as políticas atribuídas a todos os locais de conteúdo em sua organização. Você usa o cmdlet **Get-OrganizationConfig** no PowerShell do Exchange Online para obter informações sobre políticas de retenção em toda a organização.
  Para obter mais informações, consulte a seção "aplicando uma política de retenção a uma organização inteira ou locais específicos" em [visão geral das políticas de retenção do Office 365](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations).

- **[Rótulos de retenção do office 365](labels.md):** se um usuário aplicar um rótulo de retenção do Office 365 (um que esteja configurado para reter conteúdo ou reter e excluir conteúdo) em *qualquer* pasta ou item na caixa de correio, uma retenção será colocada na caixa de correio como se a caixa de correio fosse colocada em retenção de litígio ou atribuída a uma política de retenção do Office 365. Para obter mais informações, consulte o artigo [identificando caixas de correio em espera porque um rótulo de retenção foi aplicado a uma seção de pasta ou item](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) neste artigo.

Para gerenciar caixas de correio em espera, talvez seja necessário identificar o tipo de retenção colocado em uma caixa de correio para que você possa realizar tarefas como alterar a duração da retenção, remover temporariamente ou permanentemente a retenção ou excluir uma caixa de correio de uma política de retenção do Office 365. Nesses casos, a primeira etapa é identificar o tipo de retenção colocado na caixa de correio. E como várias isenções (e diferentes tipos de isenções) podem ser colocadas em uma única caixa de correio, você precisa identificar todas as isenções colocadas em uma caixa de correio se quiser remover ou alterar uma isenção.

## <a name="step-1-obtain-the-guid-for-holds-placed-on-a-mailbox"></a>Etapa 1: obter o GUID de suspensões colocadas em uma caixa de correio

Você pode executar os dois cmdlets a seguir no PowerShell do Exchange Online para obter o GUID das isenções que são colocadas em uma caixa de correio. Depois de obter um GUID, use-o para identificar o bloqueio específico na etapa 2. Uma retenção de litígio não é identificada por um GUID. A retenção de litígio está habilitada ou desabilitada para uma caixa de correio.

- **Get-Mailbox:** Use este cmdlet para determinar se a retenção de litígio está habilitada para uma caixa de correio e para obter os GUIDs de bloqueios de descoberta eletrônica, bloqueio in-loco e políticas de retenção do Office 365 que são especificamente atribuídas a uma caixa de correio. A saída desse cmdlet também indica se uma caixa de correio foi explicitamente excluída de uma política de retenção em toda a organização.

- **Get-OrganizationConfig:** Use este cmdlet para obter os GUIDs de políticas de retenção em toda a organização.

Para se conectar ao Exchange Online PowerShell, confira [Conectar ao Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).

### <a name="get-mailbox"></a>Get-Mailbox

Execute o seguinte comando para obter informações sobre as políticas de retenção de isenções e do Office 365 aplicadas a uma caixa de correio.

```powershell
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> Se houver muitos valores na propriedade InPlaceHolds e nem todos eles forem exibidos, você poderá executar o `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` comando para exibir cada GUID em uma linha separada.

A tabela a seguir descreve como identificar diferentes tipos de isenções com base nos valores da propriedade *InPlaceHolds* quando você executa o cmdlet **Get-Mailbox** .


|Tipo de bloqueio  |Valor de exemplo  |Como identificar a isenção  |
|---------|---------|---------|
|Retenção de litígio     |    `True`     |     A retenção de litígio está habilitada para uma caixa ** de correio quando a propriedade `True`LitigationHoldEnabled é definida como.    |
|retenção de descoberta eletrônica     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   A *Propriedade InPlaceHolds* contém o GUID de qualquer isenção associada a uma ocorrência de descoberta eletrônica no centro de conformidade e segurança. É possível dizer que esse é um bloqueio de descoberta eletrônica porque o GUID `UniH` começa com o prefixo (que denota uma retenção unificada).      |
|Bloqueio In-loco     |     `c0ba3ce811b6432a8751430937152491` <br/> ou <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     A propriedade *InPlaceHolds* contém o GUID do bloqueio in-loco colocado na caixa de correio. Você pode dizer que isso é um bloqueio in-loco, pois o GUID não começa com um prefixo ou começa com o `cld` prefixo.     |
|Política de retenção do Office 365 aplicada especificamente à caixa de correio     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> ou <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     A propriedade InPlaceHolds contém GUIDs de qualquer política de retenção de local específica que é aplicada à caixa de correio. Você pode identificar as políticas de retenção porque o GUID começa `mbx` com o `skp` ou o prefixo. O `skp` prefixo indica que a política de retenção é aplicada às conversas do Skype for Business na caixa de correio do usuário.    |
|Excluído de uma política de retenção do Office 365 em toda a organização     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     Se uma caixa de correio for excluída de uma política de retenção do Office 365 em toda a organização, o GUID da política de retenção para a qual a caixa de correio é excluída `-mbx` é exibida na propriedade InPlaceHolds e é identificado pelo prefixo.    |

### <a name="get-organizationconfig"></a>Get-OrganizationConfig
Se a propriedade *InPlaceHolds* estiver vazia quando você executar o cmdlet **Get-Mailbox** , ainda poderá haver uma ou mais políticas de retenção do Office 365 em toda a organização aplicadas à caixa de correio. Execute o seguinte comando no PowerShell do Exchange Online para obter uma lista de GUIDs para as políticas de retenção do Office 365 em toda a organização.

```powershell
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> Se houver muitos valores na propriedade InPlaceHolds e nem todos eles forem exibidos, você poderá executar o `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` comando para exibir cada GUID em uma linha separada.

A tabela a seguir descreve os diferentes tipos de bloqueios de toda a organização e como identificar cada tipo com base nos GUIDs contidos na propriedade *InPlaceHolds* quando você executa o cmdlet **Get-OrganizationConfig** .


|Tipo de bloqueio  |Valor de exemplo  |Descrição  |
|---------|---------|---------|
|Políticas de retenção do Office 365 aplicadas a caixas de correio do Exchange, pastas públicas do Exchange e chats do Microsoft Teams    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   Políticas de retenção em toda a organização aplicadas às caixas de correio do Exchange, pastas públicas do Exchange e chats do 1xN no Microsoft Teams são identificadas `mbx` por GUIDs que começam com o prefixo. Observação os chats do 1xN são armazenados na caixa de correio dos participantes individuais do chat.      |
|Política de retenção do Office 365 aplicada a grupos do Office 365 e mensagens de canal do teams     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    Políticas de retenção em toda a organização aplicadas a grupos do Office 365 e mensagens de canal no Microsoft Teams são identificadas por `grp` GUIDs que começam com o prefixo. Observação as mensagens do canal são armazenadas na caixa de correio de grupo associada a uma equipe da Microsoft.     |

Para obter mais políticas de retenção de informações aplicadas ao Microsoft Teams, consulte a seção "local da equipe" [visão geral das políticas de retenção](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations).

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>Noções básicas sobre o formato do valor InPlaceHolds para políticas de retenção

Além do prefixo (MBX, SKP ou GRP) que identifica um item na propriedade InPlaceHolds como uma política de retenção do Office 365, o valor também contém um sufixo que identifica o tipo de ação de retenção que é configurado para a política. Por exemplo, o sufixo de ação é realçado em negrito nos seguintes exemplos:

   `skp127d7cf1076947929bf136b7a2a8c36f`**: 1**

   `mbx7cfb30345d454ac0a989ab3041051209`**: 2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**: 3**

A tabela a seguir define as três ações de retenção possíveis:

|Valor  |Descrição  |
|---------|---------|
|**1**     | Indica que a política de retenção está configurada para excluir itens. A política não retém itens.        |
|**duas**    |    Indica que a política de retenção está configurada para reter itens. A política não excluirá itens depois que o período de retenção expirar.     |
|**3D**     |   Indica que a política de retenção está configurada para reter itens e excluí-los depois que o período de retenção expira.      |

Para obter mais informações sobre ações de retenção, consulte a seção "retendo conteúdo por um período específico de tempo" em [visão geral das políticas de retenção](retention-policies.md#retaining-content-for-a-specific-period-of-time).
   
## <a name="step-2-use-the-guid-to-identify-the-hold"></a>Etapa 2: usar o GUID para identificar a isenção

Depois de obter o GUID de uma retenção aplicada a uma caixa de correio, a próxima etapa é usar esse GUID para identificar a isenção. As seções a seguir mostram como identificar o nome da retenção (e outras informações) usando o GUID de retenção.

### <a name="ediscovery-holds"></a>bloqueios de descoberta eletrônica

Execute os seguintes comandos no PowerShell do centro de conformidade e segurança & para identificar uma retenção de descoberta eletrônica aplicada à caixa de correio. Use o GUID (não incluindo o prefixo UniH) para o bloqueio de descoberta eletrônica que você identificou na etapa 1. O primeiro comando cria uma variável que contém informações sobre a retenção. Essa variável é usada em outros comandos. O segundo comando exibe o nome da ocorrência de descoberta eletrônica à qual a retenção está associada. O terceiro comando exibe o nome da retenção e uma lista das caixas de correio às quais o bloqueio se aplica.

```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold | FL Name,ExchangeLocation
```

Para se conectar ao PowerShell do centro de conformidade e segurança &, confira [conectar-se ao PowerShell do centro de conformidade do &](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

### <a name="in-place-holds"></a>Bloqueio In-loco

Execute o seguinte comando no PowerShell do Exchange Online para identificar o bloqueio in-loco aplicado à caixa de correio. Use o GUID do bloqueio in-loco identificado na etapa 1. O comando exibe o nome da retenção e uma lista das caixas de correio às quais o bloqueio se aplica.

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```

Se o GUID do bloqueio in-loco começar com o `cld` prefixo, certifique-se de incluir o prefixo ao executar o comando anterior.

> [!IMPORTANT]
> Como continuamos investindo em diferentes maneiras de preservar o conteúdo da caixa de correio, anunciamos a aposentadoria de bloqueios in-loco no centro de administração do Exchange (Eat). A partir de 1º de abril de 2020 você não poderá criar novos bloqueios in-loco no Exchange Online. Mas você ainda poderá gerenciar bloqueios in-loco no Eat ou usando o cmdlet **Set-MailboxSearch** no PowerShell do Exchange Online. No entanto, a partir de 1º de julho de 2020, você não conseguirá gerenciar bloqueios in-loco. Você só deve removê-los no Eat ou usando o cmdlet **Remove-MailboxSearch** . Para obter mais informações sobre a aposentadoria de bloqueios in-loco, consulte [aposentadoria of Legacy eDiscovery Tools](legacy-ediscovery-retirement.md).

### <a name="office-365-retention-policies"></a>Políticas de retenção do Office 365

Execute o seguinte comando em segurança & o PowerShell do centro de conformidade para identificar a política de retenção do Office 365 (local de toda a organização ou específica) que é aplicada à caixa de correio. Use o GUID (sem incluir o prefixo MBX, SKP ou GRP ou o sufixo de ação) identificado na etapa 1.

```powershell
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a>Identificando caixas de correio em espera porque um rótulo de retenção foi aplicado a uma pasta ou item

Sempre que um usuário aplica um rótulo de retenção que é configurado para reter conteúdo ou reter e, em seguida, excluir conteúdo para qualquer pasta ou item em suas caixas de correio, a propriedade de caixa de correio *ComplianceTagHoldApplied* é definida como **true**. Quando isso acontece, a caixa de correio é considerada em espera, como se fosse colocada em retenção de litígio ou atribuída a uma política de retenção do Office 365. Quando a propriedade *ComplianceTagHoldApplied* é definida como **true**, as seguintes coisas podem ocorrer:

- Se a caixa de correio ou a conta de usuário do Office 365 do usuário for excluída, a caixa de correio se tornará uma [caixa de correio inativa](inactive-mailboxes-in-office-365.md).
- Não é possível desabilitar a caixa de correio (a caixa de correio principal ou a caixa de correio de arquivo morto, se ela estiver habilitada).
- Os itens na caixa de correio podem ser mantidos mais tempo do que o esperado. Isso ocorre porque a caixa de correio está em espera e, portanto, nenhum item é excluído permanentemente (limpo).

Para exibir o valor da propriedade *ComplianceTagHoldApplied* , execute o seguinte comando no PowerShell do Exchange Online:

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

Para obter mais informações sobre rótulos de retenção, consulte [visão geral dos rótulos de retenção do Office 365](labels.md).

## <a name="managing-mailboxes-on-delay-hold"></a>Gerenciando caixas de correio em espera de atraso

Após qualquer tipo de retenção ser removido de uma caixa de correio, uma *espera de atraso* é aplicada. Isso significa que a remoção real da retenção está atrasada por 30 dias para evitar que os dados sejam excluídos permanentemente (removidos) da caixa de correio. Isso dá aos administradores uma oportunidade de Pesquisar ou recuperar itens de caixa de correio que serão removidos após a remoção de uma retenção. Uma retenção de atraso é feita em uma caixa de correio na próxima vez que o assistente de pasta gerenciada processa a caixa de correio e detecta que uma retenção foi removida. Especificamente, uma retenção de atraso é aplicada a uma caixa de correio quando o assistente de pasta gerenciada define uma das seguintes propriedades de caixa de correio como **true**:

- **DelayHoldApplied:** Essa propriedade se aplica a conteúdo relacionado a email (gerado por pessoas que usam o Outlook e o Outlook na Web) que está armazenado na caixa de correio de um usuário.

- **DelayReleaseHoldApplied:** Essa propriedade se aplica a conteúdo baseado em nuvem (gerado por aplicativos que não são do Outlook, como o Microsoft Teams, o Microsoft Forms e o Microsoft Yammer) que é armazenado na caixa de correio de um usuário. Os dados de nuvem gerados por um aplicativo da Microsoft geralmente são armazenados em uma pasta oculta da caixa de correio de um usuário.
 
 Quando uma espera de atraso é colocada na caixa de correio (quando qualquer uma das propriedades anteriores é definida como **true**), a caixa de correio ainda é considerada em espera por uma duração de retenção ilimitada, como se a caixa de correio estivesse em retenção de litígio. Após 30 dias, o atraso esperado expira e o Office 365 tentará automaticamente remover o atraso de espera (definindo a propriedade DelayHoldApplied ou DelayReleaseHoldApplied como **false**) para que a retenção seja removida. Após qualquer uma dessas propriedades ser definida como **false**, os itens correspondentes marcados para remoção serão removidos na próxima vez que a caixa de correio for processada pelo assistente de pasta gerenciada.

Para exibir os valores das propriedades DelayHoldApplied e DelayReleaseHoldApplied para uma caixa de correio, execute o seguinte comando no PowerShell do Exchange Online.

```powershell
Get-Mailbox <username> | FL *HoldApplied*
```

Para remover o atraso antes da expiração, você pode executar um (ou ambos) os seguintes comandos no PowerShell do Exchange Online, dependendo da propriedade que você deseja alterar: 
 
```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

Ou
 
```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

Você deve receber a função de retenção legal no Exchange Online para usar os parâmetros *RemoveDelayHoldApplied* ou *RemoveDelayReleaseHoldApplied* . 

Para remover o atraso de espera em uma caixa de correio inativa, execute um dos seguintes comandos no PowerShell do Exchange Online:

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

Ou

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayReleaseHoldApplied
```

> [!TIP]
> A melhor maneira de especificar uma caixa de correio inativa no comando anterior é usar seu nome distinto ou valor de GUID do Exchange. O uso de um desses valores ajuda a evitar a especificação acidental da caixa de correio errada. 

Para obter mais informações sobre como usar esses parâmetros para gerenciar suspensões de atraso, consulte [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).

Tenha em mente os seguintes pontos ao gerenciar uma caixa de correio em atraso de espera:

- Se a propriedade DelayHoldApplied ou DelayReleaseHoldApplied estiver definida como **true** e uma caixa de correio (ou a conta de usuário do Office 365 correspondente) for excluída, a caixa de correio se tornará uma caixa de correio inativa. Isso ocorre porque uma caixa de correio é considerada em espera se a propriedade for definida como **true**e a exclusão de uma caixa de correio em espera resultar em uma caixa de correio inativa. Para excluir uma caixa de correio e não torná-la inativa, você precisa definir ambas as propriedades como **false**.

- Como declarado anteriormente, uma caixa de correio é considerada como em espera para uma duração de retenção ilimitada se a propriedade DelayHoldApplied ou DelayReleaseHoldApplied estiver definida como **true**. No entanto, isso não significa que *todo* o conteúdo da caixa de correio seja preservado. Ele depende do valor que é definido para cada propriedade. Por exemplo, digamos que ambas as propriedades estejam definidas como **true** porque as isenções são removidas da caixa de correio. Em seguida, você remove apenas a espera de atraso aplicada a dados de nuvem não-Outlook (usando o parâmetro *RemoveDelayReleaseHoldApplied* ). Na próxima vez que o assistente de pasta gerenciada processa a caixa de correio, os itens não-Outlook marcados para remoção são removidos. Qualquer item do Outlook marcado para remoção não será limpo porque a propriedade DelayHoldApplied ainda está definida como **true**. O oposto também seria true: se DelayHoldApplied estiver definido como **false** e DelayReleaseHoldApplied estiver definido como **true**, somente os itens do Outlook marcados para remoção serão removidos.

## <a name="next-steps"></a>Próximas etapas

Após identificar as isenções aplicadas a uma caixa de correio, você pode executar tarefas como alterar a duração da retenção, remover temporariamente ou permanentemente a retenção ou excluir uma caixa de correio inativa de uma política de retenção do Office 365. Para obter mais informações sobre a execução de tarefas relacionadas a isenções, consulte um dos seguintes tópicos:

- Execute o comando [set-RetentionCompliancePolicy- \<AddExchangeLocationException User Mailbox>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps) no PowerShell do centro de conformidade e segurança & para excluir uma caixa de correio de uma política de retenção do Office 365 em toda a organização. Este comando só pode ser usado para políticas de retenção onde o valor da propriedade *ExchangeLocation* é `All`igual a.

- Execute o [GUID de retenção Set- \<Mailbox-ExcludeFromOrgHolds sem prefixo ou sufixo>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps) comando no PowerShell do Exchange Online para excluir uma caixa de correio inativa de uma política de retenção do Office 365 em toda a organização.

- [Alterar a duração da retenção para uma caixa de correio inativa no Office 365](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Excluir uma caixa de correio inativa no Office 365](delete-an-inactive-mailbox.md)

- [Excluir itens na pasta de Itens recuperáveis de caixas de correio baseadas em nuvem em retenção](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
