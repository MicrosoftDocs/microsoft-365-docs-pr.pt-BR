---
title: Alterar a duração da retenção para uma caixa de correio inativa no Office 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
description: Depois que uma caixa de correio do Office 365 é desativada, você pode alterar a duração da política de retenção de bloqueio ou do Office 365 atribuída à caixa de correio inativa. A duração da retenção define por quanto tempo os itens da pasta itens recuperáveis são mantidos.
ms.openlocfilehash: c50f7845377b6428a4cdce2bb7240a7ca973a8eb
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595938"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox-in-office-365"></a>Alterar a duração da retenção para uma caixa de correio inativa no Office 365

Uma caixa de correio inativa é usada para manter o email de um funcionário anterior, depois que ele deixa sua organização. Uma caixa de correio fica inativa quando uma retenção de litígio, um bloqueio in-loco, uma política de retenção do Office 365 ou uma retenção associada a uma ocorrência de descoberta eletrônica é colocada na caixa de correio e a conta de usuário do Office 365 correspondente é excluída. O conteúdo de uma caixa de correio inativa é mantido pela duração da retenção que foi colocada na caixa de correio antes de ser desativada. A duração da retenção define por quanto tempo os itens da pasta itens recuperáveis são mantidos. Quando a duração da retenção expira para um item na pasta itens recuperáveis, o item é excluído permanentemente (limpo) da caixa de correio inativa. Depois que uma caixa de correio for desativada, você poderá alterar a duração da política de retenção de espera ou do Office 365 atribuída à caixa de correio inativa.
  
> [!IMPORTANT]
> Como continuamos a investir em diferentes maneiras de preservar o conteúdo da caixa de correio, anunciamos a aposentadoria de bloqueios in-loco no centro de administração do Exchange. Isso significa que você deve usar as políticas de retenção de litígio e do Office 365 para criar uma caixa de correio inativa. A partir de 1º de abril de 2020 você não poderá criar novos bloqueios in-loco no Exchange Online. Mas você ainda poderá alterar a duração da retenção de um bloqueio in-loco colocado em uma caixa de correio inativa. No entanto, Iniciando em 1º de julho de 2020, você não poderá alterar a duração da retenção. Você só poderá excluir uma caixa de correio inativa removendo o bloqueio in-loco. As caixas de correio inativas existentes que estão no bloqueio in-loco ainda serão preservadas até que a retenção seja removida. Para obter mais informações sobre a aposentadoria de bloqueios in-loco, consulte [aposentadoria of Legacy eDiscovery Tools](legacy-ediscovery-retirement.md).
  
## <a name="before-you-begin"></a>Antes de começar

- Você precisa usar o PowerShell do Exchange Online para alterar a duração da retenção para uma retenção de litígio em uma caixa de correio inativa. Você não pode usar o Centro de Administração do Exchange (EAC). Mas você pode usar o PowerShell do Exchange Online ou o Eat para alterar a duração da retenção de um bloqueio in-loco. Você pode usar o centro de segurança e conformidade ou o PowerShell do centro de conformidade do & de segurança para alterar a duração da retenção de uma política de retenção do Office 365.
    
