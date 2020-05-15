---
title: Excluir itens na pasta caixa de correio de nuvem em suspender itens recuperáveis-ajuda do administrador
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
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
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: 'Para administradores: excluir itens na pasta itens recuperáveis de um usuário para uma caixa de correio do Exchange Online, mesmo se essa caixa de correio for colocada em retenção legal. Essa é uma maneira eficaz de excluir dados que foram desfeitos acidentalmente no Microsoft 365.'
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 223c589d191eef14662b7e19aa5ed113db9ff3b2
ms.sourcegitcommit: 252b1d1d8ae735b99bf46e27c08353afc330aef3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232047"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a>Excluir itens da pasta itens recuperáveis das caixas de correio baseadas em nuvem em manter ajuda do administrador

A pasta itens recuperáveis para uma caixa de correio do Exchange Online existe para proteger contra exclusões acidentais ou mal-intencionadas. Também é usado para armazenar itens que são retidos e acessados por recursos de conformidade, como pesquisas de isenções e de descoberta eletrônica. No entanto, em algumas situações, as organizações podem ter dados que são retidos acidentalmente na pasta itens recuperáveis que devem ser excluídos. Por exemplo, um usuário pode enviar ou encaminhar uma mensagem de email que contenha informações confidenciais ou informações que possam ter sérias conseqüências de negócios. Mesmo que a mensagem seja excluída permanentemente, ela pode ser retida indefinidamente porque uma retenção legal foi colocada na caixa de correio. Este cenário é conhecido como dados derramamento porque os dados foram desfeitos acidentalmente no Office 365. Nessas situações, você pode excluir itens na pasta itens recuperáveis de um usuário para uma caixa de correio do Exchange Online, mesmo que essa caixa de correio seja colocada em espera com um dos diferentes recursos de retenção no Office 365. Esses tipos de isenções incluem bloqueios de litígio, isenções in-loco, retenções de descoberta eletrônica e políticas de retenção criadas no centro de segurança e conformidade do Office 365 ou Microsoft 365.
  
 Este artigo explica como excluir itens da pasta itens recuperáveis para caixas de correio baseadas em nuvem que estão em espera. Este procedimento envolve desabilitar o acesso à caixa de correio e desabilitar a recuperação de item único, desabilitar o assistente de pasta gerenciada do processamento da caixa de correio, removendo temporariamente a retenção, excluindo itens da pasta itens recuperáveis e, em seguida, revertendo a caixa de correio para sua configuração anterior. Este é o processo: 
  
