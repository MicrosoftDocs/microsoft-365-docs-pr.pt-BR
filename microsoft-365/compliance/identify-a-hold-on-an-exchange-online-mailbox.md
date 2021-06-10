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
description: Saiba como identificar os diferentes tipos de espera que podem ser colocados em uma caixa de correio Exchange Online no Microsoft 365.
ms.openlocfilehash: 0fdfbd4503a4ddffd2ce2dd97c6af42684aea293
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917531"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>Como identificar o tipo de retenção de uma caixa de correio do Exchange Online

Este artigo explica como identificar retém colocados em Exchange Online caixas de correio em Microsoft 365.

Microsoft 365 oferece várias maneiras de sua organização impedir que o conteúdo da caixa de correio seja excluído permanentemente. Isso permite que sua organização retenha conteúdo para atender aos regulamentos de conformidade ou durante as investigações legais e de outros tipos. Aqui está uma lista dos recursos de retenção (também chamados de *retenções*) no Office 365:

- **[Ressuito de litígio](create-a-litigation-hold.md):** Retém que são aplicados a caixas de correio de usuário em Exchange Online.

- **[Ressução de Descoberta e](create-ediscovery-holds.md):** Retém que estão associados a um caso core de Descoberta eDiscovery no centro de segurança e conformidade. Os retém de Descoberta Eletrônico podem ser aplicados às caixas de correio de usuário e à caixa de correio correspondente para Microsoft 365 Grupos e Microsoft Teams.

- **[Espera in-locar:](/Exchange/security-and-compliance/create-or-remove-in-place-holds)** Retém que são aplicados às caixas de correio de usuário usando In-Place ferramenta de & de Descoberta & no centro de administração do Exchange em Exchange Online. 

   > [!NOTE]
   > In-Place os respossos foram retirados e você não pode mais criar In-Place ou aplicá-los a caixas de correio. No entanto, In-Place os Holds ainda podem ser aplicados a caixas de correio em sua organização, razão pela qual elas estão incluídas neste artigo. Para obter mais informações, [consulte Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center).