- Para conectar-se ao PowerShell do Exchange Online PowerShell ou segurança & centro de conformidade, consulte um dos seguintes tópicos:
    
  - [Conectar-se ao PowerShell do Exchange Online ](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
  - [Conecte-se ao PowerShell do Centro de Conformidade e Segurança do Office 365](https://go.microsoft.com/fwlink/?linkid=799771)
    
- As suspensões associadas às ocorrências de descoberta eletrônica são infinitas, o que significa que não há duração de retenção que pode ser alterada. Os itens são retidos para sempre ou até que a retenção seja removida e a caixa de correio inativa seja excluída.
    
- Para obter mais informações sobre caixas de correio inativas, consulte [inativa caixas de correio no Office 365](inactive-mailboxes-in-office-365.md).
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Etapa 1: identificar as isenções em uma caixa de correio inativa

Como diferentes tipos de isenções ou uma ou mais políticas de retenção do Office 365 podem ser colocadas em uma caixa de correio inativa, a primeira etapa é identificar as isenções em uma caixa de correio inativa.
  
Execute o seguinte comando no PowerShell do Exchange Online para exibir as informações de retenção de todas as caixas de correio inativas em sua organização.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```

O valor de **true** para a propriedade **LitigationHoldEnabled** indica que a caixa de correio inativa está em retenção de litígio. Se um bloqueio in-loco, um bloqueio de descoberta eletrônica ou uma política de retenção do Office 365 for colocado em uma caixa de correio inativa, um GUID para a política de retenção ou bloqueio será exibido como o valor da propriedade **InPlaceHolds** . Por exemplo, veja a seguir os resultados de cinco caixas de correio inativas. 
  
||
|:-----|
|
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
LitigationHoldDuration: 365.00:00:00
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491}
...
DisplayName           : Mario Necaise
Name                  : marion
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {}
...
DisplayName           : Carol Olson
Name                  : carolo
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {mbxcdbbb86ce60342489bff371876e7f224}
...
DisplayName           : Abraham McMahon
Name                  : abrahamm
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {UniH7d895d48-7e23-4a8d-8346-533c3beac15d}
```

A tabela a seguir identifica os cinco tipos de retenção diferentes que foram usados para tornar cada caixa de correio inativa.
  
|**Caixa de correio inativa**|**Tipo de bloqueio**|**Como identificar a retenção na caixa de correio inativa**|
|:-----|:-----|:-----|
|Ana Beebe  <br/> |Retenção de litígio  <br/> |A propriedade *LitigationHoldEnabled* está definida como `True`.  <br/> |
|Pilar Fernandes  <br/> |Bloqueio In-loco  <br/> |A propriedade *InPlaceHolds* contém o GUID do bloqueio in-loco colocado na caixa de correio inativa. É possível dizer que isso é um bloqueio in-loco porque a ID não começa com um prefixo.  <br/> Você pode usar o `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` comando no PowerShell do Exchange Online para obter informações sobre o bloqueio in-loco na caixa de correio inativa.  <br/> |
|Mario Necaise  <br/> |Política de retenção do Office 365 em toda a organização no centro de conformidade e segurança &  <br/> |A propriedade *InPlaceHolds* está vazia. Isso indica que uma ou mais políticas de retenção do Office 365 em toda a organização ou (no Exchange) são aplicadas à caixa de correio inativa. Nesse caso, você pode executar o `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` comando no PowerShell do Exchange Online para obter uma lista dos GUIDs das políticas de retenção do Office 365 em toda a organização. O GUID para políticas de retenção em toda a organização que são aplicadas às caixas de correio do `mbx` Exchange começam com o prefixo; por exemplo, `mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> <br/>Para identificar a política de retenção do Office 365 que é aplicada à caixa de correio inativa, execute o seguinte comando no PowerShell do centro de conformidade de segurança &.  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|Carol Olson  <br/> |Política de retenção do Office 365 no centro de conformidade & segurança aplicado a caixas de correio específicas  <br/> |A propriedade *InPlaceHolds* contém o GUID da política de retenção do Office 365 que é aplicada à caixa de correio inativa. Você pode dizer que esta é uma política de retenção que se aplica a caixas de correio específicas porque o `mbx` GUID começa com o prefixo. Se o GUID da política de retenção aplicada à caixa de correio inativa começou com `skp` o prefixo, ele indicaria que a política de retenção é aplicada às conversas do Skype for Business.  <br/><br/> Para identificar a política de retenção do Office 365 que é aplicada à caixa de correio inativa, execute o seguinte comando no PowerShell do centro de conformidade de segurança &.<br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/>Certifique-se de remover `mbx` o `skp` prefixo ou ao executar este comando.  <br/> |
|Abraham McMahon  <br/> |retenção de caso de descoberta eletrônica no centro de conformidade de & de segurança  <br/> |A propriedade *InPlaceHolds* contém o GUID da retenção de ocorrência de descoberta eletrônica que é colocada na caixa de correio inativa. É possível dizer que esta é uma retenção de caso de descoberta eletrônica porque o `UniH` GUID começa com o prefixo.  <br/> Você pode usar o `Get-CaseHoldPolicy` cmdlet em segurança & o PowerShell do centro de conformidade para obter informações sobre a ocorrência de descoberta eletrônica à qual a retenção está associada à caixa de correio inativa. Por exemplo, você pode executar o comando `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` para exibir o nome da retenção de caso que está na caixa de correio inativa. Certifique-se de remover `UniH` o prefixo ao executar este comando.  <br/><br/> Para identificar a ocorrência de descoberta eletrônica à qual a retenção está associada à caixa de correio inativa, execute os seguintes comandos.  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> **Observação:** Não recomendamos o uso de bloqueios de descoberta eletrônica para caixas de correio inativas. That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue. Em algum momento, um caso jurídico provavelmente será encerrado e as suspensões associadas ao caso serão removidas e o caso de descoberta eletrônica será fechado (ou excluído). Na verdade, se uma retenção colocada em uma caixa de correio inativa estiver associada a uma ocorrência de descoberta eletrônica e a retenção for liberada ou se a ocorrência de descoberta eletrônica estiver fechada ou excluída, a caixa de correio inativa será excluída permanentemente. 

Para obter mais informações sobre as políticas de retenção do Office 365, consulte [visão geral das políticas de retenção](retention-policies.md).
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a>Etapa 2: alterar a duração da retenção de uma caixa de correio inativa

Depois de identificar o tipo de retenção que é colocado na caixa de correio inativa (e se há várias isenções), a próxima etapa é alterar a duração da retenção. 
  
### <a name="change-the-duration-for-a-litigation-hold"></a>Alterar a duração de uma retenção de litígio

Confira aqui como usar o PowerShell do Exchange Online para alterar a duração da retenção para uma retenção de litígio que é colocada em uma caixa de correio inativa. Você não pode usar o Eat. Execute o seguinte comando para alterar a duração da retenção. Neste exemplo, a duração da retenção é alterada para um período de tempo ilimitado.
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

O resultado é que os itens da caixa de correio inativa são mantidos indefinidamente ou até que a retenção seja removida ou a duração da retenção seja alterada para um valor diferente.
  
> [!TIP]
> A melhor maneira de identificar uma caixa de correio inativa é usando seu **nome distinto** ou valor de **GUID do Exchange** . O uso de um desses valores ajuda a evitar a especificação acidental da caixa de correio errada. 
  
### <a name="change-the-duration-for-an-in-place-hold"></a>Alterar a duração de um bloqueio in-loco

 Você pode usar o Eat ou o PowerShell do Exchange Online para alterar a duração da retenção para um bloqueio in-loco. 
  
#### <a name="use-the-eac-to-change-the-hold-duration"></a>Usar o Eat para alterar a duração da retenção

1. Se você souber o nome do bloqueio in-loco que deseja alterar, vá para a próxima etapa. Caso contrário, execute o seguinte comando para obter o nome do bloqueio in-loco que é colocado na caixa de correio inativa. Use o GUID de bloqueio in-loco obtido na [etapa 1](#step-1-identify-the-holds-on-an-inactive-mailbox).

    ```powershell
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. No Eat, vá para **Gerenciamento** \> **de conformidade e descoberta eletrônica &amp; in-loco**.
    
3. Selecione o bloqueio in-loco que você deseja alterar e, em seguida **** ![, selecione Editar](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)ícone de edição.
    
4. Na página Propriedades **de retenção de &amp; descoberta eletrônica in-loco** , selecione **bloqueio in-loco**. 
    
5. Siga um destes procedimentos com base na duração atual da retenção:
    
    1. Selecione **reter indefinidamente** para reter itens por um período de tempo ilimitado. 
    
    2. Selecione **especificar número de dias para reter itens em relação à data de recebimento** para reter itens por um período específico. Digite o número de dias para os quais você deseja armazenar itens. 
    
    ![Captura de tela da alteração da duração de um Bloqueio In-loco](media/cfcfd92a-9d65-40c0-90ef-ab72697b0166.png)
  
6. Selecione **Salvar**.
    
#### <a name="use-exchange-online-powershell-to-change-the-hold-duration"></a>Usar o PowerShell do Exchange Online para alterar a duração da retenção

1. Se você souber o nome do bloqueio in-loco que deseja alterar, vá para a próxima etapa. Caso contrário, execute o seguinte comando para obter o nome do bloqueio in-loco que é colocado na caixa de correio inativa. Use o GUID de bloqueio in-loco obtido na [etapa 1](#step-1-identify-the-holds-on-an-inactive-mailbox).

    ```powershell
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. Execute o seguinte comando para alterar a duração da retenção. Neste exemplo, a duração da retenção é alterada para 2.555 dias (aproximadamente sete anos). 
    
    ```powershell
    Set-MailboxSearch <identity of In-Place Hold> -ItemHoldPeriod 2555
    ```

     Para alterar a duração da retenção para um período de tempo ilimitado, use _-ItemHoldPeriod Unlimited_.
  
## <a name="more-information"></a>Mais informações

- **Como a duração da retenção é calculada para um item em uma caixa de correio inativa?** A duração é calculada a partir da data original em que um item de caixa de correio foi recebido ou criado. 
    
- **O que acontece quando a duração da retenção expira?** Quando a duração da retenção expira para um item de caixa de correio na pasta itens recuperáveis, o item é excluído permanentemente (limpo) da caixa de correio inativa. Se não houver nenhuma duração especificada para a retenção colocada na caixa de correio inativa, os itens na pasta itens recuperáveis nunca serão removidos (a menos que a duração da retenção de caixa de correio inativa seja alterada). 
    
- **Uma política de retenção do Exchange ainda é processada em caixas de correio inativas?** Se uma política de retenção do Exchange (o recurso gerenciamento de registros de mensagens ou MRM, no Exchange Online) tiver sido aplicada a uma caixa de correio quando for desativada, as políticas de exclusão (que são marcas de retenção configuradas com uma ação de retenção de **exclusão** ) continuarão a ser processadas na caixa de correio inativa. Isso significa que os itens que estão marcados com uma política de exclusão são movidos para a pasta itens recuperáveis quando o período de retenção expira. Esses itens são, então, removidos da caixa de correio inativa quando a duração da retenção de um item expira. 
    
    Por outro lado, quaisquer políticas de arquivamento (que são marcas de retenção configuradas com uma ação de retenção **MoveToArchive** ) que estão incluídas na política de retenção atribuída a uma caixa de correio inativa serão ignoradas. Isso significa que os itens em uma caixa de correio inativa que estão marcados com uma política de arquivo morto permanecem na caixa de correio principal quando o período de retenção expira. Elas não serão movidas para a caixa de correio de arquivo morto ou para a pasta itens recuperáveis na caixa de correio de arquivo morto. Como um usuário não pode entrar em uma caixa de correio inativa, não há motivo para consumir recursos de datacenter para processar políticas de arquivamento. 
    
- **Para verificar a duração da nova retenção, execute um dos seguintes comandos.** O primeiro comando é para retenção de litígio; o segundo é para bloqueio in-loco. 

    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

    ```powershell
    Get-MailboxSearch <identity of In-Place Hold> | FL ItemHoldPeriod
    ```

- **Assim como as caixas de correio normais, o assistente de pasta gerenciada (MFA) também processa caixas de correio inativas.** No Exchange Online, a MFA processa as caixas de correio aproximadamente uma vez a cada sete dias. Após alterar a duração da retenção para uma caixa de correio inativa, você pode usar o cmdlet **Start-ManagedFolderAssistant** para iniciar imediatamente o processamento da nova duração de retenção para a caixa de correio inativa. Execute o seguinte comando. 

    ```powershell
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- **Se várias isenções forem colocadas em uma caixa de correio inativa, nem todos os GUIDs de retenção serão exibidos.** Você pode executar o comando a seguir para exibir os GUIDs de todas as isenções (exceto as isenções de litígio) que são colocadas em uma caixa de correio inativa. 
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