[Etapa 1: coletar informações sobre a caixa de correio](#step-1-collect-information-about-the-mailbox)

[Etapa 2: preparar a caixa de correio](#step-2-prepare-the-mailbox)

[Etapa 3: remover todas as isenções da caixa de correio](#step-3-remove-all-holds-from-the-mailbox)

[Etapa 4: remover o atraso no bloqueio da caixa de correio](#step-4-remove-the-delay-hold-from-the-mailbox)

[Etapa 5: excluir itens na pasta itens recuperáveis](#step-5-delete-items-in-the-recoverable-items-folder)

[Etapa 6: reverter a caixa de correio para o estado anterior](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> Os procedimentos descritos neste artigo resultarão na exclusão permanente de dados (removidos) de uma caixa de correio do Exchange Online. Isso significa que as mensagens excluídas da pasta itens recuperáveis não podem ser recuperadas e não estarão disponíveis para descoberta legal ou outros fins de conformidade. Se você deseja excluir mensagens de uma caixa de correio que é colocada em espera como parte de uma retenção de litígio, bloqueio in-loco, retenção de descoberta eletrônica ou política de retenção criada no centro de segurança e conformidade, consulte seu gerenciamento de registros ou departamentos legais antes de remover a retenção. Sua organização pode ter uma política que define se uma caixa de correio em espera ou um incidente de derramamento de dados tem prioridade. 
  
## <a name="before-you-begin"></a>Antes de começar

- Para criar e executar uma pesquisa de conteúdo, você precisa ser membro do grupo de funções Gerente de Descoberta Eletrônica ou receber a função de gerenciamento de Pesquisa de Conformidade. Para excluir mensagens, você precisa ser membro do grupo de funções Gerenciamento da Organização ou receber a função de gerenciamento Pesquisa e Limpar. Para saber mais sobre como adicionar usuários a um grupo de função, confira [Atribuir permissões de Descoberta Eletrônica no Centro de Segurança e Conformidade](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions).

- O procedimento descrito neste artigo não tem suporte para caixas de correio inativas. Isso ocorre porque não é possível reaplicar uma retenção (ou uma diretiva de retenção) a uma caixa de correio inativa após removê-la. Quando você remove uma retenção de uma caixa de correio inativa, ela é alterada para uma caixa de correio normal excluída por software e será excluída permanentemente da sua organização depois de ser processada pelo assistente de pasta gerenciada.

- Você não pode executar esse procedimento para uma caixa de correio que foi atribuída a uma política de retenção que foi bloqueada com um bloqueio de preservação. Isso ocorre porque um bloqueio de preservação impede que você remova ou exclua a caixa de correio da política de retenção e desabilite o assistente de pasta gerenciada na caixa de correio. Para obter mais informações sobre o bloqueio de políticas de retenção, consulte [use preservação Lock para cumprir os requisitos normativos](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements).

- Se uma caixa de correio não for colocada em espera (ou não tiver a recuperação de item único habilitada), você poderá excluir os itens da pasta itens recuperáveis. Para obter mais informações sobre como fazer isso, confira [Pesquisar e excluir mensagens de email em sua organização](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization).
  
## <a name="step-1-collect-information-about-the-mailbox"></a>Etapa 1: coletar informações sobre a caixa de correio

Essa primeira etapa é coletar as propriedades selecionadas da caixa de correio de destino que afetem esse procedimento. Certifique-se de anotar essas configurações ou salvá-las em um arquivo de texto porque você alterará algumas dessas propriedades e reverterá para os valores originais na etapa 6, após excluir itens da pasta itens recuperáveis. Veja a seguir uma lista das propriedades de caixa de correio que você precisa coletar.
  
- *SingleItemRecoveryEnabled* e *RetainDeletedItemsFor*. Se necessário, você desabilitará a recuperação única e aumentará o período de retenção de itens excluídos na etapa 3. 

- *LitigationHoldEnabled* e *InPlaceHolds*. Você precisa identificar todas as suspensões colocadas na caixa de correio para que possa removê-las temporariamente na etapa 3. Consulte a seção [mais informações](#more-information) para obter dicas sobre como identificar a retenção de tipo que pode ser colocada em uma caixa de correio. 

Além disso, é necessário obter as configurações de acesso do cliente da caixa de correio para que você possa desabilitá-las temporariamente para que o proprietário (ou outros usuários) não possa acessar a caixa de correio durante esse procedimento. Por fim, você pode obter o tamanho atual e o número de itens na pasta itens recuperáveis. Após excluir itens da pasta itens recuperáveis na etapa 5, você usará essas informações para verificar se os itens foram removidos.
  
1. [Conectar-se ao Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). Certifique-se de usar um nome de usuário e senha para uma conta de administrador que tenha sido atribuída às funções de gerenciamento apropriadas no Exchange Online. 
    
2. Execute o seguinte comando para obter informações sobre a recuperação de item único e o período de retenção de item excluído.

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   Se a recuperação de item único estiver habilitada, você terá que desabilitá-lo na etapa 2. Se o período de retenção de itens excluídos não estiver definido por 30 dias (o valor máximo no Exchange Online), você poderá aumentá-lo na etapa 2. 
    
3. Execute o seguinte comando para obter as configurações de acesso à caixa de correio para a caixa de correio. 
    
    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   Você desabilitará todos esses métodos de acesso na etapa 2.
    
4. Execute o seguinte comando para obter informações sobre as políticas de retenção e isenções aplicadas à caixa de correio.
    
    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > Se houver muitos valores na propriedade *InPlaceHolds* e nem todos eles forem exibidos, você poderá executar o `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` comando para exibir cada valor em uma linha separada. 
  
5. Execute o comando a seguir para obter informações sobre as políticas de retenção em toda a organização. 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   
   Se sua organização tiver políticas de retenção em toda a organização, você terá que excluir a caixa de correio dessas políticas na etapa 3.

   > [!TIP]
    > Se houver muitos valores na propriedade *InPlaceHolds* e nem todos eles forem exibidos, você poderá executar o `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` comando para exibir cada valor em uma linha separada. 
  
6. Execute o seguinte comando para obter o tamanho atual e o número total de itens em pastas e subpastas na pasta itens recuperáveis na caixa de correio principal do usuário. 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Se a caixa de correio de arquivo morto do usuário estiver habilitada, execute o seguinte comando para obter o tamanho e o número total de itens em pastas e subpastas na pasta itens recuperáveis em suas caixas de correio de arquivo morto. 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Ao excluir itens na etapa 5, você pode optar por excluir ou não excluir itens da pasta itens recuperáveis na caixa de correio de arquivo morto principal do usuário. Se o arquivamento de expansão automática estiver habilitado para a caixa de correio, os itens em uma caixa de correio de arquivo morto auxiliar não serão excluídos.
  
## <a name="step-2-prepare-the-mailbox"></a>Etapa 2: preparar a caixa de correio

Após coletar e salvar informações sobre a caixa de correio, a próxima etapa é preparar a caixa de correio executando as seguintes tarefas: 
  
- **Desabilitar o acesso do cliente à caixa de correio** para que o proprietário da caixa de correio não possa acessar a caixa de correio e fazer quaisquer alterações nos dados da caixa de correio durante esse procedimento. 
    
- **Aumente o período de retenção de itens excluídos** para 30 dias (o valor máximo no Exchange Online) para que os itens não sejam removidos da pasta itens recuperáveis antes que você possa excluí-los na etapa 5. 
    
- **Desabilitar a recuperação de item único** para que os itens não sejam retidos (pela duração do período de retenção do item excluído) depois de excluí-los da pasta itens recuperáveis na etapa 5. 
    
- **Desative o assistente de pasta gerenciada** para que ele não processe a caixa de correio e mantenha os itens excluídos na etapa 5. 
    
Execute as etapas a seguir no PowerShell do Exchange Online.
  
1. Execute o comando a seguir para desabilitar todo o acesso do cliente à caixa de correio. A sintaxe do comando pressupõe que todos os métodos de acesso para cliente foram habilitados na caixa de correio.

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

   > [!NOTE]
    > Pode levar até 60 minutos para desabilitar todos os métodos de acesso para cliente para a caixa de correio. Observe que desabilitar esses métodos de acesso não desconectará o proprietário da caixa de correio no qual está conectado no momento. Se o proprietário não estiver conectado, não será possível acessar a caixa de correio após a desabilitação dos métodos de acesso. 
  
2. Execute o seguinte comando para aumentar o período de retenção de item excluído no máximo 30 dias. Isso pressupõe que a configuração atual é inferior a 30 dias. 

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. Execute o comando a seguir para desabilitar a recuperação de item único.
    
    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > Pode levar até 60 minutos para desabilitar a recuperação de item único. Não exclua itens na pasta itens recuperáveis até que esse período tenha decorrido. 
  
4. Execute o comando a seguir para impedir que o assistente de pasta gerenciada processe a caixa de correio. Conforme explicado anteriormente, você pode desabilitar o assistente de pasta gerenciada somente se uma política de retenção com bloqueio de preservação não for aplicada à caixa de correio. 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>Etapa 3: remover todas as isenções da caixa de correio

A última etapa para que você possa excluir itens da pasta itens recuperáveis é remover todas as isenções (que você identificou na etapa 1) colocadas na caixa de correio. Todas as isenções devem ser removidas para que os itens não sejam retidos após serem excluídos da pasta itens recuperáveis. As seções a seguir contêm informações sobre como remover diferentes tipos de bloqueios em uma caixa de correio. Consulte a seção [mais informações](#more-information) para obter dicas sobre como identificar a retenção de tipo que pode ser colocada em uma caixa de correio. Para obter mais informações, consulte [como identificar o tipo de retenção colocado em uma caixa de correio do Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md).
  
> [!CAUTION]
> Conforme mencionado anteriormente, confira o gerenciamento de registros ou os departamentos legais antes de remover uma retenção de uma caixa de correio. 
  
 ### <a name="litigation-hold"></a>Retenção de litígio
  
Execute o seguinte comando no PowerShell do Exchange Online para remover uma retenção de litígio da caixa de correio.

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> Semelhante à desabilitação dos métodos de acesso para cliente e recuperação de item único, pode levar até 60 minutos para remover a retenção de litígio. Não exclua itens da pasta itens recuperáveis até que esse período tenha decorrido. 
  
 ### <a name="in-place-hold"></a>Bloqueio In-loco
  
Execute o seguinte comando no PowerShell do Exchange Online para identificar o bloqueio in-loco colocado na caixa de correio. Use o GUID do bloqueio in-loco identificado na etapa 1. 

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

Após identificar o bloqueio in-loco, você pode usar o centro de administração do Exchange (Eat) ou o PowerShell do Exchange Online para remover a caixa de correio da isenção. Para mais informações, consulte [Criar ou remover um bloqueio In-loco](https://go.microsoft.com/fwlink/?linkid=852668).
  
 ### <a name="retention-policies-applied-to-specific-mailboxes"></a>Políticas de retenção aplicadas a caixas de correio específicas
  
Execute o seguinte comando no [PowerShell do centro de conformidade e segurança &](https://go.microsoft.com/fwlink/?linkid=627084) para identificar a política de retenção aplicada à caixa de correio. Use o GUID (não incluindo o `mbx` `skp` prefixo ou) para a política de retenção que você identificou na etapa 1. 

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

Depois de identificar a política de retenção, vá para a página retenção de **governança de informações** \> **Retention** no centro de conformidade & segurança, edite a política de retenção que você identificou na etapa anterior e remova a caixa de correio da lista de destinatários que estão incluídos na política de retenção. 
  
 ### <a name="organization-wide-retention-policies"></a>Políticas de retenção em toda a organização
  
Políticas de retenção em toda a organização e no Exchange são aplicadas a todas as caixas de correio na organização. Eles são aplicados no nível da organização (não no nível da caixa de correio) e são retornados quando você executa o cmdlet **Get-OrganizationConfig** na etapa 1. Execute o seguinte comando no [PowerShell do centro de conformidade e segurança &](https://go.microsoft.com/fwlink/?linkid=627084) para identificar as políticas de retenção em toda a organização. Use o GUID (não incluindo o `mbx` prefixo) para as políticas de retenção em toda a organização que você identificou na etapa 1. 

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

Após identificar as políticas de retenção em toda a organização, vá para a página retenção de **governança de informações** \> **Retention** no centro de conformidade & segurança, edite cada política de retenção em toda a organização que você identificou na etapa anterior e adicione a caixa de correio à lista de destinatários excluídos. Isso removerá a caixa de correio do usuário da política de retenção. 

### <a name="retention-labels"></a>Rótulos de retenção

Sempre que um usuário aplica um rótulo que é configurado para reter conteúdo ou reter e, em seguida, excluir conteúdo para qualquer pasta ou item em suas caixas de correio, a propriedade de caixa de correio *ComplianceTagHoldApplied* é definida como **true**. Quando isso acontece, a caixa de correio é considerada em espera, como se fosse colocada em retenção de litígio ou atribuída a uma política de retenção.

Para exibir o valor da propriedade *ComplianceTagHoldApplied* , execute o seguinte comando no PowerShell do Exchange Online:

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

Após identificar que uma caixa de correio está em espera porque um rótulo de retenção é aplicado a uma pasta ou item, você pode usar a ferramenta de pesquisa de conteúdo no centro de segurança e conformidade para pesquisar itens rotulados usando a condição de pesquisa ComplianceTag. Para obter mais informações, consulte a seção "condições de pesquisa" em [consultas de palavra-chave e condições de pesquisa para pesquisa de conteúdo](keyword-queries-and-search-conditions.md#conditions-for-common-properties).

Para saber mais sobre rótulos, confira [Visão geral dos rótulos](labels.md).

 ### <a name="ediscovery-holds"></a>bloqueios de descoberta eletrônica
  
Execute os seguintes comandos no [PowerShell do centro de conformidade e segurança &](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) para identificar o bloqueio associado a um caso de descoberta eletrônica (chamado de *descoberta eletrônica segura*) que é aplicado à caixa de correio. Use o GUID (não incluindo o `UniH` prefixo) para o bloqueio de descoberta eletrônica que você identificou na etapa 1. O segundo comando exibe o nome da ocorrência de descoberta eletrônica à qual a retenção está associada; o terceiro comando exibe o nome da retenção. 
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

Após identificar o nome do caso de descoberta eletrônica e a retenção, vá para a página descoberta eletrônica de **descoberta eletrônica** \> **eDiscovery** no centro de conformidade, abra o caso e remova a caixa de correio da isenção. Para obter mais informações sobre como identificar bloqueios de descoberta eletrônica, consulte a seção "isenções de descoberta eletrônica" em [como identificar o tipo de retenção colocado em uma caixa de correio do Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds).
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>Etapa 4: remover o atraso no bloqueio da caixa de correio

Após qualquer tipo de retenção ser removido de uma caixa de correio, o valor da propriedade de caixa de correio *DelayHoldApplied* ou *DelayReleaseHoldApplied* é definido como **true**. Isso ocorre na próxima vez que o assistente de pasta gerenciada processa a caixa de correio e detecta que uma retenção foi removida. Isso é chamado de *espera de atraso* e significa que a remoção real da retenção está atrasada por 30 dias para evitar que os dados sejam excluídos permanentemente da caixa de correio. (O objetivo de um atraso na espera é dar aos administradores uma oportunidade de Pesquisar ou recuperar itens de caixa de correio que serão removidos após a remoção de uma retenção.)  Quando um atraso de espera é colocado na caixa de correio, a caixa de correio ainda é considerada em espera por uma duração ilimitada, como se a caixa de correio estivesse em retenção de litígio. Após 30 dias, o atraso esperado expira e o Microsoft 365 tentará automaticamente remover o atraso de espera (definindo a propriedade *DelayHoldApplied* ou *DelayReleaseHoldApplied* como **false**) para que a retenção seja removida. Para obter mais informações sobre uma espera de atraso, consulte a seção "Gerenciando caixas de correio em espera de atraso" em [como identificar o tipo de retenção colocado em uma caixa de correio do Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).

Antes de poder excluir itens na etapa 5, você precisa remover um atraso de retenção da caixa de correio. Primeiro, determine se a espera de atraso é aplicada à caixa de correio executando o seguinte comando no PowerShell do Exchange Online:

```powershell
Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
```

Se o valor da propriedade *DelayHoldApplied* ou *DelayReleaseHoldApplied* for definido como **false**, uma espera de atraso não foi colocada na caixa de correio. Você pode ir para a etapa 5 e excluir itens na pasta itens recuperáveis.

Se o valor da propriedade *DelayHoldApplied* ou *DelayReleaseHoldApplied* for definido como **true**, execute um dos seguintes comandos para remover o atraso de espera:

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

Ou

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

Você deve receber a função de retenção legal no Exchange Online para usar o parâmetro *RemoveDelayHoldApplied* ou *RemoveDelayReleaseHoldApplied* .

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>Etapa 5: excluir itens na pasta itens recuperáveis

Agora, você está pronto para excluir itens na pasta itens recuperáveis usando os cmdlets [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch) e [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction) no centro de conformidade de & de segurança. 

Para fazer isso, confira [Pesquisar e excluir mensagens de email](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization).

### <a name="verify-that-items-were-deleted"></a>Verificar se os itens foram excluídos

Para verificar se você excluiu com êxito itens da pasta itens recuperáveis de uma caixa de correio, use o cmdlet **Get-MailboxFolderStatistics** no PowerShell do Exchange Online para verificar o tamanho e o número de itens na pasta itens recuperáveis. Você pode comparar essas estatísticas com as que você coletou na etapa 1. 
  
Execute o seguinte comando em para obter o tamanho atual e o número total de itens em pastas e subpastas na pasta itens recuperáveis na caixa de correio principal do usuário. 
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

Execute o seguinte comando para obter o tamanho e o número total de itens em pastas e subpastas na pasta itens recuperáveis na caixa de correio de arquivo morto do usuário. 

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a>Etapa 6: reverter a caixa de correio para o estado anterior

A etapa final é reverter a caixa de correio de volta à configuração anterior. Isso significa redefinir as propriedades que você alterou na etapa 2 e reaplicar as suspensões que foram removidas na etapa 3. Isso inclui:
  
- Alterar o período de retenção do item excluído de volta para o valor anterior. Como alternativa, você pode simplesmente deixar esse conjunto como 30 dias, o valor máximo no Exchange Online.
    
- Reabilitar a recuperação de item único.
    
- Habilitar novamente os métodos de acesso para cliente para que o proprietário possa acessar a caixa de correio.
    
- Reaplicar as políticas de retenção e retenção que foram removidas.
    
- Habilitar novamente o assistente de pasta gerenciada para processar a caixa de correio.
    
> [!IMPORTANT]
> Recomendamos que você Aguarde 24 horas depois de aplicar novamente uma política de retenção ou retenção (e verificar se ela está funcionando) antes de reabilitar o assistente de pasta gerenciada para processar a caixa de correio. 
  
Execute as seguintes etapas (na sequência especificada) no PowerShell do Exchange Online.
  
1. Execute o seguinte comando para alterar o período de retenção do item excluído de volta para seu valor original. Isso pressupõe que a configuração anterior tenha menos de 30 dias; por exemplo, 14 dias. 
    
    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```

2. Execute o seguinte comando para reabilitar a recuperação de item único.
   
    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. Execute o seguinte comando para reabilitar todos os métodos de acesso para cliente para a caixa de correio.
    
    ```powershell
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```

4. Reaplique as isenções que foram removidas na etapa 3. Dependendo do tipo de retenção, use um dos procedimentos a seguir.
    
    **Retenção de litígio**
    
    Execute o seguinte comando para reabilitar uma retenção de litígio para a caixa de correio.
    
    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **Retenção Local**
    
    Use o Eat (ou o PowerShell do Exchange Online) para adicionar a caixa de correio de volta ao bloqueio in-loco. 
    
    **Políticas de retenção aplicadas a caixas de correio específicas**
    
    Use o centro de conformidade & segurança para adicionar a caixa de correio de volta à política de retenção. Vá para a página retenção de **governança de informações** \> **Retention** no centro de conformidade & segurança, edite a política de retenção e adicione a caixa de correio de volta à lista de destinatários aos quais a política de retenção é aplicada. 
    
    **Políticas de retenção em toda a organização**
    
    Se você removeu uma política de retenção em toda a organização ou em todo o Exchange excluindo-a da política, use o centro de conformidade de & de segurança para remover a caixa de correio da lista de usuários excluídos. Vá para a página retenção de **governança de informações** \> **Retention** no centro de conformidade & segurança, edite a política de retenção em toda a organização e remova a caixa de correio da lista de destinatários excluídos. Isso reaplicará a política de retenção à caixa de correio do usuário. 
    
    **retenção de ocorrência de descoberta eletrônica**
    
    Use o centro de conformidade & segurança para adicionar a caixa de correio de volta à retenção associada a um caso de descoberta eletrônica. Vá para a página descoberta eletrônica de descoberta **eletrônica** \> **eDiscovery** , abra o caso e adicione a caixa de correio de volta à isenção. 
    
5. Execute o seguinte comando para permitir que o assistente de pasta gerenciada processe a caixa de correio novamente. Conforme mencionado anteriormente, recomendamos que você espere 24 horas após a reaplicação de uma política de retenção ou retenção (e verifique se ela está no lugar) antes de reabilitar o assistente de pasta gerenciada. 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. Para verificar se a caixa de correio foi revertida para a configuração anterior, você pode executar os seguintes comandos e comparar as configurações com as que você coletou na etapa 1.

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a>Mais informações

Aqui está uma tabela que descreve como identificar diferentes tipos de isenções com base nos valores da propriedade *InPlaceHolds* quando você executa os cmdlets **Get-Mailbox** ou **Get-OrganizationConfig** . Para obter informações mais detalhadas, consulte [como identificar o tipo de retenção colocado em uma caixa de correio do Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md).

Conforme explicado anteriormente, você tem que remover todas as políticas de retenção e retenção de uma caixa de correio antes de poder excluir itens com êxito na pasta itens recuperáveis. 
  
|**Tipo de bloqueio**|**Valor de Exemplo**|**Como identificar a isenção**|
|:-----|:-----|:-----|
|Retenção de litígio  <br/> | `True` <br/> |A propriedade *LitigationHoldEnabled* está definida como `True` .  <br/> |
|Bloqueio In-loco  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |A propriedade *InPlaceHolds* contém o GUID do bloqueio in-loco colocado na caixa de correio. É possível dizer que isso é um bloqueio in-loco porque o GUID não começa com um prefixo.  <br/> Você pode usar o `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` comando no PowerShell do Exchange Online para obter informações sobre o bloqueio in-loco da caixa de correio.  <br/> |
| Políticas de retenção no centro de conformidade & segurança aplicado a caixas de correio específicas  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> ou  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |Quando você executa o cmdlet **Get-Mailbox** , a propriedade *INPLACEHOLDS* também contém GUIDs de políticas de retenção aplicadas à caixa de correio. Você pode identificar as políticas de retenção porque o GUID começa com o `mbx` prefixo. Se o GUID da política de retenção começar com o `skp` prefixo, isso indica que a política de retenção é aplicada às conversas do Skype for Business.  <br/> Para identificar a política de retenção aplicada à caixa de correio, execute o seguinte comando no PowerShell do centro de conformidade & segurança: <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Certifique-se de remover `mbx` o `skp` prefixo ou ao executar este comando.  <br/> |
|Políticas de retenção em toda a organização no centro de conformidade e segurança &  <br/> |Nenhum valor  <br/> ou  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696`(indica que a caixa de correio é excluída de uma política de toda a organização)  <br/> |Mesmo se a propriedade *InPlaceHolds* estiver vazia quando você executar o cmdlet **Get-Mailbox** , ainda poderá haver uma ou mais políticas de retenção em toda a organização aplicadas à caixa de correio.  <br/> Para verificar isso, você pode executar o `Get-OrganizationConfig | FL InPlaceHolds` comando no PowerShell do Exchange Online para obter uma lista dos GUIDs de políticas de retenção em toda a organização. O GUID para políticas de retenção em toda a organização aplicada às caixas de correio do Exchange começa com o `mbx` prefixo; por exemplo, `mbxa3056bb15562480fadb46ce523ff7b02` .  <br/> Para identificar a política de retenção em toda a organização que é aplicada à caixa de correio, execute o seguinte comando no PowerShell do centro de conformidade de segurança &: <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Se uma caixa de correio for excluída de uma política de retenção em toda a organização, o GUID da política de retenção será exibido na propriedade *InPlaceHolds* da caixa de correio do usuário quando você executar o cmdlet **Get-Mailbox** ; é identificado pelo prefixo `-mbx` ; por exemplo,`-mbxe9b52bf7ab3b46a286308ecb29624696` <br/> |
|retenção de caso de descoberta eletrônica no centro de conformidade de & de segurança  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |A propriedade *InPlaceHolds* também contém o GUID de qualquer isenção associada a uma ocorrência de descoberta eletrônica no centro de conformidade de & de segurança que possa ser colocado na caixa de correio. É possível dizer que esta é uma retenção de caso de descoberta eletrônica porque o GUID começa com o `UniH` prefixo.  <br/> Você pode usar o `Get-CaseHoldPolicy` cmdlet no PowerShell do centro de conformidade & de segurança para obter informações sobre a ocorrência de descoberta eletrônica à qual a retenção da caixa de correio está associada. Por exemplo, você pode executar o comando `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` para exibir o nome da retenção de caso que está na caixa de correio. Certifique-se de remover o `UniH` prefixo ao executar este comando.  <br/><br/> Para identificar a ocorrência de descoberta eletrônica à qual a retenção da caixa de correio está associada, execute os seguintes comandos:<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`


