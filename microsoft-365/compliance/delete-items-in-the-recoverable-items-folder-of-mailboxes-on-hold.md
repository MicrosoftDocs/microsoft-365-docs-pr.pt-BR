---
title: Excluir itens na pasta Itens Recuperáveis da caixa de correio na nuvem em espera
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
description: Saiba como os administradores podem excluir itens na pasta Itens Recuperáveis de um usuário para uma caixa de correio do Exchange Online, mesmo que essa caixa de correio seja colocada em espera legal.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7a51a78280885a8a7aa7c65a0c04110b46ed7f0
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919951"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold"></a>Excluir itens na pasta de Itens recuperáveis de caixas de correio baseadas em nuvem em retenção

A pasta Itens Recuperáveis de uma caixa de correio do Exchange Online existe para proteger contra exclusões acidentais ou mal-intencionadas. Ele também é usado para armazenar itens retidos e acessados por recursos de conformidade, como retidas e pesquisas de DescobertaScoberta. No entanto, em algumas situações, as organizações podem ter dados que foram mantidos in intencionalmente na pasta Itens Recuperáveis que devem ser excluídos. Por exemplo, um usuário pode enviar ou encaminhar sem querer uma mensagem de email que contenha informações confidenciais ou informações que possam ter sérias consequências comerciais. Mesmo que a mensagem seja excluída permanentemente, ela poderá ser retida indefinidamente porque um recurso legal foi colocado na caixa de correio. Esse cenário é conhecido como vazamento *de dados* porque os dados foram involutórios involutionamente no Office 365.  Nessas situações, você pode excluir itens na pasta Itens Recuperáveis de um usuário para uma caixa de correio do Exchange Online, mesmo que essa caixa de correio seja colocada em espera com um dos diferentes recursos de espera no Office 365. Esses tipos de retenção incluem Retenções de Litígio, In-Place Retenção, Retenções de Descoberta e Políticas de Retenção criadas no centro de conformidade e segurança no Office 365 ou no Microsoft 365.
  
 Este artigo explica como os administradores podem excluir itens da pasta Itens Recuperáveis para caixas de correio baseadas em nuvem que estão em espera. Este procedimento envolve desabilitar o acesso à caixa de correio e desabilitar a recuperação de item único, desabilitar o Assistente de Pasta Gerenciada do processamento da caixa de correio, remover temporariamente a espera, excluir itens da pasta Itens Recuperáveis e reverter a caixa de correio para sua configuração anterior. Este é o processo:
  