- **[Microsoft 365 de retenção](retention.md):** Pode ser configurado para reter (ou reter e excluir) conteúdo em caixas de correio de usuário no Exchange Online e na caixa de correio correspondente para Microsoft 365 Grupos e Microsoft Teams. Você também pode criar uma política de retenção para manter Skype for Business Conversas, que são armazenadas em caixas de correio de usuário.

  Há dois tipos de políticas Microsoft 365 de retenção que podem ser atribuídas às caixas de correio.

    - **Políticas de retenção de localização específicas:** São políticas atribuídas aos locais de conteúdo de usuários específicos. Você usa o cmdlet **Get-Mailbox** no Exchange Online PowerShell para obter informações sobre políticas de retenção atribuídas a caixas de correio específicas. Para obter mais informações sobre esse tipo de política de retenção, consulte a seção Política A com inclusões ou exclusões [específicas](create-retention-policies.md#a-policy-with-specific-inclusions-or-exclusions) da documentação da política de retenção.

    - **Políticas de retenção em toda a organização:** Essas são as políticas atribuídas a todos os locais de conteúdo em sua organização. Você usa o cmdlet **Get-OrganizationConfig** no Exchange Online PowerShell para obter informações sobre políticas de retenção em toda a organização. Para obter mais informações sobre esse tipo de política de retenção, consulte a seção Política A que se aplica a locais [inteiros](create-retention-policies.md#a-policy-that-applies-to-entire-locations) da documentação da política de retenção.

- **[Microsoft 365](retention.md)** rótulos de retenção : se um usuário aplicar um rótulo de retenção do Microsoft 365 (um configurado para  reter conteúdo ou reter e excluir conteúdo) a qualquer pasta ou item em sua caixa de correio, uma retenção será colocada na caixa de correio como se a caixa de correio tivesse sido colocada em Retenção de Litígio ou atribuída a uma política de retenção Microsoft 365. Para obter mais informações, consulte a seção [Identificando](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) caixas de correio em espera porque um rótulo de retenção foi aplicado a uma pasta ou item neste artigo.

Para gerenciar caixas de correio em espera, talvez seja necessário identificar o tipo de retenção que é colocado em uma caixa de correio para que você possa executar tarefas como alterar a duração da retenção, remover temporaria ou permanentemente a retenção ou excluir uma caixa de correio de uma política de retenção de Microsoft 365. Nesses casos, a primeira etapa é identificar o tipo de espera colocada na caixa de correio. E como vários retém (e tipos diferentes de retém) podem ser colocados em uma única caixa de correio, você precisa identificar todas as restituições colocadas em uma caixa de correio se quiser remover ou alterar uma remoção.

## <a name="step-1-obtain-the-guid-for-holds-placed-on-a-mailbox"></a>Etapa 1: Obter o GUID para ressarvações colocadas em uma caixa de correio

Você pode executar os dois cmdlets a seguir no Exchange Online PowerShell para obter o GUID dos ressartices colocados em uma caixa de correio. Depois de obter um GUID, use-o para identificar a espera específica na Etapa 2. Uma Ressarção de Litígio não é identificada por um GUID. Os Retivedos de Litígio estão habilitados ou desabilitados para uma caixa de correio.

- **Get-Mailbox:** Use este cmdlet para determinar se a Retenção de Litígio está habilitada para uma caixa de correio e obter os GUIDs para retenções de Descoberta Eletrônica, In-Place Retenções e políticas de retenção Microsoft 365 que são especificamente atribuídas a uma caixa de correio. A saída desse cmdlet também indicará se uma caixa de correio foi explicitamente excluída de uma política de retenção em toda a organização.

- **Get-OrganizationConfig:** Use este cmdlet para obter os GUIDs para políticas de retenção em toda a organização.

Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

### <a name="get-mailbox"></a>Get-Mailbox

Execute o seguinte comando para obter informações sobre os retenções e Microsoft 365 de retenção aplicadas a uma caixa de correio.

```powershell
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> Se houver valores demais na propriedade InPlaceHolds e nem todos eles são exibidos, você pode executar o comando para exibir cada GUID em `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` uma linha separada.

A tabela a seguir descreve como identificar diferentes tipos de reter com base nos valores na propriedade *InPlaceHolds* quando você executar o cmdlet **Get-Mailbox.**

|Tipo de espera  |Valor de exemplo  |Como identificar a espera  |
|---------|---------|---------|
|Retenção de litígio     |    `True`     |     A responsabilidade de litígio é habilitada para uma caixa de correio quando a *propriedade LitigationHoldEnabled* é definida como `True` .    |
|Espera de Descoberta eDiscovery     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   A *propriedade InPlaceHolds* contém o GUID de qualquer reter associado a um caso de Descoberta Digital no centro de segurança e conformidade. Você pode dizer que se trata de uma ressarção de Descoberta E, pois o GUID começa com o `UniH` prefixo (que denota uma união de espera).      |
|Bloqueio In-loco     |     `c0ba3ce811b6432a8751430937152491` <br/> ou <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     A *propriedade InPlaceHolds* contém o GUID do In-Place que é colocado na caixa de correio. Você pode dizer que é um In-Place de espera porque o GUID não começa com um prefixo ou começa com o `cld` prefixo.     |
|Microsoft 365 de retenção especificamente aplicada à caixa de correio     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> ou <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     A propriedade InPlaceHolds contém GUIDs de qualquer política de retenção de local específica aplicada à caixa de correio. Você pode identificar políticas de retenção porque o GUID começa com `mbx` o ou o `skp` prefixo. O `skp` prefixo indica que a política de retenção é aplicada Skype for Business conversas na caixa de correio do usuário.    |
|Excluído de uma política de retenção de Microsoft 365 de toda a organização     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     Se uma caixa de correio for excluída de uma política de retenção de Microsoft 365 de toda a organização, o GUID da política de retenção da caixa de correio excluída será exibido na propriedade InPlaceHolds e será identificado pelo `-mbx` prefixo.    |

### <a name="get-organizationconfig"></a>Get-OrganizationConfig
Se a *propriedade InPlaceHolds* estiver vazia quando você executar o cmdlet **Get-Mailbox,** ainda poderá haver uma ou mais políticas de retenção de toda a organização Microsoft 365 aplicadas à caixa de correio. Execute o seguinte comando no Exchange Online PowerShell para obter uma lista de GUIDs para políticas de Microsoft 365 de retenção em toda a organização.

```powershell
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> Se houver valores demais na propriedade InPlaceHolds e nem todos eles são exibidos, você pode executar o comando para exibir cada GUID em `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` uma linha separada.

A tabela a seguir descreve os diferentes tipos de reter em toda a organização e como identificar cada tipo com base nos GUIDs contidos na propriedade *InPlaceHolds* ao executar o cmdlet **Get-OrganizationConfig.**

|Tipo de espera  |Valor de exemplo  |Descrição  |
|---------|---------|---------|
|Microsoft 365 de retenção aplicadas Exchange caixas de correio, Exchange pastas públicas e Teams chats    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   As políticas de retenção em toda a organização aplicadas Exchange caixas de correio, Exchange pastas públicas e chats 1xN no Microsoft Teams são identificadas por GUIDs que começam com o `mbx` prefixo. Observação Os chats 1xN são armazenados na caixa de correio dos participantes de chat individuais.      |
|Microsoft 365 política de retenção aplicada a Microsoft 365 Grupos e Teams de canal     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    As políticas de retenção em toda a organização aplicadas Microsoft 365 grupos e mensagens de canal no Microsoft Teams são identificadas por GUIDs que começam com o `grp` prefixo. Observe que as mensagens de canal são armazenadas na caixa de correio de grupo associada a uma Equipe da Microsoft.     |

Para obter mais informações sobre políticas de retenção aplicadas Microsoft Teams, [consulte Learn about retention policies for Microsoft Teams](retention-policies-teams.md).

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>Noções básicas sobre o formato do valor InPlaceHolds para políticas de retenção

Além do prefixo (mbx, skp ou grp) que identifica um item na propriedade InPlaceHolds como uma política de retenção Microsoft 365, o valor também contém um sufixo que identifica o tipo de ação de retenção configurada para a política. Por exemplo, o sufixo de ação é realçado em negrito nos seguintes exemplos:

   `skp127d7cf1076947929bf136b7a2a8c36f`**:1**

   `mbx7cfb30345d454ac0a989ab3041051209`**:2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**:3**

A tabela a seguir define as três ações de retenção possíveis:

|Valor  |Descrição  |
|---------|---------|
|**1**     | Indica que a política de retenção está configurada para excluir itens. A política não retém itens.        |
|**2**    |    Indica que a política de retenção está configurada para manter itens. A política não exclui itens depois que o período de retenção expira.     |
|**3**     |   Indica que a política de retenção está configurada para retená-los e excluí-los depois que o período de retenção expirar.      |

Para obter mais informações sobre ações de retenção, consulte [a seção Reter conteúdo para um período específico de](create-retention-policies.md#retaining-content-for-a-specific-period-of-time) tempo.
   
## <a name="step-2-use-the-guid-to-identify-the-hold"></a>Etapa 2: Usar o GUID para identificar a espera

Depois de obter o GUID para uma ressarção aplicada a uma caixa de correio, a próxima etapa é usar esse GUID para identificar a espera. As seções a seguir mostram como identificar o nome da espera (e outras informações) usando o GUID de espera.

### <a name="ediscovery-holds"></a>Bloqueios de Descoberta Eletrônica

Execute os seguintes comandos no Centro de Conformidade & e Segurança do PowerShell para identificar uma ressarção de Descoberta Eletrônico aplicada à caixa de correio. Use o GUID (sem incluir o prefixo UniH) para a isenção de Descoberta e que você identificou na Etapa 1. 

Para se conectar ao Centro de Conformidade & Segurança do PowerShell, consulte [Conexão security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).

O primeiro comando cria uma variável que contém informações sobre a espera. Essa variável é usada nos outros comandos. O segundo comando exibe o nome da ocorrência de Descoberta e à que a responsabilidade está associada. O terceiro comando exibe o nome da ressarção e uma lista das caixas de correio às que a espera se aplica.

```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold | FL Name,ExchangeLocation
```

### <a name="in-place-holds"></a>Bloqueio In-loco

Execute o seguinte comando no Exchange Online PowerShell para identificar o In-Place que é aplicado à caixa de correio. Use o GUID para a In-Place que você identificou na Etapa 1. O comando exibe o nome da ressarção e uma lista das caixas de correio às que a espera se aplica.

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```

Se o GUID da In-Place de espera começar com o prefixo, certifique-se de incluir o `cld` prefixo ao executar o comando anterior.

> [!IMPORTANT]
> À medida que continuamos a investir em diferentes maneiras de preservar o conteúdo da caixa de correio, anunciamos a ressarção do In-Place Holds no centro de administração Exchange (EAC). A partir de 1º de julho de 2020, você não poderá criar novos In-Place de Exchange Online. Mas você ainda poderá gerenciar os In-Place no EAC ou usando o cmdlet **Set-MailboxSearch** no Exchange Online PowerShell. No entanto, a partir de 1º de outubro de 2020, você não poderá gerenciar In-Place Holds. Você só os removerá no EAC ou usando o cmdlet **Remove-MailboxSearch.** Para obter mais informações sobre a aposentadoria de In-Place Detém, consulte A aposentadoria de ferramentas [de Descoberta eDiscovery herdado.](legacy-ediscovery-retirement.md)

### <a name="microsoft-365-retention-policies"></a>Microsoft 365 de retenção

Execute o seguinte comando no & Centro de Conformidade e Segurança do PowerShell para identificar a política de retenção Microsoft 365 (local específico ou em toda a organização) aplicada à caixa de correio. Use o GUID (sem incluir o prefixo mbx, skp ou grp ou o sufixo de ação) identificado na Etapa 1.

```powershell
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a>Identificar caixas de correio em espera porque um rótulo de retenção foi aplicado a uma pasta ou item

Sempre que um usuário aplica um rótulo de retenção configurado para reter ou reter conteúdo e, em seguida, excluir conteúdo a qualquer pasta ou item em sua caixa de correio, a propriedade de caixa de correio *ComplianceTagHoldApplied* é definida como **True**. Quando isso acontece, a caixa de correio é considerada em retenção, como se ela tivesse sido colocada em Retenção de Litígio ou atribuída a uma política de retenção Microsoft 365 de retenção. Quando a *propriedade ComplianceTagHoldApplied* estiver definida como **True,** as seguintes coisas poderão ocorrer:

- Se a caixa de correio ou a conta de usuário do usuário for excluída, a caixa de correio se tornará [uma caixa de correio inativa.](inactive-mailboxes-in-office-365.md)
- Não é possível desabilitar a caixa de correio (a caixa de correio principal ou a caixa de correio de arquivo morto, se ela estiver habilitada).
- Os itens na caixa de correio podem ser mantidos por mais tempo do que o esperado. Isso porque a caixa de correio está em espera e, portanto, nenhum item é excluído permanentemente (limpo).

Para exibir o valor da *propriedade ComplianceTagHoldApplied,* execute o seguinte comando no Exchange Online PowerShell:

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

Para obter mais informações sobre rótulos de retenção, consulte [rótulos de retenção](retention.md#retention-labels).

## <a name="managing-mailboxes-on-delay-hold"></a>Gerenciando caixas de correio em espera

Depois que qualquer tipo de espera é removida de uma caixa de correio, uma espera *de atraso* é aplicada. Isso significa que a remoção real da responsabilidade é adiada por 30 dias para impedir que os dados são excluídos permanentemente (apagados) da caixa de correio. Isso oferece aos administradores a oportunidade de pesquisar ou recuperar itens de caixa de correio que serão limpos após a remoção de uma responsabilidade. Uma espera de atraso é colocada em uma caixa de correio na próxima vez que o Assistente de Pasta Gerenciada processa a caixa de correio e detecta que uma espera foi removida. Especificamente, um atraso é aplicado a uma caixa de correio quando o Assistente de Pasta Gerenciada define uma das seguintes propriedades de caixa de correio como **True**:

- **DelayHoldApplied:** Essa propriedade se aplica ao conteúdo relacionado a email (gerado por pessoas que usam Outlook e Outlook na Web) que são armazenados na caixa de correio de um usuário.

- **DelayReleaseHoldApplied:** Essa propriedade se aplica ao conteúdo baseado em nuvem (gerado por aplicativos que não Outlook como Microsoft Teams, Microsoft Forms e Microsoft Yammer) armazenados na caixa de correio de um usuário. Os dados de nuvem gerados por um aplicativo Microsoft geralmente são armazenados em uma pasta oculta na caixa de correio de um usuário.

Quando um atraso é colocado na caixa de correio (quando uma das propriedades anteriores é definida como **True**), a caixa de correio ainda é considerada em espera por uma duração de espera ilimitada, como se a caixa de correio estivesse em Contencioso. Após 30 dias, a espera de atraso expira e o Microsoft 365 tentará remover automaticamente a espera (definindo a propriedade DelayHoldApplied ou DelayReleaseHoldApplied como **False**) para que a suspensão seja removida. Depois que uma dessas propriedades for definida como **False**, os itens correspondentes marcados para remoção serão limpos na próxima vez que a caixa de correio for processada pelo Assistente de Pasta Gerenciada.

Para exibir os valores das propriedades DelayHoldApplied e DelayReleaseHoldApplied para uma caixa de correio, execute o seguinte comando no Exchange Online PowerShell.

```powershell
Get-Mailbox <username> | FL *HoldApplied*
```

Para remover a espera de atraso antes de expirar, você pode executar um (ou ambos) comandos a seguir no Exchange Online PowerShell, dependendo de qual propriedade você deseja alterar:

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

Ou

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

Você deve ter a função de Responsabilidade Legal Exchange Online usar os parâmetros *RemoveDelayHoldApplied* ou *RemoveDelayReleaseHoldApplied.* 

Para remover a espera de atraso em uma caixa de correio inativa, execute um dos seguintes comandos no Exchange Online PowerShell:

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

Ou

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayReleaseHoldApplied
```

> [!TIP]
> A melhor maneira de especificar uma caixa de correio inativa no comando anterior é usar seu nome diferenciado ou Exchange GUID. Usar um desses valores ajuda a evitar a especificação acidental da caixa de correio errada. 

Para obter mais informações sobre como usar esses parâmetros para gerenciar restituições de atraso, consulte [Set-Mailbox](/powershell/module/exchange/set-mailbox).

Lembre-se das seguintes coisas ao gerenciar uma caixa de correio em espera:

- Se a propriedade DelayHoldApplied ou DelayReleaseHoldApplied estiver definida como **True** e uma caixa de correio (ou a conta de usuário correspondente) for excluída, a caixa de correio se tornará uma caixa de correio inativa. Isso acontece porque uma caixa de correio é considerada em espera se uma das propriedades estiver definida como **True** e a exclusão de uma caixa de correio em espera resulta em uma caixa de correio inativa. Para excluir uma caixa de correio e não torná-la uma caixa de correio inativa, você precisa definir ambas as propriedades como **False**.

- Como dito anteriormente, uma caixa de correio será considerada em espera por uma duração de espera ilimitada se a propriedade DelayHoldApplied ou DelayReleaseHoldApplied estiver definida como **True**. No entanto, isso não significa que *todo o* conteúdo na caixa de correio seja preservado. Depende do valor definido para cada propriedade. Por exemplo, digamos que ambas as propriedades estão definidas como **True** porque as restituições são removidas da caixa de correio. Em seguida, você remove apenas o atraso que é aplicado a dados de nuvem não Outlook (usando o *parâmetro RemoveDelayReleaseHoldApplied).* Na próxima vez que o Assistente de Pasta Gerenciada processa a caixa de correio, os itens que não Outlook marcados para remoção são limpos. Qualquer Outlook itens marcados para remoção não será limpo porque a propriedade DelayHoldApplied ainda está definida como **True**. O oposto também seria verdadeiro: se DelayHoldApplied estiver definido como **False** e DelayReleaseHoldApplied estiver definido como **True,** somente Outlook itens marcados para remoção seriam limpos.

## <a name="next-steps"></a>Próximas etapas

Depois de identificar os retenções que são aplicados a uma caixa de correio, você pode executar tarefas como alterar a duração da retenção, remover temporaria ou permanentemente a retenção ou excluir uma caixa de correio inativa de uma política de retenção Microsoft 365. Para obter mais informações sobre a execução de tarefas relacionadas a retém, consulte um dos seguintes tópicos:

- Execute o [comando Set-RetentionCompliancePolicy \<Policy Name> -Identity -AddExchangeLocationEx & ception \<user mailbox> ](/powershell/module/exchange/set-retentioncompliancepolicy) no Centro de Conformidade e Segurança do PowerShell para excluir uma caixa de correio de uma política de retenção Microsoft 365 toda a organização. Esse comando só pode ser usado para políticas de retenção em que o valor da *propriedade ExchangeLocation* é igual `All` a .

- [Alterar a duração de retenção de uma caixa de correio inativa](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Excluir uma caixa de correio inativa](delete-an-inactive-mailbox.md)

- [Excluir itens na pasta de Itens recuperáveis de caixas de correio baseadas em nuvem em retenção](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)