[Etapa 1: Coletar informações sobre a caixa de correio](#step-1-collect-information-about-the-mailbox)

[Etapa 2: Preparar a caixa de correio](#step-2-prepare-the-mailbox)

[Etapa 3: Remover todos os retém da caixa de correio](#step-3-remove-all-holds-from-the-mailbox)

[Etapa 4: Remover o atraso da caixa de correio](#step-4-remove-the-delay-hold-from-the-mailbox)

[Etapa 5: Excluir itens na pasta Itens Recuperáveis](#step-5-delete-items-in-the-recoverable-items-folder)

[Etapa 6: Reverter a caixa de correio para seu estado anterior](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> Os procedimentos descritos neste artigo resultarão na exclusão permanente dos dados (excluídos) de uma caixa de correio do Exchange Online. Isso significa que as mensagens que você excluir da pasta Itens Recuperáveis não podem ser recuperadas e não estarão disponíveis para descoberta legal ou outros fins de conformidade. Se você quiser excluir mensagens de uma caixa de correio colocada em retenção como parte de uma Retenção de Litígio, uma Retenção de In-Place, uma retenção de Descoberta Eletrônico ou uma política de retenção criada no centro de conformidade e segurança, consulte o gerenciamento de registros ou os departamentos jurídicos antes de remover a retenção. Sua organização pode ter uma política que define se uma caixa de correio em espera ou um incidente de vazamento de dados tem prioridade.
  
## <a name="before-you-delete-items"></a>Antes de excluir itens

- Para criar e executar uma pesquisa de conteúdo, você precisa ser membro do grupo de funções Gerente de Descoberta Eletrônica ou receber a função de gerenciamento de Pesquisa de Conformidade. Para excluir mensagens, você precisa ser membro do grupo de funções Gerenciamento da Organização ou receber a função de gerenciamento Pesquisa e Limpar. Para saber mais sobre como adicionar usuários a um grupo de função, confira [Atribuir permissões de Descoberta Eletrônica no Centro de Segurança e Conformidade](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions).

- O procedimento descrito neste artigo não tem suporte para caixas de correio inativas. Isso acontece porque você não pode reaplicar uma retenção (ou uma política de retenção) a uma caixa de correio inativa depois de removê-la. Quando você remove uma espera de uma caixa de correio inativa, ela é alterada para uma caixa de correio normal excluída de forma flexível e será excluída permanentemente da sua organização depois de processada pelo Assistente de Pasta Gerenciada.

- Você não pode executar esse procedimento para uma caixa de correio que tenha sido atribuída configurações de retenção com uma política bloqueada usando o Bloqueio de Preservação. Isso porque esse bloqueio impede a remoção ou exclusão da caixa de correio da política e a desabilitação do Assistente de Pasta Gerenciada na caixa de correio. Para obter mais informações sobre como bloquear políticas de retenção, consulte Usar o Bloqueio de Preservação para restringir as alterações nas políticas de retenção e políticas [de rótulo de retenção.](retention-preservation-lock.md)

- Se uma caixa de correio não for colocada em espera (ou não tiver a recuperação de item único habilitada), você poderá excluir os itens da pasta Itens Recuperáveis. Para obter mais informações sobre como fazer isso, consulte Pesquisar e [excluir mensagens de email em sua organização.](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)
  
## <a name="step-1-collect-information-about-the-mailbox"></a>Etapa 1: Coletar informações sobre a caixa de correio

Esta primeira etapa é coletar propriedades selecionadas da caixa de correio de destino que afetarão esse procedimento. Certifique-se de anotar essas configurações ou salvá-las em um arquivo de texto porque você alterará algumas dessas propriedades e reverterá para os valores originais na Etapa 6, depois de excluir itens da pasta Itens Recuperáveis. Aqui está uma lista das propriedades de caixa de correio que você precisa coletar.
  
- *SingleItemRecoveryEnabled*  e  *RetainDeletedItemsFor*. Se necessário, você desabilitará a recuperação única e aumentará o período de retenção de itens excluídos na Etapa 3.

- *LitigationHoldEnabled*  e  *InPlaceHolds*. Você precisa identificar todos os retém colocados na caixa de correio para que você possa removê-los temporariamente na Etapa 3. Consulte a [seção Mais informações](#more-information) para obter dicas sobre como identificar o tipo de espera que pode ser colocado em uma caixa de correio.

Além disso, você precisa obter as configurações de acesso para cliente de caixa de correio para que possa desabilitá-las temporariamente para que o proprietário (ou outros usuários) não possa acessar a caixa de correio durante esse procedimento. Por fim, você pode obter o tamanho atual e o número de itens na pasta Itens Recuperáveis. Depois de excluir itens da pasta Itens Recuperáveis na Etapa 5, você usará essas informações para verificar se os itens foram removidos.
  
1. [Conectar-se ao Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). Certifique-se de usar um nome de usuário e senha para uma conta de administrador que tenha sido atribuída às funções de gerenciamento apropriadas no Exchange Online.

2. Execute o seguinte comando para obter informações sobre a recuperação de item único e o período de retenção do item excluído.

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   Se a recuperação de item individual estiver habilitada, você terá que desabilitá-la na Etapa 2. Se o período de retenção do item excluído não estiver definido para 30 dias (o valor máximo no Exchange Online), você poderá autená-lo na Etapa 2.

3. Execute o seguinte comando para obter as configurações de acesso à caixa de correio da caixa de correio.

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   Você desabilitará todos esses métodos de acesso na Etapa 2.

4. Execute o seguinte comando para obter informações sobre as retenções e as políticas de retenção aplicadas à caixa de correio.

    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```

   > [!TIP]
    > Se houver muitos valores na propriedade  *InPlaceHolds*  e nem todos eles são exibidos, você pode executar o comando para exibir cada valor em  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` uma linha separada.
  
5. Execute o seguinte comando para obter informações sobre todas as políticas de retenção em toda a organização. 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```

   Se a sua organização tiver alguma política de retenção em toda a organização, você terá que excluir a caixa de correio dessas políticas na Etapa 3.

   > [!TIP]
    > Se houver muitos valores na propriedade  *InPlaceHolds*  e nem todos eles são exibidos, você pode executar o comando para exibir cada valor em  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` uma linha separada. 
  
6. Execute o seguinte comando para obter o tamanho atual e o número total de itens em pastas e subpastas na pasta Itens Recuperáveis na caixa de correio principal do usuário.

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Se a caixa de correio de arquivo morto do usuário estiver habilitada, execute o seguinte comando para obter o tamanho e o número total de itens em pastas e subpastas na pasta Itens Recuperáveis em sua caixa de correio de arquivo morto. 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Ao excluir itens na Etapa 5, você pode optar por excluir ou não itens na pasta Itens Recuperáveis na caixa de correio de arquivo morto principal do usuário. Se o arquivamento de expansão automática estiver habilitado para a caixa de correio, os itens em uma caixa de correio de arquivo morto auxiliar não serão excluídos.
  
## <a name="step-2-prepare-the-mailbox"></a>Etapa 2: Preparar a caixa de correio

Depois de coletar e salvar informações sobre a caixa de correio, a próxima etapa é preparar a caixa de correio executando as seguintes tarefas:
  
- **Desabilite o acesso do** cliente à caixa de correio para que o proprietário da caixa de correio não possa acessar sua caixa de correio e fazer alterações nos dados da caixa de correio durante esse procedimento.

- Aumente o período de retenção de **itens** excluídos para 30 dias (o valor máximo no Exchange Online) para que os itens não sejam excluídos da pasta Itens Recuperáveis antes de excluí-los na Etapa 5.

- **Desabilite a** recuperação de item único para que os itens não sejam retidos (pela duração do período de retenção de itens excluídos) depois de excluí-los da pasta Itens Recuperáveis na Etapa 5.

- **Desabilite o Assistente** de Pasta Gerenciada para que ele não processe a caixa de correio e mantenha os itens excluídos na Etapa 5.

Execute as seguintes etapas no PowerShell do Exchange Online.
  
1. Execute o seguinte comando para desabilitar todo o acesso do cliente à caixa de correio. A sintaxe do comando supõe que todos os métodos de acesso para cliente foram habilitados na caixa de correio.

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

   > [!NOTE]
    > Pode levar até 60 minutos para desabilitar todos os métodos de acesso para cliente para a caixa de correio. Observe que desabilitar esses métodos de acesso não desconecta o proprietário da caixa de correio no momento. Se o proprietário não estiver assinado, ele não poderá acessar sua caixa de correio depois que esses métodos de acesso são desabilitados.
  
2. Execute o seguinte comando para aumentar o período de retenção de itens excluídos no máximo 30 dias. Isso assume que a configuração atual é inferior a 30 dias.

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. Execute o seguinte comando para desabilitar a recuperação de item único.

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > Pode levar até 60 minutos para desabilitar a recuperação de item único. Não exclua itens na pasta Itens Recuperáveis até que esse período tenha decorrido. 
  
4. Execute o seguinte comando para impedir que o Assistente de Pasta Gerenciada processe a caixa de correio. Conforme explicado anteriormente, você só poderá desabilitar o Assistente de Pasta Gerenciada se uma política de retenção com um Bloqueio de Preservação não for aplicada à caixa de correio. 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>Etapa 3: Remover todos os retém da caixa de correio

A última etapa antes de excluir itens da pasta Itens Recuperáveis é remover todos os retém (identificados na Etapa 1) colocados na caixa de correio. Todas as retidas devem ser removidas para que os itens não sejam retidos depois que você excluí-los da pasta Itens Recuperáveis. As seções a seguir contêm informações sobre como remover diferentes tipos de retém em uma caixa de correio. Consulte a [seção Mais informações](#more-information) para obter dicas sobre como identificar o tipo de espera que pode ser colocado em uma caixa de correio. Para obter mais informações, [consulte Como identificar o tipo de espera colocada em uma caixa de correio do Exchange Online.](identify-a-hold-on-an-exchange-online-mailbox.md)
  
> [!CAUTION]
> Conforme mencionado anteriormente, consulte o gerenciamento de registros ou os departamentos jurídicos antes de remover uma espera de uma caixa de correio. 
  
### <a name="litigation-hold"></a>Retenção de litígio
  
Execute o seguinte comando no PowerShell do Exchange Online para remover uma Moção de Litígio da caixa de correio.

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

> [!NOTE]
> Semelhante a desabilitar os métodos de acesso para cliente e a recuperação de item único, pode levar até 60 minutos para remover a 1ª vez. Não exclua itens da pasta Itens Recuperáveis até que esse período tenha decorrido. 
  
### <a name="in-place-hold"></a>Bloqueio In-loco
  
Execute o seguinte comando no PowerShell do Exchange Online para identificar o In-Place De espera que é colocado na caixa de correio. Use o GUID para a In-Place que você identificou na Etapa 1.

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

Depois de identificar o In-Place, você pode usar o Centro de administração do Exchange (EAC) ou o PowerShell do Exchange Online para remover a caixa de correio da espera. Para mais informações, consulte [Criar ou remover um bloqueio In-loco](https://go.microsoft.com/fwlink/?linkid=852668).
  
### <a name="retention-policies-applied-to-specific-mailboxes"></a>Políticas de retenção aplicadas a caixas de correio específicas
  
Execute o seguinte comando no [PowerShell do Centro](https://go.microsoft.com/fwlink/?linkid=627084) de & Conformidade e Segurança para identificar a política de retenção aplicada à caixa de correio. Esse comando também retornará todas as políticas de retenção de conversa do Teams aplicadas a uma caixa de correio. Use o GUID (sem incluir o prefixo ou o prefixo) para a política de `mbx` retenção identificada na Etapa `skp` 1.

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

Depois de identificar a política de retenção, vá para a página Retenção de governança de informações no Centro de Conformidade do & de Segurança, edite a política de retenção identificada na etapa anterior e remova a caixa de correio da lista de destinatários incluídos na política de  >   retenção.
  
### <a name="organization-wide-retention-policies"></a>Políticas de retenção para toda a organização
  
As políticas de retenção em toda a organização, no Exchange e em toda a equipe são aplicadas a todas as caixas de correio na organização. Eles são aplicados no nível da organização (não no nível da caixa de correio) e são retornados quando você executar o cmdlet **Get-OrganizationConfig** na Etapa 1. Execute o seguinte comando no [PowerShell do Centro](https://go.microsoft.com/fwlink/?linkid=627084) de & Conformidade e Segurança para identificar as políticas de retenção em toda a organização. Use o GUID (sem incluir o prefixo) para as políticas de retenção em toda a organização  `mbx` identificadas na Etapa 1.

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

Depois de identificar as políticas de retenção em toda a organização, vá para a página Retenção de governança de informações no Centro de Conformidade do & de Segurança, edite cada política de retenção em toda a organização que você identificou na etapa anterior e adicione a caixa de correio à lista de  >   destinatários excluídos. Isso removerá a caixa de correio do usuário da política de retenção.

### <a name="retention-labels"></a>Rótulos de retenção

Sempre que um usuário aplica um rótulo configurado para reter conteúdo ou reter e, em seguida, excluir conteúdo para qualquer pasta ou item em sua caixa de correio, a propriedade de caixa de correio *ComplianceTagHoldApplied* é definida como **True**. Quando isso acontece, a caixa de correio é considerada em espera, como se tivesse sido colocada em Retenção de Litígio ou atribuída a uma política de retenção.

Para exibir o valor da *propriedade ComplianceTagHoldApplied,* execute o seguinte comando no PowerShell do Exchange Online:

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

Depois de identificar que uma caixa de correio está em espera porque um rótulo de retenção é aplicado a uma pasta ou item, você pode usar a ferramenta Pesquisa de Conteúdo no centro de conformidade e segurança para procurar itens rotulados usando a condição de pesquisa ComplianceTag. For more information, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md#conditions-for-common-properties).

Para obter mais informações sobre rótulos, [consulte Saiba mais sobre políticas de retenção e rótulos de retenção.](retention.md)

### <a name="ediscovery-holds"></a>Bloqueios de Descoberta Eletrônica
  
Execute os seguintes comandos no [PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) do Centro de Conformidade e Segurança para identificar a espera associada a um caso de Descoberta Eletrônico (chamado de retém de *Descoberta* Eletrônico) que é aplicado à caixa de correio. & Use o GUID (sem incluir  `UniH` o prefixo) para o eDiscovery hold que você identificou na Etapa 1. O segundo comando exibe o nome da ocorrência de Descoberta e à quais a isenção está associada; o terceiro comando exibe o nome da espera.
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

Depois de identificar o nome da ocorrência de Descoberta **EDiscovery** e a espera, vá para a página descoberta \> **eDiscovery no** centro de conformidade, abra a ocorrência e remova a caixa de correio da espera. Para obter mais informações sobre como identificar retém de Descoberta Eletrônico, consulte a seção "Resções de Descoberta Eletrônico" em Como identificar o tipo de espera colocada em uma caixa de correio do [Exchange Online.](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds)
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>Etapa 4: Remover o atraso da caixa de correio

Após qualquer tipo de espera ser removido de uma caixa de correio, o valor da propriedade de caixa de correio *DelayHoldApplied* ou *DelayReleaseHoldApplied* é definido como **True**. Isso ocorre na próxima vez que o Assistente de Pasta Gerenciada processa a caixa de correio e detecta que uma espera foi removida. Isso é chamado *de* espera de atraso e significa que a remoção real da espera é adiada por 30 dias para impedir que os dados são excluídos permanentemente da caixa de correio. (A finalidade de uma espera de atraso é dar aos administradores a oportunidade de pesquisar ou recuperar itens de caixa de correio que serão removidos após a remoção de uma espera.)  Quando um atraso é colocado na caixa de correio, a caixa de correio ainda é considerada em espera por um período ilimitado, como se a caixa de correio estivesse em Litígio. Após 30 dias, a espera de atraso expirará, e o Microsoft 365 tentará remover automaticamente a espera de atraso (definindo a propriedade *DelayHoldApplied* ou *DelayReleaseHoldApplied* como **False**) para que a espera seja removida. Para obter mais informações sobre um atraso, consulte a seção "Gerenciando caixas de correio em espera de atraso" em Como identificar o tipo de espera colocada em uma caixa de correio do [Exchange Online.](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)

Antes de excluir itens na Etapa 5, você precisa remover um atraso de espera da caixa de correio. Primeiro, determine se a espera de atraso é aplicada à caixa de correio executando o seguinte comando no PowerShell do Exchange Online:

```powershell
Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
```

Se o valor da propriedade *DelayHoldApplied* ou *DelayReleaseHoldApplied* for definido como **False,** um atraso não será colocado na caixa de correio. Você pode ir para a Etapa 5 e excluir itens na pasta Itens Recuperáveis.

Se o valor da *propriedade DelayHoldApplied* ou *DelayReleaseHoldApplied* for definido como **True**, execute um dos seguintes comandos para remover a espera de atraso:

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

Ou

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

Você deve ter a função de Reter Legal no Exchange Online para usar os parâmetros *RemoveDelayHoldApplied* ou *RemoveDelayReleaseHoldApplied.*

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>Etapa 5: Excluir itens na pasta Itens Recuperáveis

Agora você está pronto para realmente excluir itens na pasta Itens Recuperáveis usando os cmdlet & s [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch) e [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearchaction) no PowerShell do Centro de Conformidade e Segurança.

Para pesquisar itens que estão localizados na pasta Itens Recuperáveis, recomendamos que você execute uma coleção *direcionada.* Isso significa que você restringe o escopo da sua pesquisa apenas aos itens localizados na pasta Itens Recuperáveis. Você pode fazer isso executando o script no artigo [Usar Pesquisa de Conteúdo para coleções direcionadas.](use-content-search-for-targeted-collections.md) Esse script retorna o valor da propriedade de ID da pasta para todas as subpastas na pasta itens recuperáveis de destino. Em seguida, use a ID da pasta em uma consulta de pesquisa para retornar itens localizados nessa pasta.

Esta é uma visão geral do processo de pesquisa e exclusão de itens na pasta Itens Recuperáveis de um usuário:

1. Execute o script da coleção direcionada que retorna as IDs de pasta para todas as pastas na caixa de correio do usuário de destino. O script se conecta ao PowerShell do Exchange Online e ao PowerShell de & e Conformidade na mesma sessão do PowerShell. Para obter mais informações, consulte [Executar o script para obter uma lista de pastas para uma caixa de correio.](use-content-search-for-targeted-collections.md#step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site)

2. Copie as IDs de pasta de todas as subpastas na pasta Itens Recuperáveis. Como alternativa, você pode redirecionar a saída do script para um arquivo de texto.

   Aqui está uma lista e uma descrição das subpastas na pasta Itens Recuperáveis da onde você pode pesquisar e excluir itens:

   - **Exclusões**: Contém itens excluídos de forma suave cujo período de retenção de itens excluídos não expirou. Os usuários podem recuperar itens excluídos de forma suave dessa subpasta usando a ferramenta Recuperar Itens Excluídos no Outlook.

   - **Limpezas:** contém itens excluídos ilegis cujo período de retenção de itens excluídos expirou. Os usuários também podem excluir itens permanentemente, excluindo itens da pasta Itens Recuperáveis. Se a caixa de correio estiver em espera, os itens excluídos de forma permanente serão preservados. Essa subpasta não é visível para os usuários finais.

   - **DiscoveryHolds**: contém itens excluídos de forma permanente que foram preservados por uma retenção de Descoberta eDiscovery ou uma política de retenção. Essa subpasta não é visível para os usuários finais.

   - **SubstrateHolds**: contém itens excluídos permanentemente do Teams e outros aplicativos baseados em nuvem que foram preservados por uma política de retenção ou outro tipo de retenção. Essa subpasta não é visível para os usuários finais.

3. Use o cmdlet **New-ComplianceSearch** & (no PowerShell do Centro de Conformidade e Segurança) ou use a ferramenta pesquisa de conteúdo no centro de conformidade para criar uma pesquisa de conteúdo que retorna itens da pasta Itens Recuperáveis do usuário de destino. Você pode fazer isso incluindo a FolderId na consulta de pesquisa para todas as subpastas que deseja pesquisar. Por exemplo, a consulta a seguir retorna todas as mensagens nas subpastas Purges e eDiscoveryHolds:

   ```text
   folderid:<folder ID of Purges subfolder> OR folderid:<folder ID of DiscoveryHolds subfolder>
   ```

   Para obter mais informações e exemplos sobre a execução de pesquisas de conteúdo que usam a propriedade de ID da pasta, consulte Usar uma ID de pasta ou [para executar uma coleção direcionada.](use-content-search-for-targeted-collections.md#step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection)

   > [!NOTE]
   > Se você usar o cmdlet **New-ComplianceSearch** para pesquisar a pasta Itens Recuperáveis, use o cmdlet **Start-ComplianceSearch** para executar a pesquisa.

4. Depois de criar uma pesquisa de conteúdo e validar que ela retorna os itens que você quer excluir, use o comando & (no PowerShell do Centro de Conformidade e Segurança) para excluir permanentemente os itens retornados pela pesquisa de conteúdo que você criou na etapa `New-ComplianceSearchAction -Purge -PurgeType HardDelete` anterior. Por exemplo, você pode executar um comando semelhante ao seguinte comando:

   ```powershell
   New-ComplianceSearchAction -SearchName "RecoverableItems" -Purge -PurgeType HardDelete
   ```

5. No máximo 10 itens por caixa de correio são excluídos quando você executar o comando anterior. Isso significa que talvez seja preciso executar o comando várias vezes para excluir todos os itens que deseja `New-ComplianceSearchAction -Purge` excluir na pasta Itens Recuperáveis. Para excluir itens adicionais, primeiro você precisa remover a ação de limpeza da pesquisa de conformidade anterior. Você pode fazer isso executando `Remove-ComplianceSearchAction` o cmdlet. Por exemplo, para excluir a ação de limpeza que foi executado na etapa anterior, execute o seguinte comando:

   ```powershell
   Remove-ComplianceSearchAction "RecoverableItems_Purge"
   ```

   Depois de fazer isso, você pode criar uma nova ação de limpeza de pesquisa de conformidade para excluir mais itens. Você terá que excluir cada ação de limpeza antes de criar uma nova.

   Para obter uma lista das ações de pesquisa de conformidade, você pode executar o `Get-ComplianceSearchAction` cmdlet. As ações de limpeza são `_Purge` identificadas pelo nome da pesquisa.

### <a name="verify-that-items-were-deleted"></a>Verificar se os itens foram excluídos

Para verificar se você excluiu com êxito itens da pasta Itens Recuperáveis de uma caixa de correio, use o cmdlet **Get-MailboxFolderStatistics** no PowerShell do Exchange Online para verificar o tamanho e o número de itens na pasta Itens Recuperáveis. Você pode comparar essas estatísticas com as coletadas na Etapa 1.
  
Execute o seguinte comando para obter o tamanho atual e o número total de itens em pastas e subpastas na pasta Itens Recuperáveis na caixa de correio principal do usuário.
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

Execute o seguinte comando para obter o tamanho e o número total de itens em pastas e subpastas na pasta Itens Recuperáveis na caixa de correio de arquivo morto do usuário.

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a>Etapa 6: Reverter a caixa de correio para seu estado anterior

A etapa final é reverter a caixa de correio de volta para sua configuração anterior. Isso significa redefinir as propriedades alteradas na Etapa 2 e aplicar novamente as retém removidas na Etapa 3. Isso inclui:
  
- Alterando o período de retenção do item excluído de volta para seu valor anterior. Como alternativa, você pode deixar esse conjunto como 30 dias, o valor máximo no Exchange Online.

- Rehabilitando a recuperação de item único.

- Habilitando os métodos de acesso para cliente para que o proprietário possa acessar sua caixa de correio.

- Reaplicação das retenções e políticas de retenção removidas.

- Habilitando o Assistente de Pasta Gerenciada para processar a caixa de correio.

> [!IMPORTANT]
> Recomendamos que você aguarde 24 horas após reaplicação de uma política de retenção ou retenção (e verifique se ela está em funcionamento) antes de reabilitar o Assistente de Pasta Gerenciada para processar a caixa de correio.
  
Execute as seguintes etapas (na sequência especificada) no PowerShell do Exchange Online.
  
1. Execute o seguinte comando para alterar o período de retenção do item excluído de volta para seu valor original. Isso assume que a configuração anterior é inferior a 30 dias; por exemplo, 14 dias.

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

4. Reaplicar as retém removidas na Etapa 3. Dependendo do tipo de espera, use um dos procedimentos a seguir.

    **Retenção de litígio**

    Execute o seguinte comando para reabilitar uma Habilitação de Litígio para a caixa de correio.

    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **Retenção Local**

    Use o EAC (ou o PowerShell do Exchange Online) para adicionar a caixa de correio de volta ao In-Place Espera.

    **Políticas de retenção aplicadas a caixas de correio específicas**

    Use o Centro de Conformidade & segurança para adicionar a caixa de correio de volta à política de retenção. Vá para a página Retenção de & **governança** de informações no Centro de Conformidade e Segurança, edite a política de retenção e adicione a caixa de correio de volta à lista de destinatários aos que a política de retenção é  >   aplicada.

    **Políticas de retenção para toda a organização**

    Se você removeu uma política de retenção em toda a organização ou no Exchange excluindo-a da política, & use o Centro de Conformidade e Segurança para remover a caixa de correio da lista de usuários excluídos. Vá para a página Retenção de & **Governança** de Informações no Centro de Conformidade e Segurança, edite a política de retenção em toda a organização e remova a caixa de correio da lista de  >   destinatários excluídos. Isso reaplica a política de retenção à caixa de correio do usuário.

    **EDiscovery case holds**

    Use o Centro de Conformidade & segurança para adicionar a caixa de correio de volta à espera associada a uma ocorrência de Descoberta Eletrônico. Vá para a **página descoberta eDiscovery**  >  **eDiscovery,** abra a ocorrência e adicione a caixa de correio de volta à espera. 

5. Execute o seguinte comando para permitir que o Assistente de Pasta Gerenciada processe a caixa de correio novamente. Conforme mencionado anteriormente, recomendamos que você aguarde 24 horas após a reaplicação de uma política de retenção ou retenção (e verifique se ela está em funcionamento) antes de reabilitar o Assistente de Pasta Gerenciada.

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. Para verificar se a caixa de correio foi revertida de volta para sua configuração anterior, você pode executar os seguintes comandos e comparar as configurações com as que você coletou na Etapa 1.

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a>Mais informações

Aqui está uma tabela que descreve como identificar diferentes tipos de reter com base nos valores na propriedade *InPlaceHolds* quando você executar os cmdlets **Get-Mailbox** ou **Get-OrganizationConfig.** Para obter informações mais detalhadas, consulte Como identificar o tipo de [espera colocada em uma caixa de correio do Exchange Online.](identify-a-hold-on-an-exchange-online-mailbox.md)

Conforme explicado anteriormente, você precisa remover todas as retenções e políticas de retenção de uma caixa de correio antes de excluir itens com êxito na pasta Itens Recuperáveis.
  
| Tipo de espera | Valor de exemplo | Como identificar a espera |
|:-----|:-----|:-----|
|Retenção de litígio  <br/> | `True` <br/> |A  *propriedade LitigationHoldEnabled*  é definida como  `True` .  <br/> |
|Bloqueio In-loco  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |A  *propriedade InPlaceHolds*  contém o GUID do In-Place que é colocado na caixa de correio. Você pode dizer que é um In-Place, pois o GUID não começa com um prefixo.  <br/> Você pode usar o comando no PowerShell do Exchange Online para obter informações sobre o In-Place  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` De espera na caixa de correio.  <br/> |
| Políticas de retenção no Centro de Conformidade & segurança aplicadas a caixas de correio específicas  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> ou  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |Ao executar o cmdlet **Get-Mailbox,** a propriedade  *InPlaceHolds*  também contém GUIDs de políticas de retenção aplicadas à caixa de correio. Você pode identificar políticas de retenção porque o GUID começa com o  `mbx` prefixo. Se o GUID da política de retenção começar com o prefixo, isso indica que a política de retenção é aplicada às  `skp` conversas do Skype for Business.  <br/> Para identificar a política de retenção aplicada à caixa de correio &, execute o seguinte comando no PowerShell do Centro de Conformidade e Segurança: <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Remova o prefixo  `mbx` ou o  `skp` prefixo ao executar esse comando.  <br/> |
|Políticas de retenção para toda a organização no Centro de Conformidade e & Segurança  <br/> |Sem valor  <br/> ou  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696` (indica que a caixa de correio é excluída de uma política de toda a organização)  <br/> |Mesmo que a propriedade  *InPlaceHolds*  esteja vazia quando você executar o cmdlet **Get-Mailbox,** ainda pode haver uma ou mais políticas de retenção em toda a organização aplicadas à caixa de correio.  <br/> Para verificar isso, você pode executar o comando no PowerShell do Exchange Online para obter uma lista dos GUIDs para políticas de retenção  `Get-OrganizationConfig | FL InPlaceHolds` em toda a organização. O GUID para políticas de retenção em toda a organização aplicadas a caixas de correio do Exchange começa com o  `mbx` prefixo; por exemplo,  `mbxa3056bb15562480fadb46ce523ff7b02` .  <br/> Para identificar a política de retenção em toda a organização aplicada à caixa de correio &, execute o seguinte comando no PowerShell do Centro de Conformidade e Segurança: <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Se uma caixa de correio for excluída de uma política de retenção em toda a organização, o GUID da política de retenção será exibido na propriedade  *InPlaceHolds*  da caixa de correio do usuário quando você executar o cmdlet **Get-Mailbox;** ele é identificado pelo prefixo  `-mbx` ; por exemplo,  `-mbxe9b52bf7ab3b46a286308ecb29624696` <br/> |
|EDiscovery case hold in the Security & Compliance Center  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |A  *propriedade InPlaceHolds*  também contém o GUID de qualquer espera associada & a um caso de Descoberta Eletrônico no Centro de Conformidade e Segurança que pode ser colocado na caixa de correio. Você pode dizer que essa é uma isenção de caso de Descoberta eDiscovery porque o GUID começa com o  `UniH` prefixo.  <br/> Você pode usar o cmd & let no PowerShell do Centro de Conformidade e Segurança para obter informações sobre o caso de Descoberta Eletrônica ao que a isenção na caixa de correio está  `Get-CaseHoldPolicy` associada. Por exemplo, você pode executar o comando para exibir o nome do caso que  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` está na caixa de correio. Certifique-se de remover  `UniH` o prefixo ao executar esse comando.  <br/><br/> Para identificar a ocorrência de Descoberta Eletrônico à que a isenção na caixa de correio está associada, execute os seguintes comandos:<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`
